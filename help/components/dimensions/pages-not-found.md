---
title: Pages introuvables (dimensions)
description: Adresses URL ayant renvoyé une erreur sur votre site.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc
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
source-wordcount: '276'
ht-degree: 48%
---
# Pages introuvables

>[!BEGINSHADEBOX]

*Cette page d’aide décrit le fonctionnement de « Pages introuvables » en tant que [dimension](overview.md). Voir la page de mesure [Pages introuvables](../metrics/pages-not-found.md) pour plus d’informations sur son fonctionnement en tant que mesure.*

>[!ENDSHADEBOX]

La dimension « Pages introuvables » indique les adresses URL qui contenaient une erreur. Cette dimension est utile lorsque vous souhaitez réduire le nombre d’erreurs rencontrées par les visiteurs et visiteuses sur votre site.

* Vous pouvez utiliser cette dimension dans une [visualisation de flux](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) pour identifier les pages sur lesquelles les visiteurs cliquent pour atteindre l’erreur. Vous pouvez ensuite travailler avec les équipes de développement de votre organisation pour corriger le lien sur chaque page.
* Vous pouvez utiliser cette dimension avec la dimension [Référent](referrer.md) pour déterminer la page de votre site sur laquelle les visiteurs arrivent depuis les liens externes. Vous pouvez ensuite mettre en œuvre des redirections vers l’emplacement souhaité ou travailler avec un tiers pour corriger le lien.

>[!NOTE]
>
>Dans Data Warehouse, cette dimension est nommée « Erreur de type de page [!UICONTROL &#x200B; »].

## Renseignement de cette dimension avec des données

AppMeasurement collecte ces données à l’aide de la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md). Lorsque `pageType` est défini sur `errorPage`, l’URL de page de l’accès est enregistrée en tant qu’élément de dimension. Si la variable `pageType` n’est pas définie ou est définie sur une autre valeur, aucune donnée n’est collectée pour cette dimension.

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`pageType`](/help/implement/vars/page-vars/pagetype.md) |
| **Champ Web SDK/XDM** | [`web.webPageDetails.isErrorPage`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Paramètre de requête** | [`pageType`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<pageType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | S.O. |
| **Persistance** | Hit |

## Éléments de dimension

Les éléments de dimension incluent les adresses URL des pages de votre site où une erreur s’est produite.
