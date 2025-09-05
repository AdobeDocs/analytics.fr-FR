---
title: eVars de marchandisage et méthodes de recherche de produit
description: Analyse approfondie des concepts sous-jacents aux eVars de marchandisage et de la manière dont elles traitent et affectent les données.
feature: Admin Tools
role: Admin
exl-id: 9e1a39aa-451f-49bb-8e39-797b6bbd5499
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '5279'
ht-degree: 95%

---

# eVars de marchandisage et méthodes de recherche de produit

Ce document hautement détaillé décrit les concepts sous-jacents aux eVars de marchandisage, qui traitent et attribuent les données différemment des eVars standards. Il explique également comment les eVars de marchandisage se rapportent aux méthodes de recherche de produit.

## Présentation

L’utilisation d’eVars de marchandisage vous permet d’attribuer toute activité réussie aux valeurs capturées par les eVars à un niveau *par produit* au lieu d’un niveau *par visite/par commande*.

Bien que la plupart des sites web de vente au détail proposent plusieurs façons de rechercher des produits, Adobe considère que les méthodes de recherche de produit suivantes correspondent aux méthodes fondamentales que chaque client de vente au détail doit suivre dans Adobe Analytics :

* Mots-clés de recherche interne
* Codes de suivi de campagne interne
* Catégories de navigation/marchandisage
* Liens de vente croisée

Pour les besoins de ce document, associons quelques eVars aux solutions comme suit :

* eVar2 : mots-clés de recherche interne
* eVar3 : codes de suivi de campagne interne
* eVar4 : catégories de navigation/marchandisage
* eVar5 : liens de vente croisée

Nous pouvons utiliser une eVar supplémentaire afin de mesurer les performances de toutes les méthodes de recherche de produit les unes par rapport aux autres. Outre les méthodes de recherche décrites ci-dessus, l’eVar inclut d’autres méthodes de recherche dans sa comparaison, telles que des liens vers des pages de détails du produit provenant de sites web externes.

* eVar1 : méthodes de recherche de produit

Au lieu de configurer ces variables comme des eVars standards, configurez-les comme des eVars de marchandisage.

Pour illustrer comment définir ces variables, voici un exemple dans lequel un visiteur décide d’utiliser la recherche interne à l’aide du mot-clé « sandales » pour trouver un produit sur le site. Sur la page de résultats de la recherche par mot-clé, vous devez capturer des données dans au moins deux eVars :

* `eVar2` correspond au mot-clé utilisé dans la recherche (« sandales »).
* `eVar1` correspond à la méthode de recherche de produit utilisée (« recherche interne par mot-clé »).

Lorsque vous définissez ces deux variables sur ces valeurs spécifiques, vous savez que le visiteur utilise le terme de recherche interne par mot-clé « sandales » pour trouver un produit. Dans le même temps, vous savez que le visiteur n’utilise pas d’autres méthodes de recherche de produit pour trouver des produits (par exemple, il ne parcourt pas les catégories de produits au moment précis où il effectue une recherche par mot-clé). Pour s’assurer qu’une affectation appropriée par produit a lieu, ces méthodes inutilisées ne doivent pas être créditées pour la recherche d’un produit trouvé par le biais d’une recherche interne par mot-clé. Par conséquent, vous devez insérer une logique dans le code (tel qu’AppMeasurement, Adobe Experience Platform Web SDK, etc.) qui définit automatiquement les eVars associées à ces autres méthodes de recherche sur une valeur « méthode de non-recherche ».

Par exemple, lorsqu’un utilisateur recherche des produits à l’aide du mot-clé « sandales », la logique du code Analytics doit définir les variables comme étant égales aux suivantes sur la page de résultats de recherche interne par mot-clé :

* eVar2=&quot;sandales&quot; : le mot-clé « sandales » a été utilisé dans la recherche interne par mot-clé.
* eVar1=&quot;recherche interne par mot-clé&quot; : la méthode de recherche « recherche interne par mot-clé » a été utilisée.
* eVar3=&quot;campagne non interne&quot; : aucune campagne interne n’a été utilisée pour accéder à la page des résultats de recherche.
* eVar4=&quot;pas de navigation&quot; : il n’y a pas eu d’accès à une catégorie de navigation sur la page des résultats de recherche.
* eVar5=&quot;pas de vente croisée&quot; : aucun clic n’a été effectué sur un lien de vente croisée dans la page des résultats de la recherche.

## Paramètres des eVars de marchandisage

Voici les différents paramètres que vous pouvez utiliser avec vos eVars de marchandisage. La capture d’écran suivante provient du Gestionnaire de suites de rapports. Pour y accéder, sélectionnez [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Suites de rapports] > [!UICONTROL Modifier les paramètres] > [!UICONTROL Conversion] > [!UICONTROL Variables de conversion] > [!UICONTROL Ajouter nouveau] > [!UICONTROL Activer le merchandising].

![eVars de marchandisage](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/assets/merch-evars1.png)

Pour plus d’informations sur ces paramètres, reportez-vous aux sections situées sous le tableau.

