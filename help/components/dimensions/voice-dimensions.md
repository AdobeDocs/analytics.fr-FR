---
title: Dimensions de l’analyse vocale
description: Dimensions de l’analyse vocale
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
source-git-commit: 6a229439c455389b88d5fe96a0366b8888809c02
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 4%

---

# Dimensions de l’analyse vocale

Lorsque vous activez [!UICONTROL Voix et Chatbots] sur [[!UICONTROL Rapports d’applications]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md), les dimensions suivantes (et [mesures](../metrics/voice-metrics.md)) sont créées. Vous pouvez utiliser des [variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) pour les définir sur la valeur de chaîne souhaitée. Lorsqu’elles sont activées dans les paramètres de la suite de rapports, les [règles de traitement](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) sont automatiquement créées pour mapper les dimensions d’analyse vocale à la variable de données contextuelles qui leur est associée.

| Nom de la dimension | Description | Variable de données contextuelles |
| --- | --- | --- |
| Type d’erreur de voix | Type d’erreur rencontrée. | `a.voiceerrortype` |
| Langue de la voix | Langue dans laquelle l’utilisateur interagit avec votre application vocale. | `a.voicelanguage` |
| Intention de voix | La commande que l’utilisateur a l’intention d’exécuter. | `a.voiceintent` |
| Réponse de l’application vocale | Réponse renvoyée à l’utilisateur par l’application vocale. | `a.voiceappresponse` |
| Authentification vocale | État authentifié de l’utilisateur lors de l’interaction avec l’application vocale. | `a.voiceauthentication` |
| Identifiant du point ciblé | ID de point ciblé. | `a.loc.poi.id` |

{style="table-layout:auto"}
