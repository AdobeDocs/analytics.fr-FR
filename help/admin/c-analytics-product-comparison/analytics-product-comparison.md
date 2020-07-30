---
description: Cette rubrique présente la configuration système requise et compare Analysis Workspace, les Reports & Analytics, les Ad Hoc Analysis, le Report Builder, Data Warehouse et Data Workbench.
title: Configuration requise et comparaison des produits Analytics
translation-type: tm+mt
source-git-commit: 54d6b4c2993c5b0391b9243c76661db1da4087b8
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 53%

---


# Analytics Configuration requise et comparaison des produits 

Cette page contient une comparaison de divers produits Adobe Analytics : Analysis Workspace, Rapports et Analytics, Report Builder, Data warehouse, Data Workbench, Flux de données et API Analytics 2.0.

Pour savoir quel produit Adobe Analytics utiliser, accédez à ce [lien](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nom du produit et lien d’aide | [Analysis Workspace](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/reports-analytics/getting-started.html) | [Report Builder](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/fr-FR/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/home.html) | [Flux de données](https://docs.adobe.com/content/help/fr-FR/analytics/export/analytics-data-feed/data-feed-overview.html) | [API Analytics 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Méthode d&#39;accès** | [Navigateur](https://docs.adobe.com/content/help/fr-FR/analytics/admin/sys-reqs.html) | [Navigateur](https://docs.adobe.com/content/help/fr-FR/analytics/admin/sys-reqs.html) | [MS Excel pour Windows](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | Configuration via le navigateur. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/admin/sys-reqs.html) | [Windows 64 bits](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/install/c-data-workbench-client-install.html) | Configuration via le navigateur. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/export/analytics-data-feed/data-feed-overview.html) | Outils d’API RESTful. Connectez-vous avec les informations d&#39;identification d&#39;E/S d&#39;Adobe. [En savoir plus](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Granularité des données** | Agrégé | Agrégé | Agrégé | Agrégé | Accès | Accès | Agrégé |
| **ECID (Experience Cloud ID) disponible** | Non | Non | Non | Oui | Oui | Oui | Non |
| **Horodatage disponible** | Non | Non | Non | Non | Oui | Oui | Non |
| **Niveau de traitement** | Traitement complet | Traitement complet, avec rapport [en temps réel distinct](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | Traitement complet, avec rapport [en temps réel distinct](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | Traitement complet | Traitement complet | Traitement complet | Traitement complet |
| **Données du filtre de robots d&#39;administration incluses** <br>[En savoir plus](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html) | Non | Oui - rapport de robots distinct | Oui - rapport de robots distinct | Non | Non | Non | Non |
| **Faible trafic (valeurs uniques dépassées) apparaît** <br>[En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/technotes/low-traffic.translate.html) | Oui | Oui | Oui | Non | Non | Non | Oui |
| **Limite des lignes visibles (avant pagination)** | 400 | 200 | 50000 | Illimitées | Illimitées | Illimitées | 50000 |
| **Plusieurs suites de rapports** | [Oui](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) | Oui, avec des limites | Oui | Non | Oui | Non | Oui |
| **Nombre de ventilations** | Illimitées | Jusqu’à 2 | Jusqu’à 2 | Illimitées | Illimitées | Illimitées | Illimité, exécuté sur plusieurs requêtes |
| **Segmentation** <br>[En savoir plus](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) | Oui | Oui | Oui | Oui, avec [restrictions](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-compatibility.html) | Oui | Non | Oui |
| **Mesures** calculées <br>[En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/components/calculated-metrics/cm-overview.html) | Oui, avec [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | Oui | Oui | Non | Oui | Non | Oui, avec [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Canaux** marketing <br>[En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/components/marketing-channels/c-getting-started-mchannel.html) | Oui | Oui | Oui | Oui | Oui | Oui - [va_finder, va_closer](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html) | Oui |
| **analyse de cohortes** | [Oui](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | Non | Non | Non | Oui | Non | Non |
| **Attribution** | Oui, avec [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | Limited | Limited | Non | Oui | Non | Oui, avec [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Fonctionnalités** d&#39;analyste virtuel <br>[En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/virtual-analyst/overview.translate.html) | Oui | Non | Non | Non | Non | Non | Oui |
| **Traitement** <br>[En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/curate.html) | Oui - Projet et suite de rapports virtuelle | Non | Non | Non | Non | Non | Oui - VRS uniquement |
| **Partage** de projets <br>[En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Oui, avec des rôles de projet | Oui | Oui | Non | Oui | Non | Non |
| **Livraison planifiée** | Oui | Oui | Oui | Oui | Non | Oui | Non |
| **Destinations des Diffusions** | Courriel | Courriel | Courrier électronique, FTP, SFTP, [publication sur Microsoft PowerBI](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/publish-powerbi/power-bi.html) | Courriel, FTP. Contactez le service à la clientèle pour obtenir une prise en charge de destination supplémentaire, notamment SFTP, Azure Blob, Amazon S3 | - | FTP, SFTP, Azure Blob, Amazon S3 | - |
| **Traitement** du temps des rapports VRS <br>[En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/components/virtual-report-suites/vrs-report-time-processing.html) | Oui | Non | Non | Non | Non | Non | Oui |