| Paramètre | Description |
|--- | --- |
| Nom | Nom ou dimension de compte rendu des performances à laquelle la variable doit être associée. Si la variable `eVar1` est destinée à capturer les méthodes de recherche de produit, alors le champ Nom de `eVar1` doit être défini sur « Méthodes de recherche de produit ». |
| Marchandisage | Type de syntaxe à utiliser pour capturer les valeurs de l’eVar de marchandisage. |
| Affectation | Permet de déterminer la valeur de l’eVar de marchandisage qui doit être créditée lorsqu’un événement réussi se produit. |
| Expire après | Détermine le moment où les liaisons existantes d’eVar de marchandisage et de produit doivent cesser de fonctionner. |
| Type | Type de données collectées dans l’eVar de marchandisage. |
| Événement de liaison de marchandisage | Événement(s) déterminant le moment où un produit doit être lié à une valeur d’eVar de marchandisage. |
| Réinitialiser | Déclencheur qui réinitialise toutes les données principales de l’eVar à ce stade. |
| Activer le merchandising | Indicateur qui doit être défini sur « Activé » pour transformer l’eVar standard en eVar de marchandisage. |

### Activer le merchandising

Lorsque le paramètre « Activer le marchandisage » est défini sur « Activé », tous les paramètres décrits ci-dessous apparaissent dans le Gestionnaire de suites de rapports. Lorsque le paramètre « Activer le marchandisage » est défini sur « Désactivé », seuls les paramètres d’eVar standard sont disponibles.

### Marchandisage

Cette option n’est pas disponible pour les eVars standard. Le paramètre [!UICONTROL Marchandisage] vous permet de choisir [!UICONTROL Syntaxe de la variable de conversion] ou [!UICONTROL Syntaxe du produit] comme méthode de capture de la valeur de l’eVar de marchandisage.

La **[!UICONTROL Syntaxe de la variable de conversion]** signifie que vous définissez la valeur de l’eVar dans sa propre variable. Par exemple, avec la Syntaxe de la variable de conversion, la valeur `eVar1` de « recherche interne par mot-clé » est définie comme suit dans le code de page (ou le code AppMeasurement, le code Adobe Experience Platform Web SDK, etc.) :

`s.eVar1="internal keyword search";`

Toutefois, avec la **[!UICONTROL Syntaxe du produit]**, l’eVar est définie uniquement dans la variable products d’Adobe Analytics. La variable products d’Analytics est divisée en six parties différentes par produit :

`s.products="[category];[name];[quantity];[revenue];[events];[eVars]"`

* [!UICONTROL Catégorie] et [!UICONTROL Nom] identifient le produit donné.
* La [!UICONTROL Quantité] et le [!UICONTROL Chiffre d’affaires] sont utiles lorsqu’un suivi est effectué sur un achat de produit.
* Les [!UICONTROL Événements] sont utiles pour enregistrer des valeurs d’événements incrémentielles ou monétaires personnalisées qui ne sont pas censées être comptabilisées comme du chiffre d’affaires (notamment les frais d’expédition, les remises, etc.).

Les eVars de marchandisage configurées pour utiliser la Syntaxe du produit sont définies dans la dernière partie de la variable products. Supposons, par exemple, qu’un visiteur ait utilisé une recherche interne par mot-clé pour trouver l’ID de produit « 12345 ». La méthode basée sur la syntaxe du produit pour définir eVar1 dans cet exemple se présenterait comme suit :

`s.products=";12345;;;;eVar1=internal keyword search";`

Notez que des espaces réservés délimités par des points-virgules sont toujours présents pour les parties de la variable products relatives à la quantité, au chiffre d’affaires et aux événements.  Sans ces espaces réservés, le paramètre `eVar1` de la recherche interne par mot-clé serait complètement ignoré.

### Affectation

Le terme « Affectation » pour les eVars de marchandisage est trompeur, en particulier pour les eVars de marchandisage qui utilisent la syntaxe de la variable de conversion. Toutes les eVars standards peuvent avoir leur propre paramètre d’affectation individuel. Cependant, les eVars de marchandisage avec syntaxe de variable de conversion utilisent uniquement le paramètre d’affectation « Le dernier », quels que soient les paramètres d’affectation affichés dans le Gestionnaire de suites de rapports.

Comprendre le fonctionnement de ce paramètre implique de comprendre la différence entre l’affectation d’eVars et la liaison d’eVars de marchandisage. En ce qui concerne les eVars de marchandisage, « Liaison de l’eVar de marchandisage » est un nom plus adéquat pour ce paramètre « Affectation ».

#### Paramètre d’affectation d’eVar standard

Chaque fois qu’une eVar avec syntaxe standard est collectée à partir d’une demande d’image, les serveurs de traitement Adobe Analytics insèrent des données dans une autre colonne de la base de données, appelée colonne `post_evar`. Étant donné que les eVars sont censées être persistantes (elles expirent à un moment situé au-delà de l’accès actuel dans la plupart des cas), les serveurs définissent cette colonne `post_evar` à chaque demande d’image suivante. Elle est définie sur la dernière valeur transmise à l’eVar correspondante. Pour les eVars standards, lorsqu’un événement de succès se produit, Adobe Analytics utilise la colonne `post_evar` au lieu de la colonne eVar habituelle pour déterminer la valeur d’eVar devant être créditée pour l’événement.

