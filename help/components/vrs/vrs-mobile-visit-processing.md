---
description: Les sessions contextuelles dans les suites de rapports virtuelles modifient la façon dont Adobe Analytics calcule les visites mobiles. Cet article décrit les implications du traitement des événements d’accès en arrière-plan et de lancement d’applications (toutes deux définies par le SDK Mobile) sur la façon dont les visites mobiles sont définies.
title: Sessions contextuelles
uuid: d354864a-9163-4970-a3a0-f2e9729bdbe3
translation-type: tm+mt
source-git-commit: 3997889ae72920d719203edbb159b55b983158e7

---


# Sessions contextuelles

Les sessions contextuelles dans les suites de rapports virtuelles modifient la manière dont Adobe Analytics calcule les visites à partir de n’importe quel périphérique. Cet article décrit également les implications de traitement des accès en arrière-plan et des  de lancement d’application (tous deux définis par le SDK mobile) sur la manière dont les visites mobiles sont définies.

Vous pouvez définir une visite comme vous le souhaitez sans modifier les données sous-jacentes, pour qu’elle corresponde à la manière dont vos interagissent avec vos expériences numériques.

## Paramètre de l’URL de la perspective client 

Le processus de collecte de données Adobe Analytics vous permet de définir un paramètre de chaîne de  spécifiant la perspective du client (indiqué comme paramètre de chaîne de &quot;cp&quot;). Ce champ spécifie l’état de l’application numérique de l’utilisateur final. Cela vous permet de savoir si un accès a été généré alors qu’une application mobile était en arrière-plan.

## Traitement des accès en arrière-plan 

Un accès en arrière-plan est un type d’accès envoyé à Analytics à partir du SDK mobile Adobe version 4.13.6 et ultérieure lorsque l’application effectue une demande de suivi alors qu’elle se trouve en arrière-plan. Voici quelques exemples typiques :

* Données envoyées lors d’un croisement de géo-barrières
* Interaction de notification Push

Les exemples suivants illustrent la logique utilisée pour déterminer le moment où un de visites se  et se termine pour un lorsque le paramètre &quot;Empêcher les accès en arrière-plan de démarrer une nouvelle visite&quot; est activé ou non pour une suite de rapports virtuelle.

**Si le paramètre « Empêcher les accès en arrière-plan de commencer une nouvelle visite » n’est pas activé :**

Si cette fonctionnalité n’est pas activée pour une suite de rapports virtuelle, les accès en arrière-plan sont traités de la même manière que les autres accès, ce qui signifie qu’ils de nouvelles visites et agissent exactement comme les accès au premier plan. Si, par exemple, un accès en arrière-plan survient moins de 30 minutes (délai d’expiration de session standard pour une suite de rapports) avant un ensemble d’accès en premier plan, l’accès en arrière-plan fait partie de la session.

![](assets/nogood1.jpg)

Si l’accès en arrière-plan se produit plus de 30 minutes avant les accès en premier plan, l’accès en arrière-plan crée sa propre visite, pour un nombre total de visites de 2.

![](assets/nogood2.jpg)

**Si le paramètre « Empêcher les accès en arrière-plan de commencer une nouvelle visite » est activé :**

Les exemples suivants illustrent le comportement des accès en arrière-plan lorsque ce paramètre est activé.

Exemple 1 : un accès en arrière-plan se produit à un temps (t) avant une série d’accès de premier plan.

![](assets/nogoodexample1.jpg)

Dans cet exemple, si *il* est supérieur au délai d’expiration de visite configuré de la suite de rapports virtuelle, l’accès en arrière-plan est exclu de la visite formée par les accès en premier plan. Par exemple, si le délai d’expiration de la visite de la suite de rapports virtuelle était défini sur 15 minutes et *sur 20 minutes* , la visite formée par cette série d’accès (illustrée par le contour vert) exclurait l’accès en arrière-plan. Cela signifie que les eVars définies avec une expiration de &quot;visite&quot; sur l’accès en arrière-plan **ne persistent pas** dans la visite suivante et qu’un de segments de visite n’inclut que les accès au premier plan dans le contour vert.

