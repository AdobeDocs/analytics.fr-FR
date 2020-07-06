---
title: Page
description: Nom de la page.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---


# Page

La dimension &quot;Page&quot; liste les noms des pages de votre site. Il s’agit de l’une des dimensions les plus courantes utilisées dans Adobe Analytics, car il permet de savoir quelles pages de votre site offrent les meilleures performances.

Cette dimension est liée à la section [](site-section.md) Site et aux dimensions [Serveur](server.md) . La page est la plus granulaire, le serveur est la moins granulaire et la section du site est comprise entre les deux.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la chaîne [`pageName` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la `pageName` variable. Si la `pageName` variable n’est pas définie, elle revient à utiliser l’URL de la page.

## Valeurs de dimension

Les valeurs de dimension incluent le nom des pages de votre site. Votre organisation détermine les valeurs de dimension spécifiques que vous souhaitez utiliser. Certaines organisations utilisent directement `document.title`, tandis que d’autres formulent un chemin de navigation personnalisé. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un document [de conception de](/help/implement/prepare/solution-design.md)solution.

>[!NOTE]
>
>Dans les rapports et Analytics, les mesures de conversion utilisent l’attribution linéaire pour cette dimension. For example, revenue is split between all pages viewed in a visit before a `purchase` event. L’Analysis Workspace utilise la dernière attribution par défaut, avec la possibilité d’utiliser n’importe quel modèle d’attribution.