Pour les eVars standards, le paramètre d’affectation détermine si la première ou la dernière valeur d’eVar collectée au cours d’une certaine période sera insérée dans la colonne `post_evar`. Si le paramètre d’affectation d’une eVar standard équivaut à « Valeur d’origine (première) », la première valeur d’eVar collectée auprès du visiteur est insérée dans la colonne `post_evar` pour toutes les demandes d’image ultérieures. Cela se poursuit pour toutes les futures demandes envoyées à partir du navigateur de ce visiteur, et ce, jusqu’à ce que l’eVar expire en fonction de son paramètre « Expire après ».

Si le paramètre d’affectation d’une eVar standard équivaut à « Le dernier », la dernière valeur d’eVar collectée auprès du visiteur est renseignée dans la colonne `post_evar` pour toutes les demandes d’image suivantes. L’affectation « Le dernier » implique que la valeur `post_evar` change chaque fois que son eVar correspondante est définie sur une nouvelle valeur dans une demande d’image. L’affectation « Valeur d’origine (première) » implique que la colonne `post_evar` ne change pas entre les accès, même si l’eVar correspondante peut être définie sur une valeur différente dans une demande d’image ultérieure.

#### Paramètre d’affectation (liaison) d’eVar de marchandisage

Comme mentionné précédemment, toutes les eVars de marchandisage avec syntaxe de variable de conversion disposent uniquement d’une affectation « Le dernier ». Par conséquent, le paramètre d’affectation des eVars de merchandising ne détermine pas les valeurs qui sont insérées dans la colonne post_evar lorsqu’un visiteur continue à utiliser le site. Ce paramètre détermine plutôt la valeur d’eVar liée à un produit et la manière dont ces produits réaffectent leurs événements de succès aux valeurs d’eVar auxquelles ils sont liés.

Voici ce qui se produit lorsque le paramètre d’affectation (c’est-à-dire de liaison) d’une eVar de marchandisage est défini sur « Valeur d’origine (première) » : tous les produits définis avec la colonne post_evar et qui n’ont pas été précédemment liés à l’eVar « prétraitée » correspondant à cette colonne seront liés à la valeur contenue dans la colonne en question.  Cette liaison entre la valeur de l’eVar et le produit restera la même jusqu’à expiration de l’eVar, selon les réglages du paramètre « Expire après » qui se trouve dans les paramètres de la suite de rapports.

Chaque fois qu’une demande d’image répond aux critères qui lieraient autrement un produit déjà lié à la valeur d’eVar la plus récemment définie, le paramètre « Valeur d’origine (première) » force les serveurs de collecte de données d’Adobe Analytics à ignorer toute autre tentative de ce type. L’inverse se produit avec les eVars de marchandisage dont le paramètre d’affectation (liaison) équivaut à « Le dernier ». Chaque fois qu’une demande d’image répond aux critères qui lient un produit à une eVar de marchandisage, le produit se lie (et se relie) à la valeur la plus récente transmise à l’eVar, ou à la valeur qui est (toujours) contenue dans la colonne `post_evar`.

Comme mentionné précédemment, les eVars de marchandisage vous permettent d’affecter des événements de succès aux valeurs d’eVar par produit plutôt qu’en fonction de la visite/de la commande. Ainsi, chaque fois qu’un produit lié est associé à un événement de succès (un achat ou un ajout au panier, par exemple), l’événement de succès crédite à la fois le produit et les valeurs de l’eVar de marchandisage auxquelles le produit est lié à ce moment-là.

### Expire après

Le paramètre d’expiration d’une eVar de marchandisage vous permet de choisir les éléments suivants :

* Le moment où les liaisons produit/eVar expirent.

* Le moment où la colonne post_evar ne doit plus être automatiquement remplie suite à la transmission d’une eVar dans une demande d’image.

L’expiration d’une eVar peut survenir lorsqu’un événement de succès est enregistré ou qu’une certaine période s’écoule. Adobe Analytics n’autorise qu’un seul paramètre d’expiration à la fois par eVar.

En ce qui concerne la méthode de recherche de produit, il est recommandé de définir l’expiration d’une eVar de marchandisage sur :

* la durée pendant laquelle un produit est conservé dans le panier d’un site avant que le site ne le supprime automatiquement du panier (par exemple, 14 jours, 30 jours, etc.) ;
* OU le moment où l’événement d’achat a lieu.

Avec l’un ou l’autre de ces paramètres, le crédit de commande/unité/chiffre d’affaires attribué à un produit acheté par un visiteur est affecté aux valeurs de l’eVar de marchandisage auxquelles les produits étaient liés à ce moment-là.

### Type

Le paramètre de type d’eVar détermine le type de données inséré dans l’eVar. Dans la plupart des cas, cette valeur doit être égale à « Texte ». L’utilisation de « Compteur » pour une eVar de marchandisage est rare. Cependant, le « Compteur » peut être utilisé pour attribuer des succès aux valeurs d’eVars de compteur sur la base du produit. Discuter de solutions avec un type de « compteur » n’entre pas dans le cadre de ce document.

