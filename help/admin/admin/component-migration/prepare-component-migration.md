---
description: Explique les préparatifs nécessaires à la préparation de la migration des composants et projets d’Adobe Analytics vers Customer Journey Analytics.
title: Préparation à la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics
feature: Admin Tools
source-git-commit: cbd991821dc1eefa458ec5d92b75f9b4dfcc9fa0
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 15%

---

# Préparation à la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics

Avant que quiconque au sein de votre entreprise ne commence la migration des projets, comme décrit dans [Migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md), complétez les sections suivantes.

## Conditions préalables

Avant que vos projets et les composants associés ne soient prêts à migrer, vous devez d’abord :

* Utilisez l’une des méthodes suivantes pour ingérer des données dans Adobe Experience Platform afin d’afficher les données de la suite de rapports Adobe Analytics dans Customer Journey Analytics :

  >[!NOTE]
  >
  >  Lorsque vous utilisez le WebSDK pour ingérer des données, tous les champs de schéma doivent être mappés manuellement. (Pour plus d’informations sur le processus de mappage, voir [Migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md))


   * Pour utiliser le connecteur source Adobe Analytics, vous devez :

      * [Configuration de suites de rapports pour l’ingestion dans Adobe Experience Platform et Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      * [Ingérer et utiliser les données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=fr)

   * Pour utiliser le WebSDK, vous devez :

      * [Configuration de suites de rapports pour l’ingestion dans Adobe Experience Platform et Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      * [Ingestion de données via le SDK Web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html)

* Créez un [connection](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html?lang=fr) et [vue des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr) avec les données ingérées.

* Assurez-vous que les utilisateurs de Customer Journey Analytics sont configurés pour les vues de données où les données sont mappées.

  Pour plus d’informations, voir [Autorisations du Customer Journey Analytics dans le Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Contrôle d’accès Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  L’onglet Autorisations fait partie de chaque profil de produit dans Admin Console. Vous pouvez ajouter des utilisateurs à des profils de produit spécifiques. Ensuite, vous attribuez des droits à des vues de données spécifiques et spécifiez les autorisations dont disposent les utilisateurs dans un profil de produits.

* Déterminez en tant qu’organisation comment mapper les composants.

  Pour plus d’informations, voir la section ci-dessous, [Déterminer en tant qu’organisation comment mapper des composants](#decide-as-an-organization-how-you-will-map-components).

## Comprendre ce qui est inclus dans une migration

Les tableaux suivants décrivent les éléments d’un projet et d’un composant qui sont inclus dans une migration :

### Éléments de composant migrés

Les Dimensions et les mesures sont migrées dans le cadre du processus de mappage décrit dans la section [Migration de projets Adobe Analytics vers Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics), tandis que les segments et les plages de dates sont recréés en Customer Journey Analytics en fonction de la variable

|  | Migré |
|---------|---------|
| **[Propriétaire](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | Dimensions et mesures : Non<p>Segments et plages de dates : ![coche](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Partage](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensions et mesures : Non<p>Segments et plages de dates : Non</p> |
| **[Descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimensions et mesures : Non<p>Segments et plages de dates : ![coche](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Balises](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensions et mesures : Non<p>Segments et plages de dates : Non</p> |
| **[Attribution (sur les dimensions)](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimensions et mesures : Non<p>Segments et plages de dates : Non</p> |

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
| **[Propriétaire](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) Défini par l’utilisateur effectuant la migration |
| **[Traitement](/help/analyze/analysis-workspace/curate-share/curate.md)** | Non |
| **[Partage](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | Non |
| **[Annotations](/help/analyze/analysis-workspace/components/annotations/overview.md)** | Non |
| **[Structure du dossier](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | Non |
| **[Descriptions](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |
| **[Balises](/help/analyze/landing.md)** | Non |
| **[Favoris](/help/analyze/landing.md)** | Non |
| **[Plannings](/help/components/scheduled-projects-manager.md)** | Non |
| **[Détection des anomalies](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## Comprendre les éléments non pris en charge qui provoquent des erreurs

Les visualisations, panneaux et fonctionnalités suivants ne sont pas pris en charge dans Customer Journey Analytics. Lorsque ces éléments sont inclus dans un projet avant la migration, ils peuvent entraîner l’échec de la migration ou entraîner des erreurs une fois le projet migré.

Supprimez ces éléments du projet Adobe Analytics avant de migrer le projet vers Customer Journey Analytics. Si une migration échoue, supprimez ces éléments avant de retenter la migration.

### Visualisations non prises en charge

* [Carte](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

### Panneaux non pris en charge

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [Comparaison des segments](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [Audience moyenne par minute de média](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [Élément suivant ou précédent](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [Résumé de la page](/help/analyze/analysis-workspace/c-panels/page-summary.md)

### Fonctionnalités non prises en charge

* [Analyse des contributions](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md)

* [Alertes](/help/components/c-alerts/intellligent-alerts.md)

## Déterminer en tant qu’organisation comment mapper des composants

>[!IMPORTANT]
>
>Le processus de migration identifie les composants de votre projet Adobe Analytics qui ne peuvent pas être automatiquement mappés à des composants dans Customer Journey Analytics et vous permet de les mapper manuellement.
>
>**Les mappages effectués sur un projet s’appliquent à tous les projets futurs de l’ensemble de votre organisation, quel que soit l’utilisateur qui effectue la migration. Ces mappages ne peuvent pas être modifiés ou annulés, sauf en contactant l’assistance clientèle.**
>
>C’est pourquoi il est important que votre entreprise décide de la manière dont les dimensions et les mesures seront mappées avant la migration de tous les projets. Cela évite aux administrateurs individuels de prendre des décisions dans un silo lorsqu’ils ne prennent en compte qu’un seul projet.
>
>Vous trouverez ci-dessous une liste de dimensions et de mesures que vous devez mapper manuellement si elles existent dans votre projet. Nous vous recommandons de consulter cette liste avant votre migration. Si l’un de ces composants existe dans votre projet, décidez maintenant à quels composants de Customer Journey Analytics vous allez les mapper.


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
* bouncerate
* pageevents
* pageviewspervisit
* orderspervisit
* averagepagedepth
* averagetimespentonsite
* exitlinkinstances
* customlinkinstances
* downloadlinkinstances
* darkvisiteurs
* singlepagevisits
* singlevaluevisit
* visitorhomepage
* visitorsmcvisid
* pagesnotfound
* nouvel engagement
* time_granularity
* concurrent_viewers_visitors
* concurrent_viewers_occurrences
* périphériques
* estimatedpeople
* playback_time_dépenser_seconds
* playback_time_used_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* targetconversion
* targetimpression