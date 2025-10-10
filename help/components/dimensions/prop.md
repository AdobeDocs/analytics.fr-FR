---
title: Prop
description: Une dimension personnalisée que vous pouvez utiliser dans les rapports.
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 93%

---

# Prop

*Cette page d’aide décrit le fonctionnement des props en tant que [dimension](overview.md). Pour plus d’informations sur la mise en œuvre des props, voir [props](/help/implement/vars/page-vars/prop.md) dans le guide d’utilisation de mise en œuvre.*

Les props sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles ne persistent pas au-delà de l’accès défini.

>[!TIP]
>
>Dans la plupart des cas, Adobe recommande d’utiliser des [eVars](evar.md). Dans les versions précédentes d’Adobe Analytics, les props et eVars présentaient des avantages et des inconvénients les uns pour les autres. Toutefois, Adobe a amélioré les eVars afin qu’elles répondent à presque tous les cas d’utilisation des props.

Si vous disposez d’un [document de conception de solution](/help/implement/prepare/solution-design.md), vous pouvez attribuer ces dimensions personnalisées aux valeurs propres à votre entreprise. Le nombre de props disponibles dépend de votre contrat avec Adobe. Si le contrat que vous avez conclu avec Adobe le prévoit, vous pouvez obtenir jusqu’à 75 props.

## Renseignement des props avec des données

Chaque prop collecte des données de la chaîne de requête [`c1` - `c75` &#x200B;](/help/implement/validate/query-parameters.md) dans les demandes d’image. Par exemple, le paramètre de chaîne de requête `c1` collecte des données pour prop1, tandis que le paramètre de chaîne de requête `c68` collecte des données pour prop68.

AppMeasurement, qui compile les variables JavaScript en une demande d’image pour la collecte de données, utilise les variables `prop1` - `prop75`. Consultez [prop](/help/implement/vars/page-vars/prop.md) dans le guide d’utilisation de mise en œuvre pour obtenir des instructions de mise en œuvre.

## Éléments de dimension

Étant donné que les props contiennent des chaînes personnalisées dans votre mise en œuvre, votre organisation détermine les éléments de dimension de chaque prop. Veillez à enregistrer l’objectif de chaque prop et des éléments de dimension standard dans un [document de conception de solution](/help/implement/prepare/solution-design.md).

## Respect de la casse

Par défaut, les props ne sont pas sensibles à la casse. Si vous envoyez la même valeur dans différents cas (par exemple, `"DOG"` et `"Dog"`), Analysis Workspace les regroupe dans le même élément de dimension. La casse de la première valeur affichée au début du mois de rapports est utilisée. Data Warehouse affiche la première valeur rencontrée pendant la période de demande.

Vous pouvez rendre toute prop sensible à la casse. Vous pouvez également désactiver le respect de la casse pour toute prop où il est activé. Contactez l’assistance clientèle d’Adobe avec l’identifiant de suite de rapports et les variables souhaitées pour activer ou désactiver le respect de la casse.

>[!WARNING]
>
>Activer/désactiver le respect de la casse peut réduire drastiquement les éléments de dimension, provoquer des résultats inattendus avec des segments et provoquer des problèmes avec les filtres. Adobe recommande vivement de modifier ce paramètre entre deux périodes importantes, comme au début d’un mois ou d’une année.

## Valeur des props par rapport aux eVars

Dans la plupart des cas, Adobe recommande d’utiliser des eVars. Les exceptions à cette déclaration sont les suivantes :

* Vous pouvez utiliser des props dans les rapports en temps réel. L’affichage des eVars dans les rapports prend au moins 30 minutes.
* Les props peuvent devenir des props de liste, qui acceptent plusieurs valeurs dans le même accès. Les variables de liste sont une variable distincte et seules trois variables de liste sont disponibles.
* Lorsque vous activez le cheminement sur une prop, les dimensions [Entrée](entry-dimensions.md) et [Sortie](exit-dimensions.md) sont immédiatement disponibles. Si vous souhaitez des dimensions d’entrée et de sortie pour les eVars, vous pouvez créer un segment manuellement.

Consultez [eVar](evar.md) pour plus de comparaisons entre les props et les eVars.
