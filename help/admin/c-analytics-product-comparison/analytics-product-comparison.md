---
description: Cette rubrique présente la configuration système requise et compare Analysis Workspace, les Reports & Analytics, les, le Report Builder, Data Warehouse et Data Workbench.
title: Configuration requise et comparaison des produits Analytics
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 8f25dfefbc6fba1fb525d2e9e0fce654e21ef362
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 98%

---

# Configuration requise et comparaison des produits Analytics

Cette page contient une comparaison de divers produits Adobe Analytics : Analysis Workspace, Reports &amp; Analytics, Report Builder, Data Warehouse, Data Workbench, Data Feeds et API Analytics 2.0.

Pour savoir quel produit Adobe Analytics utiliser, accédez à ce [lien](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nom du produit et lien d’aide | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html?lang=fr) | [Flux de données](/help/export/analytics-data-feed/data-feed-overview.md) | [API Analytics 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Méthode d’accès** | [Navigateur](/help/admin/sys-reqs.md) | [Navigateur](/help/admin/sys-reqs.md) | [MS Excel pour Windows](/help/analyze/report-builder/setup/system-requirements.md) | Configuration via le navigateur. [En savoir plus](/help/admin/sys-reqs.md) | [Windows 64 bits](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=fr) | Configuration via le navigateur. [En savoir plus](/help/export/analytics-data-feed/data-feed-overview.md) | Outils de l’API RESTful. Connectez-vous à l’aide des informations d’identification Adobe Developer. [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Granularité des données** | Agrégé | Agrégé | Agrégé | Agrégé | Accès | Accès | Agrégé |
| **Experience Cloud ID (ECID) disponible** | Non | Non | Non | Oui | Oui | Oui | Non |
| **Horodatage disponible** | Non | Non | Non | Non | Oui | Oui | Non |
| **Niveau de traitement** | Traitement complet | Traitement complet avec [rapport en temps réel](/help/components/c-real-time-reporting/realtime.md) distinct | Traitement complet avec [rapport en temps réel](/help/components/c-real-time-reporting/realtime.md) distinct | Traitement complet | Traitement complet | Traitement complet | Traitement complet |
| **Données de filtrage des robots d’administration incluses** <br> [En savoir plus](/help/admin/admin/bot-removal/bot-removal.md) | Non | Oui - Rapport de robot distinct | Oui - Rapport de robot distinct | Non | Non | Non | Non |
| **Le faible trafic (valeurs uniques dépassées) apparaît** <br> [En savoir plus](/help/technotes/low-traffic.md) | Oui | Oui | Oui | Non | Non | Non | Oui |
| **Limite des lignes visibles (avant pagination)** | 400 | 200 | 50000 | Illimitées | Illimitées | Illimitées | 50 000 |
| **Suites de rapports multiples** | [Oui](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Oui, avec des limites | Oui | Non | Oui | Non | Oui |
| **Nombre de ventilations** | Illimitées | Jusqu’à 2 | Jusqu’à 2 | Illimitées | Illimitées | Illimitées | Illimitées, appliquées à plusieurs requêtes |
| **Segmentation** <br> [En savoir plus](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Oui | Oui | Oui | Oui, avec des [limites](/help/components/segmentation/seg-reference/seg-compatibility.md) | Oui | Non | Oui |
| **Mesures calculées** <br> [En savoir plus](/help/components/c-calcmetrics/cm-overview.md) | Oui, avec [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Oui | Oui | Non | Oui | Non | Oui, avec [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canaux marketing** <br> [En savoir plus](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Oui | Oui | Oui | Oui | Oui | Oui - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Oui |
| **Analyse des cohortes** | [Oui](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Non | Non | Non | Oui | Non | Non |
| **Attribution** | Oui, avec [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Limitées | Limitées | Non | Oui | Non | Oui, avec [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Fonctionnalités Virtual Analyst** <br> [En savoir plus](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | Oui | Non | Non | Non | Non | Non | Oui |
| **Traitement** <br> [En savoir plus](/help/analyze/analysis-workspace/curate-share/curate.md) | Oui - Projet et suite de rapports virtuelle | Non | Non | Non | Non | Non | Oui - Suite de rapports virtuelle uniquement |
| **Partage des projets** <br> [En savoir plus](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Oui, avec des rôles de projet | Oui | Oui | Non | Oui | Non | Non |
| **Livraison planifiée** | Oui | Oui | Oui | Oui | Non | Oui | Non |
| **Destinations des diffusions** | Courriel | Courriel | Courriel, FTP, SFTP, [publication sur Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | Courriel, FTP. Contactez l’assistance clientèle pour obtenir une prise en charge de destination supplémentaire, notamment SFTP, Azure Blob ou Amazon S3. | - | FTP, SFTP, Azure Blob, Amazon S3 | - |
| **Traitement du temps de rapport des suites de rapports virtuelles** <br> [En savoir plus](/help/components/vrs/vrs-report-time-processing.md) | Oui | Non | Non | Non | Non | Non | Oui |
