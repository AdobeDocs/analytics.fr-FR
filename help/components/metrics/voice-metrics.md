---
title: Mesures d’analyse vocale
description: Mesures d’analyse vocale
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
TQID: https://experienceleague.adobe.com/snDtqM3TiX--cjPjKj8cGkaFxMIxRprvD4ia9OnBXJk
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
source-wordcount: 102
ht-degree: 21%

---

# Mesures d’analyse vocale

Lorsque vous activez [!UICONTROL Voix et robots de conversation] dans [[!UICONTROL Rapports d’application]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), les mesures (et [dimensions](../dimensions/voice-dimensions.md) suivantes sont créées. Vous pouvez utiliser [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) pour les définir sur une valeur de `1` (ou plus le cas échéant). Lorsqu’elles sont activées dans les paramètres de la suite de rapports, les [&#x200B; Règles de traitement &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) sont automatiquement créées pour mapper les mesures d’analyse vocale à la variable de données contextuelles qui leur est associée.

| Nom de la mesure | Description | Variable de données contextuelles |
| --- | --- | --- |
| Énoncés vocaux | Se déclenche lorsqu’une commande est envoyée à un assistant vocal. | `a.voiceutterances` |
| Fin de session vocale | Se déclenche lorsque l’application vocale est fermée. | `a.voiceendsession` |
| Erreur vocale | Se déclenche lorsque l’application vocale rencontre une erreur. | `a.voiceerror` |

{style="table-layout:auto"}
