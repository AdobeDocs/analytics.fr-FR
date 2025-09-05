---
description: Configuration requise et comparaison d’Analysis Workspace, Report Builder, Data Warehouse et Data Workbench
title: Configuration requise et comparaison des produits Analytics
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 100%

---

# Configuration requise et comparaison des produits Analytics

Cette page contient une comparaison de divers produits Adobe Analytics : Analysis Workspace, Report Builder, Data Warehouse, Data Feeds and Analytics API 2.0.

Pour plus d’informations sur le produit Adobe Analytics à utiliser, voir [Quel outil Adobe Analytics dois-je utiliser ?](/help/analyze/get-started/which-analytics-tool.md).

| Nom du produit et lien d’aide | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Flux de données](/help/export/analytics-data-feed/data-feed-overview.md) | [API Analytics 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **Méthode d’accès** | [Navigateur](/help/analyze/get-started/sys-reqs.md) | [MS Excel pour Windows](/help/analyze/legacy-report-builder/setup/system-requirements.md) | Configuration via le navigateur. [En savoir plus](/help/analyze/get-started/sys-reqs.md) | Configuration via le navigateur. [En savoir plus](/help/export/analytics-data-feed/data-feed-overview.md) | Outils de l’API RESTful. Connectez-vous à l’aide des informations d’identification Adobe Developer. [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Granularité des données** | Agrégé | Agrégé | Agrégé | Accès | Agrégé |
| **Experience Cloud ID (ECID) disponible** | Non | Non | Oui | Oui | Non |
| **Horodatage disponible** | Non | Non | Non | Oui | Non |
| **Niveau de traitement** | Traitement complet | Traitement complet avec [rapport en temps réel](/help/admin/tools/manage-rs/edit-settings/realtime/realtime.md) distinct | Traitement complet | Traitement complet | Traitement complet |
| **Données de filtrage des robots d’administration incluses** <br> [En savoir plus](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) | Non | Oui - Rapport de robot distinct | Non | Non | Non |
| **Le faible trafic (valeurs uniques dépassées) apparaît** <br> [En savoir plus](/help/technotes/low-traffic.md) | Oui | Oui | Non | Non | Oui |
| **Limite des lignes visibles (avant pagination)** | 400 | 50000 | Illimitées | Illimitées | 50000 |
| **Suites de rapports multiples** | [Oui](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Oui | Non | Oui | Non | Oui |
| **Nombre de répartitions** | Illimitées | Jusqu’à 2 | Illimitées | Illimitées | Illimitées, appliquées à plusieurs requêtes |
| **Segmentation** <br> [En savoir plus](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Oui | Oui | Oui, avec des [limites](/help/components/segmentation/seg-reference/seg-compatibility.md) | Non | Oui |
| **Mesures calculées** <br> [En savoir plus](/help/components/calculated-metrics/cm-overview.md) | Oui, avec [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Oui, avec Attribution | Oui | Non | Oui, avec [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canaux marketing** <br> [En savoir plus](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Oui | Oui | Oui | Oui - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Oui |
| **Analyse des cohortes** | [Oui](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Oui | Non | Non | Non |
| **Attribution** | Oui, avec [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Limitées | Non | Non | Oui, avec [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Non |
| **Traitement** <br> [En savoir plus](/help/analyze/analysis-workspace/curate-share/curate.md) | Oui - Projet et suite de rapports virtuelle | Non | Non | Non | Oui - Suite de rapports virtuelle uniquement |
| **Partage des projets** <br> [En savoir plus](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Oui, avec des rôles de projet | Oui | Non | Non | Non |
| **Livraison planifiée** | Oui | Oui | Oui | Oui | Non |
| **Destinations des diffusions** | Courriel | Courriel, FTP, SFTP, [publication sur Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC et E-mail | Amazon S3, Azure RBAC, Azure SAS et Google Cloud Platform | - |
| **Traitement de la période de rapport de la suite de rapports virtuelle** <br> [En savoir plus](/help/components/vrs/vrs-report-time-processing.md) | Oui | Non | Non | Non | Oui |
