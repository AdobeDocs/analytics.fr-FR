---
title: Page
description: Nom de la page.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 80%

---

# Page

La &quot;page&quot; [dimension](overview.md) répertorie les noms des pages de votre site. Il s’agit de l’une des dimensions les plus courantes et utilisées dans Adobe Analytics, car elle permet d’identifier les pages de votre site qui offrent les meilleures performances.

Cette dimension est liée aux dimensions [Section du site](site-section.md) et [Serveur](server.md). Page est la dimension la plus granulaire, Serveur est la moins granulaire et Section du site est comprise entre les deux.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`pageName` chaîne de requête](/help/implement/validate/query-parameters.md) dans les [appels des pages vues (`t()`)](/help/implement/vars/functions/t-method.md). Les [appels de suivi des liens (`tl()`)](/help/implement/vars/functions/tl-method.md) éliminent toujours cette dimension, même si la chaîne de requête `pageName` existe.

AppMeasurement collecte ces données à l’aide de la variable [`pageName`](/help/implement/vars/page-vars/pagename.md). Si la variable `pageName` n’est pas définie, cette dimension revient à l’utilisation de la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Éléments de dimension

Les éléments de dimension comprennent les noms des pages de votre site. Votre entreprise détermine les éléments de dimension spécifiques que vous souhaitez utiliser. Certaines organisations utilisent directement `document.title`, tandis que d’autres formulent un chemin de navigation personnalisé. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un [document de conception de solution](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Analysis Workspace utilise la dernière attribution par défaut, avec la possibilité d’utiliser n’importe quel modèle d’attribution.
