---
title: Dimensions de l’analyse vocale
description: Dimensions de l’analyse vocale
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 4%

---

# Dimensions de l’analyse vocale

Lorsque vous activez [!UICONTROL Voix et robots de conversation] dans [[!UICONTROL Rapports d’application]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md), les dimensions (et [mesures](../metrics/voice-metrics.md) suivantes sont créées. Vous pouvez utiliser des [variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) pour les définir sur la valeur de chaîne souhaitée. Lorsqu’elles sont activées dans les paramètres de la suite de rapports, les [ Règles de traitement ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) sont automatiquement créées pour mapper les dimensions d’analyse vocale à la variable de données contextuelles qui leur est associée.

| Nom de la dimension | Description | Variable de données contextuelles |
| --- | --- | --- |
| Type d’erreur vocale | Type d’erreur rencontrée. | `a.voiceerrortype` |
| Langage Vocal | Langue dans laquelle l’utilisateur interagit avec votre application vocale. | `a.voicelanguage` |
| Intention de la voix | Commande que l’utilisateur a l’intention d’exécuter. | `a.voiceintent` |
| Réponse de l’application vocale | Réponse que l’application vocale a renvoyée à l’utilisateur. | `a.voiceappresponse` |
| Authentification vocale | État d’authentification de l’utilisateur lors de l’interaction avec l’application vocale. | `a.voiceauthentication` |
| ID du point ciblé | ID du point ciblé. | `a.loc.poi.id` |

{style="table-layout:auto"}
