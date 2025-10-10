---
title: Mesures d’analyse vocale
description: Mesures d’analyse vocale
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '102'
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
