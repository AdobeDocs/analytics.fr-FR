---
title: Prop
description: Dimension personnalisée que vous pouvez utiliser dans les rapports.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 19%

---


# Prop

*Cette page d’aide décrit le fonctionnement des props en tant que dimension. For information on how to implement props, see[props](/help/implement/vars/page-vars/prop.md)in the Implement user guide.*

Les props sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Ils ne persistent pas au-delà de l&#39;impact qu&#39;ils ont défini.

>[!TIP]
>
>Adobe recommends using [eVars](evar.md) in most cases. Dans les versions précédentes d’Adobe Analytics, les props et eVars présentaient des avantages et des inconvénients les uns pour les autres. Toutefois, Adobe a amélioré les eVars afin qu’elles répondent à presque tous les cas d’utilisation des props.

Si vous disposez d’un document [de conception de](/help/implement/prepare/solution-design.md)solution, vous pouvez allouer ces dimensions personnalisées aux valeurs propres à votre entreprise. Le nombre de props disponibles dépend de votre contrat avec Adobe. Jusqu’à 75 props sont disponibles si votre contrat avec Adobe le permet.

## Renseigner les props avec des données

Chaque prop collecte les données de la chaîne [`c1` `c75` -](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. Par exemple, le paramètre de chaîne de `c1` requête collecte des données pour prop1, tandis que le paramètre de chaîne de `c68` requête collecte des données pour prop68.

AppMeasurement, qui compile des variables JavaScript dans une demande d’image pour la collecte de données, utilise les variables `prop1` - `prop75`. Voir [prop](/help/implement/vars/page-vars/prop.md) dans le guide de l’utilisateur Mise en oeuvre pour obtenir des instructions d’implémentation.

## Éléments de Dimension

Les props contenant des chaînes personnalisées dans votre implémentation, votre organisation détermine les éléments de dimension de chaque prop. Veillez à enregistrer l’objectif de chaque élément de prop et de dimension typique dans un document [de conception de](/help/implement/prepare/solution-design.md)solution.

## Respect de la casse

Par défaut, les props ne sont pas sensibles à la casse. Si vous envoyez la même valeur dans différents cas (par exemple, `"DOG"` et `"Dog"`), l’Analysis Workspace les regroupe dans le même élément de dimension. La casse de la première valeur affichée au début du mois de rapports est utilisée. Data warehouse affiche la première valeur rencontrée pendant la période de demande.

Vous pouvez rendre toute prop sensible à la casse. Vous pouvez également désactiver le respect de la casse pour toute prop une fois qu’elle est activée. Contactez le service à la clientèle d’Adobe avec l’identifiant de la suite de rapports et les variables souhaitées pour inverser la sensibilité à la casse.

>[!IMPORTANT]
>
>Le basculement de la sensibilité à la casse peut masquer des éléments de dimension, provoquer des résultats inattendus avec des segments et provoquer des problèmes avec les filtres. L’Adobe recommande vivement de modifier ce paramètre entre deux périodes principales, telles que le début d’un mois ou d’une année.

## Valeur des props sur les eVars

Dans la plupart des cas, Adobe recommande d’utiliser des eVars. Les exceptions à cette déclaration sont les suivantes :

* Vous pouvez utiliser des props dans des rapports en temps réel. L’affichage des eVars en rapports prend au moins 30 minutes.
* Les props peuvent devenir des props de liste, qui acceptent plusieurs valeurs dans le même accès. Les variables de liste sont une variable distincte et seules trois variables de liste sont disponibles.
* Lorsque vous activez le cheminement sur une prop, les dimensions [Entrée](entry-dimensions.md) et [Sortie](exit-dimensions.md) deviennent immédiatement disponibles. Si vous souhaitez des dimensions d’entrée et de sortie pour les eVars, vous pouvez créer manuellement un segment.

Voir [eVar](evar.md) pour plus d’informations sur les comparaisons entre props et eVars.
