---
title: Page
description: Nom de la page.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 94%

---

# Page

La &quot;Page&quot; [dimension](overview.md) répertorie les noms des pages de votre site. Il s’agit de l’une des dimensions les plus courantes et utilisées dans Adobe Analytics, car elle permet d’identifier les pages de votre site qui offrent les meilleures performances.

Cette dimension est liée aux dimensions [Section du site](site-section.md) et [Serveur](server.md). Page est la dimension la plus granulaire, Serveur est la moins granulaire et Section du site est comprise entre les deux.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`pageName` chaîne de requête](/help/implement/validate/query-parameters.md) dans les [appels des pages vues (`t()`)](/help/implement/vars/functions/t-method.md). Les [appels de suivi des liens (`tl()`)](/help/implement/vars/functions/tl-method.md) éliminent toujours cette dimension, même si la chaîne de requête `pageName` existe.

AppMeasurement collecte ces données à l’aide de la variable [`pageName`](/help/implement/vars/page-vars/pagename.md). Si la variable `pageName` n’est pas définie, la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md) est utilisée.

## Éléments de dimension

Les éléments de dimension comprennent les noms des pages de votre site. Votre entreprise détermine les éléments de dimension spécifiques à utiliser. Certaines organisations utilisent directement `document.title`, tandis que d’autres formulent un chemin de navigation personnalisé. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un [document de conception de solution](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Dans Reports &amp; Analytics, les mesures de conversion utilisent l’attribution linéaire pour cette dimension. Par exemple, les recettes sont fractionnées entre toutes les pages vues lors d’une visite avant un événement `purchase`. Analysis Workspace utilise la dernière attribution par défaut, avec la possibilité d’utiliser n’importe quel modèle d’attribution.