### Événement de liaison de marchandisage

Le paramètre Événement de liaison de marchandisage vous permet de spécifier les conditions provoquant la liaison d’un produit à une valeur d’eVar de marchandisage. Ces conditions sont uniquement limitées au déclenchement d’événements de succès ou d’eVars spécifiques. Le déclenchement de variables de trafic (par exemple, props) n’a ainsi aucun effet sur les liaisons de marchandisage.

Notez que le paramètre Événement de liaison de marchandisage peut lier un produit à une valeur d’eVar par le biais de plusieurs événements. Exemples :

* Par le biais d’un événement d’affichage de produit
* Par le biais d’un événement d’ajout au panier
* Par le biais d’un événement d’achat

Par défaut, le paramètre lie un produit à une valeur d’eVar de marchandisage chaque fois qu’un(e) autre événement/eVar (de marchandisage ou standard) est contenu(e) dans la même demande d’image que le produit.

### Réinitialiser

Le paramètre Réinitialiser vous permet de faire « expirer » immédiatement toutes les valeurs d’eVar pour tous les visiteurs qui disposent actuellement d’une valeur `post_evar` dans la base de données principale d’Adobe Analytics. Il élimine également toutes les liaisons produit/eVar actuelles.

>[!IMPORTANT]
>Adobe ne recommande pas l’utilisation du paramètre Réinitialiser, sauf si vous avez pleinement l’intention de laisser l’eVar « repartir de zéro » au niveau des données, et ce, dès le moment où la réinitialisation a lieu.

## Quels paramètres devriez-vous utiliser ?

Parmi les nombreuses combinaisons de paramètres disponibles, vous pouvez vous demander : quelles sont celles qui correspondent aux bonnes pratiques ?

Si vous souhaitez lier la « recherche interne par mot-clé » à l’ID de produit 12345, définissez la variable products comme suit :

`s.products=";12345;;;;eVar1=internal keyword search";`

Tous les événements de succès (ajouts au panier, achats) capturés en même temps que l’ID de produit 12345 sont crédités à la fois à l’ID de produit 12345 et à la valeur eVar1 de la « recherche interne par mot-clé ». La seule manière dont une valeur eVar1 différente peut être créditée pour des événements de succès associés à l’ID de produit 12345 est si la variable eVar1 était plus tard définie sur une valeur différente dans la variable products (avec l’ID de produit 12345).

Par exemple :

```js
s.products=";12345;;;;eVar1=internal campaign";
```

Ce paramètre de variable modifie la liaison de l’ID de produit 12345, en la faisant passer de la valeur eVar1 de « recherche interne par mot-clé » à la valeur eVar1 de « campagne interne ». En outre, cette modification de liaison se produit lorsque l’eVar est configurée pour utiliser la syntaxe du produit et le paramètre d’affectation (liaison) « Le dernier ». Si le paramètre d’affectation (liaison) était à la place défini sur « Valeur d’origine (première) », définir eVar1 sur « campagne interne » avec l’ID de produit 12345 ne relierait pas l’ID de produit 12345 à la valeur d’eVar1 de « campagne interne ». Au lieu de cela, la liaison resterait sur la valeur liée à l’origine, soit « recherche interne par mot-clé ».

### Défis liés à l’utilisation de la syntaxe du produit

Sans planification attentive, l’utilisation de la syntaxe du produit peut entraîner plusieurs problèmes. Prenons l’exemple de l’utilisation de plusieurs eVars pour effectuer le suivi des méthodes de recherche de produit sur le site web. Ici, chaque eVar de méthode de recherche de produit individuel doit être définie en même temps pour créditer une eVar de méthode de recherche spécifique (et éviter de créditer les autres eVars de méthode de recherche). La syntaxe du produit peut être utilisée dans de tels scénarios, mais le code de déploiement qui en résulte est plus complexe.

Si nous reprenons l’exemple des « sandales » et l’adaptons pour utiliser la syntaxe du produit (en supposant que le visiteur ait trouvé un produit avec l’ID « sandal123 » à l’aide du mot-clé « sandales »), la variable products qui en résulte doit être définie comme suit :

`s.products=";sandal123;;;;eVar2=sandals|eVar1=internal search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";`

Bien que la syntaxe de la variable products contenue dans cet exemple soit longue, elle lie chacune des valeurs d’eVar affichées à l’ID de produit « sandal123 ». À partir de là, tous les événements de succès (par exemple, ajouts au panier, achats) capturés en même temps que le produit « sandal123 » sont crédités aux valeurs d’eVar dernièrement liées au produit.  Cet exemple de code indique si l’achat d’une unité du produit « sandal123 » (à 79,95 $) a lieu après la liaison des eVars ci-dessus au produit « sandal123 » :

```js
s.products=";sandal123;1;79.95";
s.events="purchase";
```

Les valeurs suivantes se verraient alors toutes attribuer 1 commande, 1 unité et un chiffre d’affaires de 79,95 $ :

* Valeur eVar2 de « sandales »
* Valeur eVar1 de « recherche interne par mot-clé »
* Valeur eVar3 de « campagne non interne »
* Valeur eVar4 de « pas de navigation »
* Valeur eVar5 de « non-vente croisée »

