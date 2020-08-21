---
title: Prop
description: Dimension personnalisée que vous pouvez utiliser dans les rapports.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 63%

---


# Prop

*Cette page d’aide décrit le fonctionnement des props en tant que dimension. Pour plus d’informations sur la mise en œuvre des props, voir[props](/help/implement/vars/page-vars/prop.md)dans le guide d’utilisation de mise en œuvre.*

Les props sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles ne persistent pas au-delà de l’accès défini.

>[!TIP]
>
>Dans la plupart des cas, Adobe recommande d’utiliser des [eVars](evar.md). Dans les versions précédentes d’Adobe Analytics, les props et eVars présentaient des avantages et des inconvénients les uns pour les autres. Toutefois, Adobe a amélioré les eVars afin qu’elles répondent à presque tous les cas d’utilisation des props.

Si vous disposez d’un [document de conception de solution](/help/implement/prepare/solution-design.md), vous pouvez attribuer ces dimensions personnalisées aux valeurs propres à votre entreprise. Le nombre de props disponibles dépend de votre contrat avec Adobe. Si le contrat que vous avez conclu avec Adobe le prévoit, vous pouvez obtenir jusqu’à 75 props.

## Renseignement des props avec des données

Chaque prop collecte des données de la chaîne de requête [`c1` - `c75` ](/help/implement/validate/query-parameters.md) dans les demandes d’image. Par exemple, le paramètre de chaîne de requête `c1` collecte des données pour prop1, tandis que le paramètre de chaîne de requête `c68` collecte des données pour prop68.

AppMeasurement, qui compile les variables JavaScript en une demande d’image pour la collecte de données, utilise les variables `prop1` - `prop75`. Consultez [prop](/help/implement/vars/page-vars/prop.md) dans le guide d’utilisation de mise en œuvre pour obtenir des instructions de mise en œuvre.

## Éléments de Dimension

Les props contenant des chaînes personnalisées dans votre implémentation, votre organisation détermine les éléments de dimension de chaque prop. Make sure you record the purpose of each prop and typical dimension items in a [solution design document](/help/implement/prepare/solution-design.md).

## Respect de la casse

Par défaut, les props ne sont pas sensibles à la casse. Si vous envoyez la même valeur dans différents cas (par exemple, `"DOG"` et `"Dog"`), Analysis Workspace les regroupe dans le même élément de dimension. La casse de la première valeur affichée au début du mois de rapports est utilisée. Le Data Warehouse affiche la première valeur rencontrée pendant la période de demande.

Vous pouvez rendre toute prop sensible à la casse. Vous pouvez également désactiver le respect de la casse pour toute prop une fois qu’elle est activée. Contactez le service à la clientèle d’Adobe avec l’identifiant de la suite de rapports et les variables souhaitées pour inverser la sensibilité à la casse.

>[!IMPORTANT]
>
>Le basculement de la sensibilité à la casse peut masquer des éléments de dimension, provoquer des résultats inattendus avec des segments et provoquer des problèmes avec les filtres. L’Adobe recommande vivement de modifier ce paramètre entre deux périodes principales, telles que le début d’un mois ou d’une année.

## Valeur des props par rapport aux eVars

Dans la plupart des cas, Adobe recommande d’utiliser des eVars. Les exceptions à cette déclaration sont les suivantes :

* Vous pouvez utiliser des props dans les rapports en temps réel. L’affichage des eVars dans les rapports prend au moins 30 minutes.
* Les props peuvent devenir des props de liste, qui acceptent plusieurs valeurs dans le même accès. Les variables de liste sont une variable distincte et seules trois variables de liste sont disponibles.
* Lorsque vous activez le cheminement sur une prop, les dimensions [Entrée](entry-dimensions.md) et [Sortie](exit-dimensions.md) sont immédiatement disponibles. Si vous souhaitez des dimensions d’entrée et de sortie pour les eVars, vous pouvez créer un segment manuellement.

Consultez [eVar](evar.md) pour plus de comparaisons entre les props et les eVars.
