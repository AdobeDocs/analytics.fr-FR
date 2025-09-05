---
description: Explique les préparatifs nécessaires pour préparer la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics.
title: Préparer la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics
feature: Admin Tools
exl-id: a9ff98dc-6568-428d-a8a8-faca5bc76a29
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 10%

---

# Préparer la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics

Avant que quiconque au sein de votre organisation ne commence à migrer les projets comme décrit dans [Migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](/help/admin/tools/component-migration/component-migration.md), renseignez les sections suivantes.

## Conditions préalables

Avant que vos projets et leurs composants associés ne soient prêts à migrer, vous devez d’abord suivre les étapes de la section [Évolution à partir d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=fr) du guide d’Adobe Customer Journey Analytics. Ces étapes sont les suivantes :

1. Utilisez l’une des méthodes suivantes pour ingérer des données dans Adobe Experience Platform afin d’afficher les données de suite de rapports Adobe Analytics dans Customer Journey Analytics :

   >[!NOTE]
   >
   >  Lorsque vous utilisez le SDK Web pour ingérer des données, tous les champs de schéma doivent être mappés manuellement. (Pour plus d’informations sur le processus de mappage, voir [ Migration de composants et de projets d’Adobe Analytics vers Customer Journey Analytics ](/help/admin/tools/component-migration/component-migration.md))


   * Pour utiliser le connecteur source Adobe Analytics, vous devez effectuer les opérations suivantes :

      1. [Configurer des suites de rapports pour l’ingestion dans Adobe Experience Platform et Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [ Ingérer et utiliser les données ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=fr)

   * Pour utiliser le SDK Web, vous devez effectuer les opérations suivantes :

      1. [Configurer des suites de rapports pour l’ingestion dans Adobe Experience Platform et Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Ingestion de données via Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html)

1. Créez une [connexion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html) et [vue de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr) avec les données ingérées.

1. Assurez-vous que les utilisateurs et utilisatrices de Customer Journey Analytics disposent des privilèges d’accès aux vues de données où les données sont mappées.

   Pour plus d’informations, voir [Autorisations Customer Journey Analytics dans Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html#customer-journey-analytics-permissions-in-admin-console) dans [Contrôle d’accès Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

   L’onglet Autorisations fait partie de chaque profil de produit dans Admin Console. Vous pouvez ajouter des utilisateurs à des profils de produit spécifiques. Ensuite, vous attribuez des droits à des vues de données spécifiques et spécifiez les autorisations dont disposent les utilisateurs dans un profil de produit.

1. En tant qu’organisation, décidez de la manière dont vous allez mapper les composants.

   Pour plus d’informations, consultez la section ci-dessous, [Décider en tant qu’organisation de la manière dont vous allez mapper les composants](#decide-as-an-organization-how-you-will-map-components).

## Comprendre ce qui est inclus dans une migration

Les tableaux suivants décrivent les éléments d’un projet et d’un composant qui sont inclus dans une migration :

### Éléments de composant migrés

Les dimensions et les mesures sont migrées dans le cadre du processus de mappage décrit dans [Migration de projets Adobe Analytics vers Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics).

Les segments, périodes et mesures calculées qui n’existent pas encore dans Customer Journey Analytics y sont recréés en fonction des dimensions et des mesures mappées.

|  | Migré |
|---------|---------|
| **[Propriétaire](/help/components/calculated-metrics/workflow/cm-manager.md)** | Dimensions et mesures : Non<p>Segments et périodes : ![coche](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Partage](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensions et mesures : Non<p>Segments et périodes : non</p> |
| **[Descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimensions et mesures : Non<p>Segments et périodes : ![coche](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Balises](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensions et mesures : Non<p>Segments et périodes : non</p> |
| **[Attribution (sur les dimensions)](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimensions et mesures : Non<p>Segments et périodes : non</p> |

{style="table-layout:auto"}

### Éléments de projet migrés

|  | Migré |
|---------|----------|
| **[Périodes](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |
| **[Segments](/help/components/segmentation/seg-overview.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |
| **[Segments rapides](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |
| **[Dimensions](/help/components/dimensions/overview.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) Mappé automatiquement ou manuellement |
| **[Mesures](/help/components/metrics/overview.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) Mappé automatiquement ou manuellement |
| **[Panneaux](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |
| **[Visualisations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |
| **[Propriétaire](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) Définie par l’utilisateur effectuant la migration |
| **[Traitement](/help/analyze/analysis-workspace/curate-share/curate.md)** | Non |
| **[Partage](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | Non |
| **[Annotations](/help/analyze/analysis-workspace/components/annotations/overview.md)** | Non |
| **[Structure des dossiers](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | Non |
| **[Descriptions](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |
| **[Balises](/help/analyze/landing.md)** | Non |
| **[Favoris](/help/analyze/landing.md)** | Non |
| **[Horaires](/help/components/scheduled-projects-manager.md)** | Non |
| **[Détection des anomalies](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## Comprendre les éléments non pris en charge qui provoquent des erreurs

Les visualisations et panneaux suivants ne sont pas pris en charge dans Customer Journey Analytics. Lorsque ces éléments sont inclus dans un projet avant la migration, ils peuvent entraîner l’échec de la migration ou des erreurs une fois le projet migré.

Supprimez ces éléments du projet Adobe Analytics avant de migrer le projet vers Customer Journey Analytics. En cas d’échec de la migration, supprimez ces éléments avant de réessayer.

### Visualisations non prises en charge

* [Carte](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

### Panneaux non pris en charge

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [Comparaison des segments](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [Audience moyenne par minute de média](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [Élément suivant ou précédent](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [Résumé de la page](/help/analyze/analysis-workspace/c-panels/page-summary.md)

* [Analyse des contributions](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)

## En tant qu’organisation, décidez de la manière de mapper les composants

>[!IMPORTANT]
>
>Le processus de migration identifie les composants de votre projet Adobe Analytics qui ne peuvent pas être automatiquement mappés aux composants dans Customer Journey Analytics. Il vous permet également de les mapper manuellement.
>
>**Les mappages effectués sur un projet s’appliquent à tous les projets futurs de l’ensemble de votre organisation IMS, quel que soit l’utilisateur ou l’utilisatrice qui effectue la migration. Ces mappages ne peuvent pas être modifiés ou annulés, sauf en contactant l’assistance clientèle.**
>
>C’est pourquoi il est important que votre organisation décide de la manière dont les dimensions et les mesures seront mappées avant la migration des projets. Cela permet d’éviter que des administrateurs individuels prennent des décisions en silo lorsqu’ils ne prennent en compte qu’un seul projet.
>
>Voici une liste des dimensions et des mesures que vous devez mapper manuellement si elles existent dans votre projet. Nous vous recommandons de consulter cette liste avant votre migration. Si l’un de ces composants existe dans votre projet, décidez maintenant à quels composants Customer Journey Analytics vous allez les mapper.


### Dimensions qui doivent être mappées manuellement

* averagepagetime
* pagetimeseconds
* singlepagevisits
* visitnumber
* timeprior
* timespent
* category
* connectiontype
* customerloyalty
* customlink
* downloadlink
* exitlink
* hitdepth
* hittype
* pathlength
* daysbeforefirstpurchase
* dayssincelastpurchase
* dayssincelastvisit
* identificationstate
* optoutreason
* persistentcookie
* returnfrequency
* searchenginenatural
* searchenginenaturalkeyword
* mobilecarrier
* monitorresolution
* surveybase
* mcaudiences
* tntbase
* targetraw


### Mesures qui doivent être mappées manuellement

* timespentvisit
* timespentvisitor
* rechargements
* bounces
* rebondir
* pageevents
* pageviewspervisit
* orderspervisit
* averagepagedepth
* averagetimespentonsite
* exitlinkinstances
* customlinkinstances
* downloadlinkinstances
* visiteurs sombres
* singlepagevisits
* singlevaluevisits
* visitorhomepage
* visitorsmcvisid
* pagesnotfound
* nouveaux engagements
* time_granularity
* concurrent_viewers_visitor
* concurrent_viewers_occurrence
* périphériques
* personnes estimées
* playback_time_spent_seconds
* playback_time_spent_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* targetconversion
* target timpression