Il s’agit d’une attribution correcte, ce qui n’est pas un problème. Le principal dilemme de cette approche est plutôt de déterminer comment et quand définir les eVars de la méthode de recherche de produit.

Dans la plupart des cas avec la syntaxe du produit, les eVars de la méthode de recherche de produit doivent être définies sur une page de détails du produit plutôt que sur la page sur laquelle la méthode de recherche a été réellement utilisée (par exemple, sur la page de résultats de la recherche par mot-clé, la page de navigation, la page de destination de la campagne interne, etc.). Il est raisonnable de supposer qu’un produit n’a pas été réellement « trouvé » tant qu’un visiteur n’a pas interagi avec celui-ci dans une certaine mesure. Par conséquent, ces eVars (à l’aide de la syntaxe du produit) ne doivent pas être définies sur la page de la méthode de recherche, car plusieurs produits sont (généralement) affichés sur ces pages. Nous ne souhaitons lier la valeur de la méthode de recherche qu’aux produits avec lesquels le visiteur a interagi.

De plus, lors de l’affichage d’une page de méthode de recherche, les visiteurs peuvent cliquer sur un lien les menant à la page détaillée d’un produit individuel ou ajouter un produit individuel au panier directement à partir de cette page de méthode de recherche. En reprenant notre exemple de mot-clé de recherche « sandales », si un visiteur ajoute le produit « sandal123 » au panier directement à partir d’une page de résultats de recherche par mot-clé, le code de capture de l’ajout au panier (via l’événement onClick du bouton Ajouter au panier, etc.) doit être généré dynamiquement au moment de l’ajout au panier ou « codé en dur » directement via le code de page ou un système de gestion des balises.  Quoi qu’il en soit, voici à quoi devrait ressembler le code à déclencher dans de tels cas :

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
s.tl(true,"o","Cart Add")
```

Ce code lie correctement les valeurs d’eVar affichées ci-dessus au produit « sandal123 ». Toutefois, pour définir correctement ces valeurs lorsque l’événement de clic se produit, le développeur doit effectuer les opérations suivantes :

* Ajouter une logique côté serveur à la page de résultats de recherche qui détermine les valeurs à insérer dans les eVars de la méthode de recherche de produit, puis
* Assembler l’ensemble de la variable products affichée ci-dessus sans erreur de syntaxe.

En outre, si un visiteur décide de « trouver » le produit en cliquant sur un lien vers sa page de détails, le développeur doit effectuer les opérations suivantes :

* Transmettez les détails de la méthode de recherche de produit (comme illustré ci-dessus) depuis la page de la méthode de recherche vers la page des détails du produit, et
* recréez la même valeur de variable products à partir des éléments qui viennent d’être transmis depuis la page précédente.

### Là où la syntaxe du produit est utile

La syntaxe du produit reste utile lorsque

* Des interactions simultanées surviennent avec plusieurs produits dotés des mêmes ID de produit, et
* Les eVars à lier à ces produits doivent avoir des valeurs différentes par ID de produit.

Par exemple, de nombreux produits d’habillement disposent de « SKU enfants », qui désignent la taille, la couleur, le style et tout autre attribut. Ces attributs séparent un produit enfant unique des autres produits appartenant au même produit parent. Imaginons que vous décidiez d’acheter un t-shirt bleu de taille M ainsi qu’un t-shirt rouge de taille L. Supposons que les deux t-shirts possèdent l’ID de produit parent « tshirt123 » et que la variable `eVar10` ait été configurée pour capturer les SKU enfants. Les variables définies sur la page de confirmation d’achat sont définies comme suit :

```js
s.events="purchase";
s.products=";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

Dans ce cas, les deux valeurs `eVar10` (SKU enfant) « tshirt123-m-blue » et « tshirt123-l-red » sont créditées pour l’achat de leurs instances respectives de l’ID de produit « tshirt123 ».

### Défis liés à l’affectation « Le dernier »

