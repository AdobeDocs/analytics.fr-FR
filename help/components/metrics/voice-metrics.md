---
title: Mesures d’analyse vocale
description: Mesures d’analyse vocale
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: 6a229439c455389b88d5fe96a0366b8888809c02
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 21%

---

# Mesures d’analyse vocale

Lorsque vous activez [!UICONTROL Voix et Chatbots] sur [[!UICONTROL Rapports d’applications]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md), les mesures suivantes (et [dimensions](../dimensions/voice-dimensions.md)) sont créées. Vous pouvez utiliser des [variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) pour les définir sur une valeur de `1` (ou plus, le cas échéant). Lorsqu’elles sont activées dans les paramètres de la suite de rapports, les [règles de traitement](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) sont automatiquement créées pour mapper les mesures d’analyse vocale à la variable de données contextuelles qui leur est associée.

| Nom de la mesure | Description | Variable de données contextuelles |
| --- | --- | --- |
| Énoncés vocaux | Déclenche lorsqu’une commande est envoyée à un assistant vocal. | `a.voiceutterances` |
| Fin de session vocale | Déclenche lorsque l’application vocale est fermée. | `a.voiceendsession` |
| Erreur vocale | Déclenche lorsque l’application vocale rencontre une erreur. | `a.voiceerror` |

{style="table-layout:auto"}
