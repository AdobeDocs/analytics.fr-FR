---
description: Ressources et liens relatifs à l’API de création de rapports.
title: API de création de rapports dans Analytics
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 90%

---

# API de création de rapports dans Analytics

La documentation des API Adobe Analytics se trouve sur [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Comparaison des API Analytics

| **Type d’API** | **Traitement complet** | **Temps réel** | **Livestream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **Description** | Données finalisées intégralement traitées disponibles dans toutes les interfaces d’Analytics. | Mesures limitées partiellement traitées disponibles quelques secondes après la collecte. | Données d’accès partiellement traitées disponibles quelques secondes après la collecte. | Données finalisées entièrement traitées utilisées pour l’extraction d’exportations volumineuses de données. |
| [**Latence**](/help/technotes/latency.md) | 30-90 minutes | Secondes -10 minutes | Secondes -10 minutes | + 90 minutes |
| **Traitement** | Complet | Partiel | Partiel | Complet |
| **Interfaces de création de rapports** | Analysis Workspace, Report Builder, API | Rapport en temps réel dans l’API Report Builder 1.4 | API seulement | Data Warehouse, API |
| **Granularité des données** | Récapitulatif | Récapitulatif | Au niveau des accès | Récapitulatif |
| **Traitement du profil du visiteur** | Oui | Non | Non | Oui |
| **Prise en charge des segments** | Oui | Non | Non | Partiel |