Vous pourriez rencontrer d’autres problèmes en utilisant le paramètre d’affectation (liaison) « Le dernier ». Dans de nombreuses expériences de navigation sur le Web, les visiteurs « retrouvent » un produit qu’ils ont déjà consulté et/ou ajouté au panier. Cela se produit généralement lors d’une visite ultérieure ou juste avant qu’ils ne décident de terminer un achat. Supposons que lors d’une visite sur le site, un visiteur trouve le produit « sandal123 » après avoir recherché le mot-clé « sandales ». Il l’ajoute immédiatement au panier à partir de la page des résultats de la recherche par mot-clé. Le code qui capture l’ajout au panier est défini comme suit :

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross";
```

Par conséquent, chacune des valeurs d’eVar affichées dans cette demande d’image est liée au produit « sandal123 ».

Imaginez à présent que la personne n’achète pas le produit au cours de cette visite, mais qu’elle revienne sur le site trois jours plus tard et que le produit « sandals123 » se trouve encore dans son panier. Le visiteur souhaite en savoir plus sur le produit avant de procéder à l’achat. Toutefois, au lieu d’utiliser une recherche par mot-clé pour trouver le produit, le visiteur navigue sur le site. Il se retrouve dans la section de navigation du marchandisage « femmes > chaussures > sandales » juste avant de « retrouver » le produit. Lorsqu’il finit par « retrouver » la page de détails du produit « sandal123 », les variables sont définies comme suit (au chargement de la page) :

```js
s.events="prodView";
s.products=";sandal123;;;;eVar4=womens > shoes > sandals|eVar1=browse|eVar3=non-internal campaign|eVar2=non-search|eVar5=non-cross-sell";
```

Avec le paramètre d’affectation (liaison) configuré sur « Le dernier », le produit « sandal123 » se relie à des valeurs d’eVar complètement différentes de celles auxquelles il était lié à l’origine. De plus, si le visiteur procède ensuite à l’achat de « sandal123 », tout crédit d’achat est attribué à ces valeurs d’eVar nouvellement liées plutôt qu’aux valeurs liées d’origine !

La question est alors la suivante : quelles valeurs d’eVar doivent être créditées pour l’achat ? N’oubliez pas que le visiteur a d’abord trouvé le produit « sandal123 » via une recherche interne par mot-clé. Il l’a ensuite ajouté au panier directement à partir de la page des résultats de recherche. Par conséquent, la valeur eVar1 de « recherche interne par mot-clé » (et la valeur eVar2 de « sandales ») doit être créditée pour l’achat. Toutefois, les paramètres d’affectation (liaison) ont été définis sur « Le dernier ». Par conséquent, la valeur « navigation » de l’eVar1 (et la valeur « femmes > chaussures > sandales » de l’eVar4) est créditée pour l’achat à la place. En effet, il s’agissait des dernières valeurs liées à « sandal123 » avant que le visiteur ne procède à l’achat.

Une solution à ce problème consiste à remplacer le paramètre d’affectation (liaison) de l’eVar de marchandisage « Le dernier » par « Valeur d’origine (première) ». Ainsi, les valeurs d’eVar d’origine liées au produit « sandal123 » sont créditées lorsque l’achat a lieu, indépendamment du nombre de fois où le visiteur « retrouve » le produit.

Si la personne ajoute un produit au panier mais ne l’achète jamais, l’expiration de l’eVar permet à une nouvelle valeur de méthode de recherche d’être liée au produit. L’expiration de l’eVar doit correspondre à la durée pendant laquelle un site web permet à un produit de rester dans le panier avant sa suppression automatique.

### Utilisation de la syntaxe de la variable de conversion

Revenons à la question de la « Syntaxe du produit » par rapport à la « Syntaxe de la variable de conversion ». Adobe a découvert une méthode plus simple permettant à la fois de collecter les eVars de marchandisage relatives à la méthode de recherche de produit et de lier leurs valeurs aux produits trouvés par les visiteurs. L’utilisation de la syntaxe de la variable de conversion réduit en effet le travail d’implémentation dont doivent se charger les développeurs du client. Cette méthode offre des informations identiques, voire plus intéressantes, que celle relative à la syntaxe du produit. Les développeurs doivent simplement suivre les instructions de déploiement qui leur ont été fournies. Le reste du code peut ensuite être placé dans le fichier Adobe AppMeasurement/Adobe Experience Platform Web SDK.

Par exemple, examinons la solution recommandée pour le suivi des performances de la recherche interne par mot-clé. Il est indiqué que, sur la page des résultats de recherche par mot-clé, le code capture le mot-clé recherché par le biais d’une variable prop (par exemple, prop4) ainsi que d’une autre prop (par exemple, prop5). Ces props effectuent le suivi du nombre de résultats affichés à partir de la recherche. Chaque fois qu’une demande d’image Adobe Analytics est générée sur la page des résultats de recherche, les objets de couche de données (ou code de page) déployés par les développeurs sont utilisés pour renseigner les variables ci-dessus (les props).

Une logique supplémentaire contenue dans le fichier AppMeasurement/Adobe Experience Platform Web SDK peut renseigner le reste des variables (les dimensions/eVars de marchandisage) qui doivent être définies au même moment.\
Par exemple, si un nouveau visiteur recherche le mot-clé « sandales », et obtient 25 résultats sur la page de résultats de recherche, le code à déclencher (via le code de page OU la capture de la couche de données) se présente comme suit :

```js
s.prop4="sandals";
s.prop5="25";
```

La logique contenue dans le fichier SDK AppMeasurement/Analytics peut alors transformer automatiquement ce fragment de code en ce qui suit :

```js
s.prop4="sandals";
s.prop5="25";
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Vous n’avez pas à vous soucier de transférer des données d’une page à l’autre et d’essayer de créer une chaîne assez volumineuse et encombrante à insérer dans la variable products. Au lieu de cela, les développeurs peuvent implémenter leur partie des solutions de suivi (ce qui est inséré dans les props) et laisser le reste de l’implémentation au code personnalisé fourni par les services de conseil d’Adobe.

