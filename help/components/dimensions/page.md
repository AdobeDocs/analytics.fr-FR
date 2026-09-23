---
title: Page
description: Nom de la page.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 54%
---
# Page

La [dimension](overview.md) « Page » répertorie les noms des pages de votre site. Il s’agit de l’une des dimensions les plus couramment utilisées dans Adobe Analytics, car elle fournit des informations sur les pages de votre site qui offrent les meilleures performances.

Cette dimension est liée aux dimensions [Section du site](site-section.md) et [Serveur](server.md). Page est la dimension la plus granulaire, Serveur est la moins granulaire et Section du site est comprise entre les deux.

## Renseignement de cette dimension avec des données

Définissez la variable [`pageName`](/help/implement/vars/page-vars/pagename.md) dans [Appels de page vue (`t()`)](/help/implement/vars/functions/t-method.md). Si la variable `pageName` n’est pas définie, cette dimension revient à utiliser la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md). [Les appels de suivi des liens (`tl()`)](/help/implement/vars/functions/tl-method.md) éliminent toujours cette dimension, même si la valeur `pageName` existe.

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`pageName`](/help/implement/vars/page-vars/pagename.md) |
| **Champ Web SDK/XDM** | [`web.webPageDetails.name`](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/data-types/webpage-details) |
| **Paramètre de requête** | [`pageName`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<pageName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 100 octets |
| **Persistance** | Hit |

## Éléments de dimension

Les éléments de dimension comprennent les noms des pages de votre site. Votre entreprise détermine les éléments de dimension spécifiques que vous souhaitez utiliser. Certaines organisations utilisent directement `document.title`, tandis que d’autres formulent un chemin de navigation personnalisé. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un [document de conception de solution](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Analysis Workspace utilise la dernière attribution par défaut, avec la possibilité d’utiliser n’importe quel modèle d’attribution.
