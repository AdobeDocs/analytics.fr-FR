---
description: Cette rubrique présente la configuration système requise et compare Analysis Workspace, les Reports & Analytics, les Ad Hoc Analysis, le Report Builder, Data Warehouse et Data Workbench.
title: Configuration requise et comparaison des produits Analytics
translation-type: tm+mt
source-git-commit: 9265fb410b20a764ecc86c56b453b045122fcd05
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 73%

---


# Analytics Configuration requise et comparaison des produits 

Configuration système requise et comparaison de l’espace de travail des Analyses, des rapports et analyses, des Analyses ad hoc, du créateur de rapports, de l’entrepôt de données et des outils de données.

Pour savoir quel produit Adobe Analytics utiliser, accédez à ce [lien](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nom du produit et lien d’aide | [Analysis Workspace](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/reports-analytics/getting-started.html) | [Ad Hoc Analysis](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/ad-hoc-analysis/adhoc-home.html) | [Report Builder](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/fr-FR/analytics/export/data-warehouse/data-warehouse.translate.html) | [Data Workbench](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/home.html) |
|---|---|---|---|---|---|---|
| **Méthode d’accès** | Solution de navigateur pour créer des projets d’analyse personnalisés et fiables, et démocratiser les informations. | Solution de navigateur pour les analyses digitales. | Outil Java pour des analyses digitales avancées. | Module complémentaire Excel qui permet de créer des requêtes personnalisées à partir des Reports &amp; Analytics et de les visualiser à l’aide de Microsoft Excel. | Solution de navigateur qui génère des rapports au format .csv. Peut générer des fichiers de format Tableau. | Outil d’analyse multicanal pour des analyses avancées, comme la modélisation d’attribution personnalisée, l’analyse prédictive et l’analyse client avec vue à 360 degrés. |
| **Ventilations des rapports** | Illimitées | Jusqu’à 2 corrélations | Illimitées | Jusqu’à 2 corrélations | Effectue des ventilations illimitées entièrement étendues (ventilation par segment). | Illimitées |
| **Comparaisons des segments** | Illimitées | Jusqu’à 2 segments | Illimitées | Illimitées (empilement des requêtes de données) | 1 segment. Prise en charge de plusieurs segments (empilés). | Illimitées |
| **Limite de sortie des lignes** | 400 | 200 | 50 000 | 50 000 | Illimitées | Personnalisable |
| **** Limites de valeur unique (dans les rapports d’eVar/de prop) | 500 K-2 millions | 500 K-2 millions | 500 K-2 millions | 500 K-2 millions | Illimitées | Personnalisable |
| **Entonnoir/cheminement** | Oui : [Abandon](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)/[flux](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/visualizations/flow/flow.html) | [Oui](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/reports.html) | [Oui](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-reports-paths.html) | Oui | Non | Oui |
| **Analyse avancée du parcours client** | Yes: [Customer Journey Analytics](https://docs.adobe.com/content/help/fr-FR/analytics-platform/using/cja-landing.html) | Non | Oui | Non | Non | Oui |
| **Analyse des cohortes** | [Oui](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | Non | Non | Non | Non | Oui |
| **Attribution avancée** | [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution-iq.html) | Limitée - premier/dernier/linéaire | Limitée - premier/dernier/linéaire | Limitée - premier/dernier/linéaire | Limitée - premier/dernier/linéaire | Oui |
| **Options de visualisation améliorées** | [Oui](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) | Non | Oui | Oui | Non | Oui |
| **Mise en page personnalisable** | [Oui](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html) | Oui - [Tableaux de bord](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/dashboard.html) | Non | [Oui](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/configure-the-custom-layout.html) | Tri des résultats par ventilation ou mesure. | Oui |
| **** Traitement des projets (simplifie les rapports pour les personnes qui ne sont pas analystes) | [Oui](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/curate.translate.html) | Non | Non | Oui | Non | Oui |
| **Partage des projets** | [Oui : tous/n’importe quel utilisateur](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/curate.translate.html) | [Oui : tous/n’importe quel utilisateur](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html) | Uniquement avec les utilisateurs des Ad Hoc Analysis | Oui : tous/n’importe quel utilisateur | Non | Oui |
| **Diffusion de rapports** planifiée | [Oui](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/schedule-projects.html) | [Oui](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html) | [Oui](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-schedule.html) | [Oui](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/t-schedule-a-data-request.html) | Oui | Oui |
| **Configuration système requise** | <br>[BrowserMore...](https://docs.adobe.com/content/help/fr-FR/analytics/admin/sys-reqs.html) | <br>[BrowserMore...](https://docs.adobe.com/content/help/fr-FR/analytics/admin/sys-reqs.html) | <br>[JavaPlus...](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-getting-started.html) | Windows, MS<br>[ExcelPlus...](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | Navigateur et programme pour ouvrir des fichiers  .csv (MS Excel, par exemple). Peut générer des fichiers de format Tableau. | Windows 64 bit, good graphics adapter for OpenGL 3.2 [More...](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html) |
| **Compatibilité de la suite de rapports virtuelle (traitement du temps de rapport)** | Oui | Oui | Oui | Oui | Non | Oui? |
| **Suites de rapports multiples** | Oui | Non | Non | Non | Non | Oui? |
| **Mesures calculées** | Oui | Oui | Oui | Oui | Oui | Oui |
| **Compatibilité des Canaux marketing** | Oui | Oui | Oui | Oui | ? | ? |
| **Niveau de granularité** |  |  |  |  |  |  |
| **Détection des anomalies** | Oui | Non |  |  |  |  |
| **Analyse des contributions** | Oui | Non | Non | Non | Non | Oui |
| **Types de segment** |  |  |  |  |  |  |