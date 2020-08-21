---
title: Page
description: Nom de la page.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 88%

---


# Page

La dimension « Page » liste les noms des pages de votre site. Il s’agit de l’une des dimensions les plus courantes et utilisées dans Adobe Analytics, car elle permet d’identifier les pages de votre site qui offrent les meilleures performances.

Cette dimension est liée aux dimensions [Section du site](site-section.md) et [Serveur](server.md). Page est la dimension la plus granulaire, Serveur est la moins granulaire et Section du site est comprise entre les deux.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`pageName`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable `pageName`. Si la variable `pageName` n’est pas définie, l’URL de la page est utilisée.

## Éléments de Dimension

Les éléments de Dimension incluent le nom des pages de votre site. Votre organisation détermine les éléments de dimension spécifiques que vous souhaitez utiliser. Certaines organisations utilisent directement `document.title`, tandis que d’autres formulent un chemin de navigation personnalisé. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un [document de conception de solution](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Dans Reports &amp; Analytics, les mesures de conversion utilisent l’attribution linéaire pour cette dimension. Par exemple, les recettes sont fractionnées entre toutes les pages vues lors d’une visite avant un événement `purchase`. Analysis Workspace utilise la dernière attribution par défaut, avec la possibilité d’utiliser n’importe quel modèle d’attribution.
