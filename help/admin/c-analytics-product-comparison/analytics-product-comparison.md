---
description: Cette rubrique présente la configuration système requise et compare Analysis Workspace, les Reports & Analytics, les Ad Hoc Analysis, le Report Builder, Data Warehouse et Data Workbench.
title: Configuration requise et comparaison des produits Analytics
translation-type: tm+mt
source-git-commit: 8a48a5bd9e7ef38ffc90ecb9c640166bb3ac4405
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 53%

---


# Analytics Configuration requise et comparaison des produits

Cette page contient une comparaison de divers produits Adobe Analytics : analysis workspace, Rapports et analyses, Report Builder, Data Warehouse, Data Workbench, Flux de données et API Analytics 2.0.

Pour savoir quel produit Adobe Analytics utiliser, accédez à ce [lien](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nom du produit et lien d’aide | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/home.html) | [Flux de données](/help/export/analytics-data-feed/data-feed-overview.md) | [API Analytics 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Méthode d&#39;accès** | [Navigateur](/help/admin/sys-reqs.md) | [Navigateur](/help/admin/sys-reqs.md) | [MS Excel pour Windows](/help/analyze/report-builder/setup/system-requirements.md) | Configuration via le navigateur. [En savoir plus](/help/admin/sys-reqs.md) | [Windows 64 bits](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/install/c-data-workbench-client-install.html) | Configuration via le navigateur. [En savoir plus](/help/export/analytics-data-feed/data-feed-overview.md) | Outils d’API RESTful. Connectez-vous avec les informations d&#39;identification d&#39;E/S d&#39;Adobe. [En savoir plus](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Granularité des données** | Agrégé | Agrégé | Agrégé | Agrégé | Accès | Accès | Agrégé |
| **ID d’Experience Cloud (ECID) disponible** | Non | Non | Non | Oui | Oui | Oui | Non |
| **Horodatage disponible** | Non | Non | Non | Non | Oui | Oui | Non |
| **Niveau de traitement** | Traitement complet | Traitement complet, avec rapport [en temps réel distinct](/help/components/c-real-time-reporting/realtime.md) | Traitement complet, avec rapport [en temps réel distinct](/help/components/c-real-time-reporting/realtime.md) | Traitement complet | Traitement complet | Traitement complet | Traitement complet |
| **Données du filtre de robots d’administration incluses** <br> [En savoir plus](/help/admin/admin/bot-removal/bot-removal.md) | Non | Oui - rapport de robots distinct | Oui - rapport de robots distinct | Non | Non | Non | Non |
| **Le faible trafic (valeurs uniques dépassées) apparaît.** <br> [En savoir plus](/help/technotes/low-traffic.md) | Oui | Oui | Oui | Non | Non | Non | Oui |
| **Limite des lignes visibles (avant pagination)** | 400 | 200 | 50000 | Illimitées | Illimitées | Illimitées | 50000 |
| **Plusieurs suites de rapports** | [Oui](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Oui, avec des limites | Oui | Non | Oui | Non | Oui |
| **Nombre de ventilations** | Illimitées | Jusqu’à 2 | Jusqu’à 2 | Illimitées | Illimitées | Illimitées | Illimité, exécuté sur plusieurs requêtes |
| **Segmentation** <br> [En savoir plus](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Oui | Oui | Oui | Oui, avec [restrictions](/help/components/segmentation/seg-reference/seg-compatibility.md) | Oui | Non | Oui |
| **Mesures calculées** <br> [En savoir plus](/help/components/c-calcmetrics/cm-overview.md) | Oui, avec [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Oui | Oui | Non | Oui | Non | Oui, avec [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canaux marketing** <br> [En savoir plus](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Oui | Oui | Oui | Oui | Oui | Oui - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Oui |
| **Analyse de cohortes** | [Oui](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Non | Non | Non | Oui | Non | Non |
| **Attribution** | Oui, avec [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Limited | Limited | Non | Oui | Non | Oui, avec [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Fonctionnalités de Virtual Analyst** <br> [En savoir plus](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | Oui | Non | Non | Non | Non | Non | Oui |
| **Traitement** <br> [En savoir plus](/help/analyze/analysis-workspace/curate-share/curate.md) | Oui - Projet et suite de rapports virtuelle | Non | Non | Non | Non | Non | Oui - VRS uniquement |
| **Partage de projet** <br> [En savoir plus](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Oui, avec des rôles de projet | Oui | Oui | Non | Oui | Non | Non |
| **Livraison planifiée** | Oui | Oui | Oui | Oui | Non | Oui | Non |
| **Destinations des diffusions** | Courriel  | Courriel  | Courrier électronique, FTP, SFTP, [publication sur Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | Courriel, FTP. Contactez le service à la clientèle pour obtenir une prise en charge de destination supplémentaire, notamment SFTP, Azure Blob, Amazon S3 | - | FTP, SFTP, Azure Blob, Amazon S3 | - |
| **Traitement du temps de rapport VRS** <br> [En savoir plus](/help/components/vrs/vrs-report-time-processing.md) | Oui | Non | Non | Non | Non | Non | Oui |
