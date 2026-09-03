---
title: Pages introuvables (dimensions)
description: Adresses URL ayant renvoyé une erreur sur votre site.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 232
ht-degree: 73%

---

# Pages introuvables

*Cette page d’aide décrit le fonctionnement de « Pages introuvables » en tant que [dimension](overview.md). Voir la page de mesure [Pages introuvables](../metrics/pages-not-found.md) pour plus d’informations sur son fonctionnement en tant que mesure.*

La dimension « Pages introuvables » indique les adresses URL qui contenaient une erreur. Cette dimension est utile lorsque vous souhaitez réduire le nombre d’erreurs rencontrées par les visiteurs et visiteuses sur votre site.

* Vous pouvez utiliser cette dimension dans une [visualisation de flux](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) pour identifier les pages sur lesquelles les visiteurs cliquent pour atteindre l’erreur. Vous pouvez ensuite travailler avec les équipes de développement de votre organisation pour corriger le lien sur chaque page.
* Vous pouvez utiliser cette dimension avec la dimension [Référent](referrer.md) pour déterminer la page de votre site sur laquelle les visiteurs arrivent depuis les liens externes. Vous pouvez ensuite implémenter des redirections vers l’emplacement souhaité ou travailler avec un tiers pour corriger le lien.

>[!NOTE]
>
>Dans Data Warehouse, cette dimension est nommée « Erreur de type de page [!UICONTROL  »].

## Renseignement de cette dimension avec des données

Cette dimension récupère les données des [`pageType` chaînes de requête `g` à partir de ](/help/implement/validate/query-parameters.md) et dans les demandes d’image. Si la chaîne de requête `pageType` est égale à `errorPage`, la chaîne de requête `g` (URL de la page) est enregistrée. AppMeasurement collecte ces données à l’aide de la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md). Si la variable `pageType` n’est pas définie ou si elle est définie sur autre chose que `errorPage`, aucune donnée n’est collectée pour cette dimension.

## Éléments de dimension

Les éléments de dimension incluent les adresses URL des pages de votre site où une erreur s’est produite.