Comme expliqué précédemment, toutes les eVars de marchandisage qui utilisent la syntaxe de la variable de conversion sont dotées du paramètre d’affectation « Le dernier ». Une fois qu’une eVar est définie sur une valeur quelconque, cette valeur persiste pour tous les accès suivants (via la colonne post_evar). Elle persiste jusqu’à ce qu’elle soit définie sur une autre valeur ou jusqu’à l’expiration de l’eVar. Ainsi, tous les produits avec lesquels un utilisateur interagit après la définition des eVars, s’ils n’ont pas déjà été liés à ces eVars, sont liés aux valeurs « Le dernier » transmises à l’eVar.

En reprenant l’exemple ci-dessus, la valeur `eVar2` de « sandales » et la valeur eVar1 de « recherche interne par mot-clé », etc. persistent sur toutes les pages affichées après que la recherche par mot-clé a eu lieu. Elles persistent jusqu’à ce que les eVars soient remplacées par d’autres valeurs. Supposons qu’un visiteur clique sur un lien vers la page des détails du produit pour l’ID de produit « sandal123 » à partir de la page des résultats de recherche par mot-clé.  S’il n’a pas encore été lié, l’ID de produit « sandal123 » se lie à chacune des valeurs contenues dans les colonnes post_evar ou aux valeurs d’eVars collectées à partir de la page précédente (résultats de recherche).

Un autre point doit être reconsidéré avec la syntaxe de la variable de conversion. Les événements de liaison doivent être configurés pour lier une valeur d’eVar à un produit. La simple définition d’une eVar de marchandisage (dans sa propre variable) à côté d’un produit (dans la variable products) dans une demande d’image Adobe Analytics ne lie pas nécessairement la valeur d’eVar au produit.  Au lieu de cela, le paramètre Événement de liaison de marchandisage, défini dans le Gestionnaire de suites de rapports, détermine les critères qui lient une valeur d’eVar à un produit.

Puisque nous souhaitons lier les valeurs de l’eVar de la méthode de recherche de produit à des produits chaque fois qu’une interaction a lieu avec le produit (ce qui implique qu’un produit a été « trouvé »), on peut raisonnablement présumer que les interactions les plus courantes qui peuvent avoir lieu avec un « produit trouvé » correspondent soit à une consultation produit (lorsque les visiteurs accèdent à la page des détails du produit), soit à un ajout au panier (lorsque les visiteurs ajoutent un produit au panier directement à partir d’une page de la méthode de recherche de produit).

Par conséquent, nous pouvons choisir ces deux événements (prodView, scAdd) comme événements de liaison de marchandisage « fondamentaux ».
Voici ce qui se produit lorsque l’un de ces événements de liaison est contenu dans une demande d’image. Tous les ID de produit contenus dans la même demande (dans la variable products) et n’ayant pas été liés à une eVar de marchandisage sont liés aux valeurs les plus récentes transmises dans l’eVar de marchandisage (colonnes post_evar). Toute tentative visant à relier ces produits suite à cette liaison d’origine est ignorée lorsque le paramètre d’affectation (liaison) est défini sur « Valeur d’origine (première) ».

### Paramètres des bonnes pratiques

Voici, ci-dessous, les paramètres des bonnes pratiques. Ils permettent une implémentation facile de la méthode de recherche de produit afin d’offrir les meilleurs résultats. Adobe recommande aux clients de configurer chacune de leurs eVars de marchandisage relatives aux méthodes de recherche de produit (en général) comme suit :

* Marchandisage activé : activé ;
* [Syntaxe] de marchandisage : syntaxe de la variable de conversion ;
* [Liaison] de l’affectation : valeur d’origine (première) ;
* Expire après : durée pendant laquelle un produit reste dans un panier avant d’être automatiquement supprimé (par exemple, 14 jours, 30 jours, etc.).  Si une telle durée n’existe pas, l’expiration survient après l’événement « d’achat » ;
* Type : texte ;
* Événements de liaison de marchandisage : consultation produit, ajout au panier et achat.

## À quoi servent les événements de liaison ?

Lorsqu’un événement de liaison est contenu dans le même appel au serveur que la variable products, les valeurs de l’eVar de marchandisage (qui utilise la syntaxe de la variable de conversion) qui se trouvent dans la colonne post se lient à la variable products. En se basant sur l’exemple précédent, supposons qu’un appel au serveur contienne les valeurs d’eVar de marchandisage suivantes :

```js
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Comme expliqué précédemment, les eVars ci-dessus persistent au-delà de l’accès actuel via leur colonne post_evar respective. Par conséquent, les serveurs d’Adobe transforment les eVars ci-dessus en ce qui suit :

```js
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Ces colonnes post sont stockées dans la base de données d’Adobe et persistent au-delà de l’accès actuel, où elles ont été initialement définies. Cela suppose qu’aucune expiration ou réinitialisation de variable n’a lieu.  Ces valeurs post_evar sont « mises à disposition » par les serveurs d’Adobe au moment de traiter tout futur appel au serveur contenant à la fois l’événement de liaison et la variable products.

La liaison qui a lieu se produit uniquement entre ces valeurs post_evar et le contenu de la variable products. L’événement de liaison ne « lie » pas nécessairement aux eVars ou à la variable products. Il s’agit du « catalyseur » qui indique aux serveurs d’Adobe de lier les valeurs post_evar aux produits.

