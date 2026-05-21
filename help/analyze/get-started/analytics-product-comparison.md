---
description: Configuration requise et comparaison d’Analysis Workspace, Report Builder, Data Warehouse et Data Workbench
title: Configuration requise et comparaison des produits Analytics
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
TQID: https://experienceleague.adobe.com/VQgK6DUSlz-UA3zk-Q18-QOAI5M6xfK7KqBYwW56j6w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: af53ada8-1b7d-4929-ac91-ac971dd20ec7
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e9cb007b-c8b7-4975-bc81-11a788c535fa
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 67%

---

# Configuration requise et comparaison des produits Analytics

Cette page contient une comparaison de divers produits Adobe Analytics : Analysis Workspace, Report Builder, Data Warehouse, Data Feeds and Analytics API 2.0.

Pour plus d’informations sur le produit Adobe Analytics à utiliser, voir [Quel outil Adobe Analytics dois-je utiliser ?](/help/analyze/get-started/which-analytics-tool.md).

| Nom du produit et lien d’aide | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Flux de données](/help/export/analytics-data-feed/data-feed-overview.md) | [API Analytics 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **Méthode d’accès** | [Navigateur](/help/analyze/get-started/sys-reqs.md) | [MS Excel pour Windows](/help/analyze/legacy-report-builder/setup/system-requirements.md) | Configuration via le navigateur. [En savoir plus](/help/analyze/get-started/sys-reqs.md) | Configuration via le navigateur. [En savoir plus](/help/export/analytics-data-feed/data-feed-overview.md) | Outils de l’API RESTful. Connectez-vous à l’aide des informations d’identification Adobe Developer. [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Granularité des données** | Agrégé | Agrégé | Agrégé | Accès | Agrégé |
| **Experience Cloud ID (ECID) disponible** | Non | Non | Oui | Oui | Non |
| **Horodatage disponible** | Non | Non | Non | Oui | Non |
| **Niveau de traitement** | Traitement complet | Traitement complet avec [rapport en temps réel](/help/admin/tools/manage-rs/edit-settings/realtime/realtime.md) distinct | Traitement complet | Traitement complet | Traitement complet |
| **Données de filtrage des robots d’administration incluses** <br> [En savoir plus](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) | Non | Oui - Rapport de robot distinct | Non | Non | Non |
| **Le faible trafic (valeurs uniques dépassées) apparaît** <br> [En savoir plus](/help/technotes/low-traffic.md) | Oui | Oui | Non | Non | Oui |
| **Limite des lignes visibles (avant pagination)** | 400 | 50000 | Illimitées | Illimitées | 50000 |
| **Suites de rapports multiples** | [Oui](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Oui | Non | Oui | Non |
| **Nombre de répartitions** | Illimitées | Jusqu’à 2 | Illimitées | Illimitées | Illimitées, appliquées à plusieurs requêtes |
| **Segmentation** <br> [En savoir plus](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Oui | Oui | Oui, avec des [limites](/help/components/segmentation/seg-reference/seg-compatibility.md) | Non | Oui |
| **Mesures calculées** <br> [En savoir plus](/help/components/calculated-metrics/cm-overview.md) | Oui, avec [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Oui, avec Attribution | Oui | Non | Oui, avec [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canaux marketing** <br> [En savoir plus](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Oui | Oui | Oui | Oui - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Oui |
| **Analyse des cohortes** | [Oui](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Oui | Non | Non | Non |
| **Attribution** | Oui, avec [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Limitées | Non | Non | Oui, avec [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Traitement** <br> [En savoir plus](/help/analyze/analysis-workspace/curate-share/curate.md) | Oui - Projet et suite de rapports virtuelle | Non | Non | Non | Oui - Suite de rapports virtuelle uniquement |
| **Partage des projets** <br> [En savoir plus](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Oui, avec des rôles de projet | Oui | Non | Non | Non |
| **Livraison planifiée** | Oui | Oui | Oui | Oui | Non |
| **Destinations des diffusions** | Courriel | Courriel, FTP, SFTP, [publication sur Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC et E-mail | Amazon S3, Azure RBAC, Azure SAS et Google Cloud Platform | - |
| **Traitement de la période de rapport de la suite de rapports virtuelle** <br> [En savoir plus](/help/components/vrs/vrs-report-time-processing.md) | Oui | Non | Non | Non | Oui |
| **Rapports géographiques et technologiques** | Oui <p>Utilise des valeurs intermédiaires plutôt que des champs de publication. La logique de premier accès de la visite est basée sur le `post_cust_hit_time_gmt` plutôt que sur le `visit_page_num=1`. Les résultats peuvent différer des autres outils si les modifications d’adresses IP en milieu de visite, les accès arrivent dans le désordre ou les visites dépassent les limites mensuelles.</p> | Oui <p>Utilise des valeurs intermédiaires plutôt que des champs de publication. La logique de premier accès de la visite est basée sur le `post_cust_hit_time_gmt` plutôt que sur le `visit_page_num=1`. Les résultats peuvent différer des autres outils si les modifications d’adresses IP en milieu de visite, les accès arrivent dans le désordre ou les visites dépassent les limites mensuelles.</p> | Oui <p>Utilise des valeurs de publication et des `visit_page_num=1` pour déterminer le premier accès de la visite. Applique la valeur du premier accès à tous les accès de la visite pour ces dimensions.</p> | Oui <p>Utilise des valeurs de publication et des `visit_page_num=1` pour déterminer le premier accès de la visite. Applique la valeur du premier accès à tous les accès de la visite pour ces dimensions.</p> | Oui <p>Utilise des valeurs intermédiaires plutôt que des champs de publication. La logique de premier accès de la visite est basée sur le `post_cust_hit_time_gmt` plutôt que sur le `visit_page_num=1`. Les résultats peuvent différer des autres outils si les modifications d’adresses IP en milieu de visite, les accès arrivent dans le désordre ou les visites dépassent les limites mensuelles.</p> |
