---
title: URL de la page
description: L’URL de la page.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
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
source-wordcount: '238'
ht-degree: 52%
---
# URL de la page

La [dimension](overview.md) « URL de la page » répertorie les URL de votre site.

>[!IMPORTANT]
>
>Cette dimension est uniquement disponible dans Data Warehouse. Si vous souhaitez utiliser une dimension URL dans dʼautres solutions Analytics, pensez à copier la valeur dans une [eVar](evar.md) pour chaque hit.

## Renseignement de cette dimension avec des données

AppMeasurement collecte automatiquement l’URL de la page à chaque [appel de page vue (`t()`)](/help/implement/vars/functions/t-method.md). Vous pouvez remplacer la valeur collectée à lʼaide de la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md). Si une URL dépasse 255 octets, le dépassement est stocké dans le paramètre de chaîne de requête `-g`. Le protocole et les chaînes de requête dans l’URL sont inclus. [Les appels de suivi des liens (`tl()`)](/help/implement/vars/functions/tl-method.md) éliminent toujours cette dimension, même si la valeur d’URL existe.

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`pageURL`](/help/implement/vars/page-vars/pageurl.md) |
| **Champ Web SDK/XDM** | [`web.webPageDetails.URL`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Paramètre de requête** | [`g`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<pageUrl>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 255 octets (pas de limite fixe avec dépassement) |
| **Persistance** | Hit |

## Renseignement d’une eVar avec une URL

Adobe recommande de définir une eVar sur la chaîne concaténée `window.location.hostname + window.location.pathname`. Cette chaîne fonctionne généralement mieux que `window.location.href` parce qu’elle omet le protocole, les chaînes de requête et les balises d’ancrage.

Si vous souhaitez que l’eVar corresponde exactement à la dimension « URL de la page » dans Data Warehouse, vous pouvez utiliser des [variables dynamiques](/help/implement/vars/page-vars/dynamic-variables.md) et définir l’eVar sur `D=g` pour chaque hit.

## Éléments de dimension

Les éléments de dimension comprennent les adresses URL des pages de votre site.
