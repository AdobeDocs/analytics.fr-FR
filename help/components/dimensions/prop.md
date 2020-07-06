---
title: Prop
description: Dimension personnalisée que vous pouvez utiliser dans les rapports.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 26%

---


# Prop

*Cette page d’aide décrit le fonctionnement des props en tant que dimension. For information on how to implement props, see[props](/help/implement/vars/page-vars/prop.md)in the Implement user guide.*

Les props sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Ils ne persistent pas au-delà de l&#39;impact qu&#39;ils ont défini.

>[!TIP]
>
>Adobe recommends using [eVars](evar.md) in most cases. Dans les versions précédentes d’Adobe Analytics, les props et eVars présentaient des avantages et des inconvénients les uns pour les autres. Toutefois, Adobe a amélioré les eVars afin qu’elles répondent à presque tous les cas d’utilisation des props.

Si vous disposez d’un document [de conception de](/help/implement/prepare/solution-design.md)solution, vous pouvez allouer ces dimensions personnalisées aux valeurs propres à votre entreprise. Le nombre de props disponibles dépend de votre contrat avec Adobe. Jusqu’à 75 props sont disponibles si votre contrat avec Adobe le prend en charge.

## Renseigner les props avec des données

Chaque prop collecte les données de la chaîne [`c1` `c75` -](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. Par exemple, le paramètre de chaîne de `c1` requête collecte des données pour prop1, tandis que le paramètre de chaîne de `c68` requête collecte des données pour prop68.

AppMeasurement, qui compile des variables JavaScript dans une demande d’image pour la collecte de données, utilise les variables `prop1` - `prop75`. Voir [prop](/help/implement/vars/page-vars/prop.md) dans le guide de l’utilisateur Mise en oeuvre pour obtenir des instructions d’implémentation.

## Valeurs de dimension

Les props contenant des chaînes personnalisées dans votre implémentation, votre organisation détermine les valeurs de dimension de chaque prop. Veillez à enregistrer l’objectif de chaque valeur de prop et de dimension standard dans un document [de conception de](/help/implement/prepare/solution-design.md)solution.

## Valeur des props sur les eVars

Dans la plupart des cas, Adobe recommande d’utiliser des eVars. Les exceptions à cette déclaration sont les suivantes :

* Vous pouvez utiliser des props dans des rapports en temps réel. L’affichage des eVars en rapports prend au moins 30 minutes.
* Les props peuvent devenir des props de liste, qui acceptent plusieurs valeurs dans le même accès. Les variables de liste sont une variable distincte et seules trois variables de liste sont disponibles.
* Lorsque vous activez le cheminement sur une prop, les dimensions [Entrée](entry-dimensions.md) et [Sortie](exit-dimensions.md) deviennent immédiatement disponibles. Si vous souhaitez des dimensions d’entrée et de sortie pour les eVars, vous pouvez créer manuellement un segment.

Voir [eVar](evar.md) pour plus de comparaisons entre les props et les eVars.
