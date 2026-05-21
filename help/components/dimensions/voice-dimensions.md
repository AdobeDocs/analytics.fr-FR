---
title: Dimensions de l’analyse vocale
description: Dimensions de l’analyse vocale
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
TQID: https://experienceleague.adobe.com/OZ-lQkbS8hsv8ywUUa2BQoH40nfklRkJNd9SlEVkmEI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 133
ht-degree: 16%

---

# Dimensions de l’analyse vocale

Lorsque vous activez [!UICONTROL Voix et robots de conversation] dans [[!UICONTROL Rapports d’application]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), les dimensions (et [mesures](../metrics/voice-metrics.md) suivantes sont créées. Vous pouvez utiliser des [variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) pour les définir sur la valeur de chaîne souhaitée. Lorsqu’elles sont activées dans les paramètres de la suite de rapports, les [&#x200B; Règles de traitement &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) sont automatiquement créées pour mapper les dimensions d’analyse vocale à la variable de données contextuelles qui leur est associée.

| Nom de la dimension | Description | Variable de données contextuelles |
| --- | --- | --- |
| Voix – Type d’erreur | Type d’erreur rencontrée. | `a.voiceerrortype` |
| Voix – Langue | Langue dans laquelle l’utilisateur interagit avec votre application vocale. | `a.voicelanguage` |
| Voix – Intention | Commande que l’utilisateur a l’intention d’exécuter. | `a.voiceintent` |
| Voix – Réponse de l’application | Réponse que l’application vocale a renvoyée à l’utilisateur. | `a.voiceappresponse` |
| Voix – Authentification | État d’authentification de l’utilisateur lors de l’interaction avec l’application vocale. | `a.voiceauthentication` |
| ID de point d’intérêt | ID du point ciblé. | `a.loc.poi.id` |

{style="table-layout:auto"}