![](assets/nogoodexample1-2.jpg)

Inversement, si *il* est inférieur au délai d’expiration de visite configuré de la suite de rapports virtuelle, l’accès en arrière-plan est inclus dans la visite comme s’il s’agissait d’un accès de premier plan (représenté par le contour vert) :

![](assets/nogoodexample1-3.jpg)

Cela signifie que :

* Les eVars définies avec une expiration de &quot;visite&quot; sur l’accès en arrière-plan conservent leurs valeurs sur les autres accès de cette visite.
* Toutes les valeurs définies dans l’accès en arrière-plan sont incluses dans l’évaluation logique  du segment de niveau visite.

Dans les deux cas, le nombre total de visites serait de 1.

Exemple 2 : si un accès en arrière-plan se produit après une série d’accès de premier plan, le comportement est similaire :

![](assets/nogoodexample2.jpg)

Si l’accès en arrière-plan survient après le délai d’expiration configuré de la suite de rapports virtuelle, l’accès en arrière-plan ne fait pas partie d’une session (indiqué en vert) :

![](assets/nogoodexample2-1.jpg)

De même, si la période *t* était inférieure au délai d’expiration configuré de la suite de rapports virtuelle, l’accès en arrière-plan est inclus dans la visite formée par les accès au premier plan précédents :

![](assets/nogoodexample2-2.jpg)

Cela signifie que :

* Les eVars définies avec l’expiration &quot;visite&quot; sur les accès au premier plan précédents conservent leurs valeurs sur l’accès en arrière-plan au cours de cette visite.
* Toutes les valeurs définies dans l’accès en arrière-plan sont incluses dans l’évaluation logique  du segment de niveau visite.

Comme auparavant, le nombre total de visites dans les deux cas serait de 1.

Exemple 3 : dans certaines circonstances, un accès en arrière-plan peut entraîner la combinaison de deux visites distinctes en une seule visite. Dans le scénario suivant, un accès en arrière-plan est précédé et suivi d’une série d’accès en premier plan :

![](assets/nogoodexample3.jpg)

Si, dans cet exemple, *t1* et *t2* sont tous deux inférieurs au délai d’expiration de visite configuré par la suite de rapports virtuelle, tous ces accès sont combinés en une seule visite, même si *t1* et *t2 ensemble sont supérieurs au délai d’expiration de la visite :*

![](assets/nogoodexample3-1.jpg)

Si, toutefois, *t1* et *t2* sont supérieurs au délai configuré par la suite de rapports virtuelle, ces accès sont séparés en deux visites distinctes :

![](assets/nogoodexample3-2.jpg)

De même (comme dans nos exemples précédents), si *t1* est inférieur au délai d’expiration et *t2* est inférieur au délai d’expiration, l’accès en arrière-plan sera inclus dans la première visite :

![](assets/nogoodexample3-3.jpg)

Si *t1* est supérieur au délai d’expiration et *t2* inférieur au délai d’expiration, l’accès en arrière-plan est inclus dans la seconde visite :

![](assets/nogoodexample3-4.jpg)

Exemple 4 : dans les scénarios où une série d’accès en arrière-plan se produit pendant le délai de visite de la suite de rapports virtuelle, les accès forment une « visite en arrière-plan » invisible qui n’est pas incluse dans le nombre de visites et n’est pas accessible à l’aide d’un conteneur de segmentation des visites.

![](assets/nogoodexample4.jpg)

Même si cela n’est pas considéré comme une visite, tous les jeux d’eVars disposant d’une expiration de visite conservent leur valeur dans les autres accès en arrière-plan de cette « visite en arrière-plan ».

Exemple 5 : dans les scénarios où plusieurs accès en arrière-plan se produisent consécutivement à la suite d’une série d’accès de premier plan, il est possible (en fonction du paramètre de délai de visite) que les accès en arrière-plan maintiennent une visite active plus longtemps que le délai de visite. Par exemple, si *t1* et *t2* étaient ensemble supérieurs au délai d’expiration de la visite de la suite de rapports virtuelle, mais inférieurs au délai d’expiration, la visite s’étendrait toujours aux deux accès en arrière-plan :

