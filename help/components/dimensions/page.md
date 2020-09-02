---
title: Page
description: Nom de la page.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 71%

---


# Page

La dimension « Page » liste les noms des pages de votre site. Il s’agit de l’une des dimensions les plus courantes et utilisées dans Adobe Analytics, car elle permet d’identifier les pages de votre site qui offrent les meilleures performances.

Cette dimension est liée aux dimensions [Section du site](site-section.md) et [Serveur](server.md). Page est la dimension la plus granulaire, Serveur est la moins granulaire et Section du site est comprise entre les deux.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la chaîne [`pageName` de](/help/implement/validate/query-parameters.md) requête dans les appels de vue de [page (`t()`)](/help/implement/vars/functions/t-method.md). [Les appels de suivi de lien (`tl()`)](/help/implement/vars/functions/tl-method.md) dépouillent toujours cette dimension, même si la chaîne de `pageName` requête existe.

AppMeasurement collecte ces données à l’aide de la variable [`pageName`](/help/implement/vars/page-vars/pagename.md). If the `pageName` variable is not defined, it falls back to using the [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Éléments de Dimension

Les éléments de Dimension incluent le nom des pages de votre site. Votre organisation détermine les éléments de dimension spécifiques que vous souhaitez utiliser. Certaines organisations utilisent directement `document.title`, tandis que d’autres formulent un chemin de navigation personnalisé. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un [document de conception de solution](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Dans Reports &amp; Analytics, les mesures de conversion utilisent l’attribution linéaire pour cette dimension. Par exemple, les recettes sont fractionnées entre toutes les pages vues lors d’une visite avant un événement `purchase`. Analysis Workspace utilise la dernière attribution par défaut, avec la possibilité d’utiliser n’importe quel modèle d’attribution.