Supposons que, lors d’un accès ultérieur, les variables suivantes soient définies :

```js
s.products=";sandals123"
s.events="prodView";
```

Dans les colonnes post_evar, les serveurs de traitement d’Adobe considèrent cet accès comme suit :

```js
s.products=";sandals123";
s.events="prodView";
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Supposons que eVar1, eVar2, eVar3, eVar4 et eVar5 aient été configurées pour utiliser `prodView` comme événement de liaison. Si l’une de ces eVars n’est pas configurée pour utiliser prodView comme événement de liaison, la liaison entre cette eVar (configurée incorrectement) et la variable products n’a pas lieu.

La liaison produit des résultats très intéressants, que l’on peut voir dans la valeur de la colonne post_products. La liaison transforme le code ci-dessus et définit quelques autres colonnes post comme suit :

```js
post_events="prodView";
post_products=";sandals123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

La valeur contenue dans la colonne post_products peut vous être familière. Faites défiler ce document vers le haut et comparez cette valeur post_products à la valeur s.products, comme illustré plus bas. Notez que la colonne post_products est définie à l’aide de la syntaxe de la variable du produit.

Cela signifie que la liaison « copie » les valeurs de l’eVar avec syntaxe de la variable de conversion dans la variable products via la syntaxe du produit. Cette action de copie n’a lieu que lorsque la variable products et un événement de liaison (défini via la configuration de l’eVar) sont contenus dans la même requête. À ce stade, la ou les valeurs contenues dans la ou les colonnes post_eVar sont liées au produit. Cette liaison est représentée par l’intermédiaire de la syntaxe du produit, telle qu’elle est stockée dans la colonne post_products.

## eVars de marchandisage, mesure Instances et attribution

Lorsqu’une eVar standard est envoyée dans un appel au serveur Analytics, une instance est toujours attribuée à la valeur de sa colonne post_evar. Les instances représentent le nombre de fois où une eVar a été définie sur une valeur particulière dans une demande d’image.

Supposons, par exemple, que la variable `eVar10` soit une eVar standard avec une attribution [!UICONTROL Dernière touche]. Si vous définissez `s.eVar10="hello world"` sur une page, la valeur de « hello world » est transmise à la colonne post_evar10 lors du traitement de l’accès par Adobe. La mesure des instances est égale à « 1 » pour chaque paramètre `eVar10` individuel de `hello world`. Gardez en tête qu’une instance n’est pas toujours enregistrée lorsque la colonne post_evar dispose d’une valeur. La colonne post_evar détermine plutôt la valeur qui obtient l’instance lorsqu’une instance est enregistrée.

Les instances d’une eVar de marchandisage attribuent les valeurs collectées par l’eVar. Cependant, cela ne se produit que lorsqu’il y a « interaction » simultanée avec un produit lié à la valeur de l’eVar de marchandisage.

Par exemple, la définition de `s.eVar1="Internal Keyword Search"` en elle-même n’accorde aucun crédit de mesure d’instance à la valeur eVar1 de « Recherche interne par mot-clé ». Une instance est bien enregistrée à ce stade. Cependant, à moins qu’un produit ne soit lié à cette valeur « recherche interne par mot-clé » simultanément à la définition de la variable `eVar1`, l’instance est attribuée à l’intervalle Non spécifié. En d’autres termes, la valeur `eVar1` de « recherche interne par mot-clé » peut obtenir une instance. Mais cela se produit uniquement lorsqu’un produit lié à la valeur « recherche interne par mot-clé » apparaît dans la variable products de la même demande d’image.

En résumé, sans configuration supplémentaire, la mesure Instances prête à l’emploi d’une eVar de marchandisage a peu d’utilité. Heureusement, Adobe a publié [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). Cet outil vous permet d’appliquer plusieurs modèles d’attribution à toute mesure personnalisée collectée par Adobe Analytics. Les mesures qui appliquent ces modèles d’attribution n’utilisent pas les valeurs contenues dans les colonnes post_evar ni les valeurs liées à un produit particulier. Au lieu de cela, ces mesures utilisent uniquement les valeurs transmises par le biais des demandes d’image (ou les valeurs capturées par le biais des règles de traitement Adobe Analytics). Vous pouvez utiliser les fonctionnalités d’Attribution pour obtenir une mesure des instances correctement attribuées pour toutes les eVars de marchandisage qui utilisent la syntaxe de la variable de conversion.

![Sélection de l’attribution](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/assets/attribution-select.png)

Lors de l’ajout d’une mesure d’instance d’eVar de marchandisage à un rapport, le modèle d’attribution approprié serait le modèle « Dernière touche ». Le paramètre Intervalle de recherche en amont du modèle n’a pas d’importance dans ce cas. La raison est qu’un modèle d’attribution Dernière touche « forcé » accorde toujours le crédit d’instance à chaque valeur individuelle transmise par le biais d’une requête. Et cela, qu’importe si les paramètres d’attribution/de liaison réels de l’eVar sont définis sur « Le dernier » et sur « Valeur d’origine (première) ».