![](assets/nogoodexample5.jpg)

De même, si une série d’accès en arrière-plan survient avant une série d’ de premier plan, un comportement similaire se produit :

![](assets/nogoodexample5-1.jpg)

Les accès en arrière-plan se comportent de cette manière afin de conserver les effets d’attribution des eVars ou d’autres variables définies lors des accès en arrière-plan. Cela permet d’attribuer des  de conversion en premier plan en aval aux actions entreprises lorsqu’une application se trouvait en arrière-plan. Il permet également à un de segments de visite d’inclure des accès en arrière-plan qui ont abouti à une session de premier plan en aval utile pour mesurer l’efficacité des messages Push.

## Comportement de la mesure des visites 

Le nombre de visites est basé uniquement sur le nombre de visites qui incluent au moins un accès de premier plan. Cela signifie que les accès en arrière-plan orphelins ou les &quot;visites en arrière-plan&quot; ne sont pas comptabilisés dans la mesure Visite.

## Temps passé par comportement de la mesure des visites 

Le temps passé est toujours calculé de manière analogue à la façon dont il est sans accès en arrière-plan utilisant le temps entre les accès. Bien que, si une visite inclut des accès en arrière-plan (parce qu’ils se sont produits assez près des accès en premier plan), ces accès sont inclus dans le calcul de la durée par visite comme s’ils s’agissait d’un accès en premier plan.

## Paramètres du traitement des accès en arrière-plan 

Comme le traitement des accès en arrière-plan est uniquement disponible pour les suites de rapports virtuelles utilisant le paramètre Reporter le traitement du temps, Adobe Analytics prend en charge deux méthodes de traitement des accès en arrière-plan afin de conserver les nombres de visites dans la suite de rapports de base (parente) qui n’utilise pas le paramètre Reporter le traitement du temps. Pour accéder à ce paramètre, accédez à la console d’administration d’Adobe Analytics, accédez aux paramètres de la suite de rapports de base applicable, puis au menu &quot;Gestion mobile&quot;, puis au sous-menu &quot; d’applications mobiles&quot;.

1. &quot;Traitement hérité activé&quot; : Il s’agit du paramètre par défaut pour toutes les suites de rapports. En laissant le traitement hérité sur les accès en arrière-plan des processus comme accès normaux dans notre pipeline de traitement en ce qui concerne la suite de rapports de base Attribution de temps non-rapport. Cela signifie que les accès en arrière-plan qui apparaissent dans la suite de rapports de base incrémentent les visites comme un accès normal. Si vous ne souhaitez pas que les accès en arrière-plan apparaissent dans votre suite de rapports de base, définissez ce paramètre sur Désactivé.
1. &quot;Traitement hérité désactivé&quot; : Le traitement hérité des accès en arrière-plan étant désactivé, tous les accès en arrière-plan envoyés à la suite de rapports de base sont ignorés par la suite de rapports de base et ne sont accessibles que lorsqu’une suite de rapports virtuelle créée sur cette suite de rapports de base est configurée pour utiliser le traitement du temps des rapports. Cela signifie que les données capturées par les accès en arrière-plan envoyés à cette suite de rapports de base apparaissent uniquement dans une suite de rapports virtuelle activée pour le traitement du temps des rapports.

   Ce paramètre est destiné aux clients qui souhaitent tirer parti du nouveau traitement des accès en arrière-plan sans modifier le nombre de visites de leur suite de rapports de base.

Dans les deux cas, les accès en arrière-plan sont facturés au même coût que tout autre accès envoyé à Analytics.

## Démarrage de nouvelles visites à chaque lancement d’une application 

Outre le traitement de l’accès en arrière-plan, les suites de rapports virtuelles peuvent forcer une nouvelle visite au chaque fois que le SDK mobile envoie un de lancement d’application . Lorsque ce paramètre est activé, chaque fois qu’un de lancement d’application est envoyé à partir du SDK, il force une nouvelle visite à l’, que la visite ait atteint son délai d’expiration ou non. L’accès contenant le de lancement de l’application est inclus comme premier accès lors de la visite suivante et incrémente le nombre de visites et crée un de visite distinct pour la segmentation.
