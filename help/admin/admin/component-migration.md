---
description: Explique comment migrer des composants et des projets d’Adobe Analytics vers Customer Journey Analytics.
title: Migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics
feature: Admin Tools
hide: true
hidefromtoc: true
source-git-commit: 792b2171c5535fcd3920b5cbb100b2fb7c642db8
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 7%

---

# Migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics

Les administrateurs Adobe Analytics peuvent migrer les projets Adobe Analytics et leurs composants associés vers Customer Journey Analytics.

Le processus de migration comprend :

* Recréation de projets Adobe Analytics dans Customer Journey Analytics.

* Mappage des dimensions et des mesures des suites de rapports Adobe Analytics aux dimensions et aux mesures dans les vues de données du Customer Journey Analytics.

  Certaines dimensions et mesures sont automatiquement mappées ; d’autres doivent être mappées manuellement dans le cadre du processus de migration. Les segments sont également migrés, mais il n’est pas nécessaire de les mapper dans le cadre du processus de migration.

  Tous les composants migrés s’affichent dans le résumé de migration une fois la migration terminée.

## Préparation d’une migration

Avant que toute personne de votre entreprise ne commence la migration de projets, suivez les sections suivantes.

### Conditions préalables

Avant que vos projets et les composants associés ne soient prêts à migrer, vous devez d’abord :

* Utilisez le connecteur source Analytics pour afficher les données de la suite de rapports Adobe Analytics dans Customer Journey Analytics. Pour ce faire, vous devez :

   * [Configuration de suites de rapports pour l’ingestion dans Adobe Experience Platform et Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [Ingérer et utiliser les données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=fr)

* Assurez-vous que les utilisateurs de Customer Journey Analytics sont configurés pour les vues de données où les données sont mappées.

  Pour plus d’informations, voir [Autorisations du Customer Journey Analytics dans le Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Contrôle d’accès Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  L’onglet Autorisations fait partie de chaque profil de produit dans Admin Console. Vous pouvez ajouter des utilisateurs à des profils de produit spécifiques. Ensuite, vous attribuez des droits à des vues de données spécifiques et spécifiez les autorisations dont disposent les utilisateurs dans un profil de produits.

* Créez un plan de migration, comme décrit dans la section ci-dessous, [Création d’un plan de migration en tant qu’organisation](#create-a-migration-plan-as-an-organization).

### Comprendre ce qui est inclus dans une migration

Les tableaux suivants décrivent les éléments d’un projet et d’un composant qui sont inclus dans une migration :

#### Éléments de composant migrés

|  | Migré |
|---------|---------|
| **[Propriétaire](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |
| **[Partage](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Non |
| **[Descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | ? |
| **[Balises](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Non |
| **[Attribution (sur les dimensions)](/help/analyze/analysis-workspace/attribution/overview.md)** | ? |

{style="table-layout:auto"}

#### Éléments de projet migrés

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
| **[Partage (rôles de projet)](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | Non |
| **[Partage (partager avec n’importe qui lien)](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | ? <!-- if no, combine with the above and just call it sharing? What about sharing links?--> |
| **[Annotations](/help/analyze/analysis-workspace/components/annotations/overview.md)** | Non |
| **[Structure du dossier](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | Non |
| **[Descriptions](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![coche](assets/Smock_Checkmark_18_N.svg) |
| **[Balises](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | Non |
| **[Plannings](/help/components/scheduled-projects-manager.md)** | Non |
| **[Détection des anomalies](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)** | ? |
| **[Favoris](/help/analyze/landing.md)** | ? |

{style="table-layout:auto"}

### Comprendre les éléments non pris en charge qui provoquent des erreurs

Les visualisations, panneaux et fonctionnalités suivants ne sont pas pris en charge dans Customer Journey Analytics. Lorsque ces éléments sont inclus dans un projet avant la migration, ils peuvent entraîner l’échec de la migration ou entraîner des erreurs une fois le projet migré.

Supprimez ces éléments du projet Adobe Analytics avant de migrer le projet vers Customer Journey Analytics. Si une migration échoue, supprimez ces éléments avant de retenter la migration.

#### Visualisations non prises en charge

* [Carte](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

#### Panneaux non pris en charge

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [Comparaison des segments](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [Audience moyenne par minute de média](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [Élément suivant ou précédent](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [Résumé de la page](/help/analyze/analysis-workspace/c-panels/page-summary.md)

#### Fonctionnalités non prises en charge

* [Analyse des contributions](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md)

* [Alertes](/help/components/c-alerts/intellligent-alerts.md)

### Création d’un plan de migration en tant qu’organisation

Puisque tous les composants mappés pour une migration de projet donnée s’appliquent à toute migration de projet future pour l’ensemble de l’organisation, il est important que votre organisation planifie toutes les migrations de projet à l’avance.

En tant qu’organisation, vous devez décider comment les dimensions et les mesures seront mappées. Cela évite aux administrateurs individuels de prendre des décisions dans un silo lorsqu’ils ne prennent en compte qu’un seul projet.

## Migration de projets Adobe Analytics vers Customer Journey Analytics

>[!IMPORTANT]
>
>Avant de migrer des projets vers Customer Journey Analytics comme décrit dans cette section, découvrez-en plus sur la migration des projets dans la section [Planification de la migration](#plan-the-migration) ci-dessus.
>
>Toutes les dimensions ou mesures que vous mappez sont permanentes, à la fois pour ce projet et pour tous les futurs projets migrés dans l’ensemble de votre organisation. Les mappages que vous effectuez ne peuvent pas être modifiés une fois la migration terminée.

1. Dans Adobe Analytics, sous l’onglet [!UICONTROL **Administration**] , sélectionnez [!UICONTROL **Tous les administrateurs**].

1. Sous [!UICONTROL **Configuration et collecte des données**], sélectionnez [!UICONTROL **Migration des composants**].

1. Localisez le projet que vous souhaitez migrer. Vous pouvez filtrer, trier ou rechercher la liste des projets.

   Par défaut, seuls les projets partagés avec vous sont affichés. Pour afficher tous les projets de votre entreprise, sélectionnez la variable **Filtrer** puis développez [!UICONTROL **Autres filtres**] et sélectionnez [!UICONTROL **Tout afficher**]. (Pour plus d’informations sur le filtrage, le tri et la recherche dans la liste des projets, voir [Filtrage, tri et recherche dans la liste des projets](#filter-sort-and-search-the-list-of-projects).)

1. Passez la souris sur le projet que vous souhaitez migrer, puis sélectionnez l’option **Migrer** icon ![Migration du projet](assets/migrate.svg).

   Ou

   Sélectionnez le projet que vous souhaitez migrer, puis sélectionnez [!UICONTROL **Migration vers Customer Journey Analytics**].

   Vous ne pouvez sélectionner qu’un seul projet à la fois pour la migration.

   La variable [!UICONTROL **Migration du nom du projet vers Customer Journey Analytics**] s’affiche.

   <!-- add screenshot -->

1. Dans le [!UICONTROL **Propriétaire du projet**] , commencez à saisir le nom de l’utilisateur que vous souhaitez définir comme propriétaire du projet dans Customer Journey Analytics, puis sélectionnez son nom dans le menu déroulant.

   Le propriétaire que vous spécifiez dispose de droits de gestion complets pour le projet.

1. Dans le [!UICONTROL **Schéma de mappage pour les suites de rapports**] , sélectionnez une suite de rapports.

1. Dans le [!UICONTROL **Vue des données**] dans le menu déroulant, sélectionnez la vue de données du Customer Journey Analytics dans laquelle vous souhaitez migrer le projet et les composants.

1. Sélectionner [!UICONTROL **Schéma de mappage**].

1. Dans le [!UICONTROL **Schéma de mappage**] , développez la section [!UICONTROL **Dimensions**] et [!UICONTROL **Mesures**] sections.

   Certaines dimensions et mesures dans Adobe Analytics sont automatiquement mappées à une dimension ou à une mesure dans Customer Journey Analytics. D’autres doivent être mappés manuellement.

   **Mappage automatique des dimensions et des mesures**

   Certaines dimensions et mesures dans Adobe Analytics sont automatiquement mappées à une dimension ou à une mesure dans Customer Journey Analytics. Vous ne pouvez pas prendre de décisions de mappage pour ces dimensions et mesures.

   Par exemple, la variable **Visites** dans Adobe Analytics est automatiquement mappée à l’objet **Sessions** en Customer Journey Analytics.

   Vous pouvez sélectionner n’importe quelle dimension ou mesure pour afficher les identifiants associés.

   <!-- update screenshot after I can see the Status column -->

   ![Schéma de migration de projet](assets/project-migration-schema.png)

   **Mappage manuel des dimensions et des mesures**

   Certaines dimensions et mesures dans Adobe Analytics ne peuvent pas être automatiquement mappées à une dimension ou à une mesure dans Customer Journey Analytics.

   Lorsqu’une dimension ou une mesure ne peut pas être automatiquement mappée, un compteur orange s’affiche en regard de la variable [!UICONTROL **Dimensions**] ou [!UICONTROL **Mesures**] en-tête de section, indiquant le nombre de dimensions ou de mesures à mapper manuellement. Dans le tableau, une icône d’avertissement ![icône d’avertissement](assets/schema-warning.png) s’affiche en regard de chaque dimension ou mesure à mapper manuellement.

   En outre, la variable [!UICONTROL **État**] column indique [!UICONTROL **Non mappé**].

   <!-- update screenshot after I can see the Status column -->

   ![Mappage manuel du schéma de migration](assets/schema-manual-map.png)

1. Pour mapper manuellement des dimensions et des mesures, sélectionnez une dimension ou une mesure contenant une icône d’avertissement. ![icône d’avertissement](assets/schema-warning.png), puis dans la variable [!UICONTROL **Mesure de Customer Journey Analytics mappée**] (ou la variable [!UICONTROL **Dimension de Customer Journey Analytics mappée**] si vous mappez une dimension), sélectionnez la dimension ou la mesure en Customer Journey Analytics à mapper à la dimension ou à la mesure sélectionnée.

   ![dimensions et mesures de mappage](assets/schema-manual-map-drop-down.png)

   Une fois qu’une dimension ou une mesure est mappée, l’icône d’avertissement disparaît et la variable [!UICONTROL **État**] modification de la colonne [!UICONTROL **Mappé**] avec un point vert. (Un état de [!UICONTROL **Mappé**] avec un point gris indique que la dimension ou la mesure a été mappée lors d’une migration précédente ; les mappages précédents ne peuvent pas être mis à jour.)

   Répétez cette procédure pour chaque dimension ou mesure contenant l’icône d’avertissement.

   Une fois que toutes les dimensions et mesures de la suite de rapports Adobe Analytics sont mappées à une dimension ou à une mesure dans la vue de données du Customer Journey Analytics, une coche verte s’affiche. ![coche](assets/report-suite-check.png) apparaît en regard du nom de la suite de rapports dans la variable [!UICONTROL **Schéma de mappage pour les suites de rapports**] .

1. (Conditionnel) Si le projet que vous migrez contient plusieurs suites de rapports, sélectionnez-en une autre dans la variable [!UICONTROL **Schéma de mappage pour les suites de rapports**] , puis répétez les étapes 6 à 10. <!-- double-check that the step numbers are still correct -->

1. Sélectionner [!UICONTROL **Migrer**].

   >[!WARNING]
   >
   >   Un message d’avertissement s’affiche après avoir sélectionné [!UICONTROL **Migrer**]. Avant de choisir de continuer, vous devez comprendre que toutes les dimensions ou mesures que vous mappez sont permanentes, à la fois pour ce projet et pour tous les projets futurs migrés dans l’ensemble de l’organisation. Si vous continuez, les mappages que vous effectuez ne peuvent pas être modifiés.

   Une fois la migration terminée, la variable [!UICONTROL **État de migration**] fournit un résumé de ce qui a été migré.

   Si la migration échoue, voir la section [Réessayer une migration ayant échoué](#retry-a-failed-migration) pour plus d’informations.

## Réessayer une migration ayant échoué

Si une migration échoue, vous pouvez effectuer une nouvelle tentative.

Vous pouvez réessayer une migration ayant échoué de l’une des façons suivantes :

>[!NOTE]
>
>Si la migration continue d’échouer après une nouvelle tentative, contactez l’assistance clientèle avec l’identifiant de projet. L’ID de projet est accessible sur la page État de la migration. <!-- when does this page display? How can they get there -->

1. Dans Adobe Analytics, sous l’onglet [!UICONTROL **Administration**] , sélectionnez [!UICONTROL **Tous les administrateurs**].

1. Sous [!UICONTROL **Configuration et collecte des données**], sélectionnez [!UICONTROL **Migration des composants**].

1. Sélectionner [!UICONTROL **En échec**] dans le [!UICONTROL **État de migration**] en regard du projet que vous souhaitez réessayer.

   ![échec de la colonne d’état de migration](assets/migration-failed.png)

   La variable [!UICONTROL **État de migration**] s’affiche.

   Cette page s’affiche également immédiatement après l’exécution des étapes de migration décrites dans la section . [Migration de projets Adobe Analytics vers Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) ci-dessus.

1. Sélectionner [!UICONTROL **Réessayer la migration**].

## Filtrage, tri et recherche dans la liste des projets

Vous pouvez filtrer, trier et rechercher la liste des projets sur la page de migration des composants.

### Filtrage de la liste des projets

Vous pouvez filtrer selon les critères suivants :

| Filtre | Description |
|---------|----------|
| [!UICONTROL **Statut**] | L’état de la migration : <ul><li>[!UICONTROL **Pas démarré**]</li><li>[!UICONTROL **Commencé**]</li><li>[!UICONTROL **Terminé**]</li><li>[!UICONTROL **Échec**]</li></ul>. |
| [!UICONTROL **Balises**] | Sélectionnez une balise dans la liste des balises. Seuls les projets auxquels sont appliquées les balises sélectionnées sont affichés. |
| [!UICONTROL **Suite de rapports**] | Sélectionnez une suite de rapports dans la liste des suites de rapports. Seuls les projets qui utilisent les suites de rapports sélectionnées s’affichent. |
| [!UICONTROL **Propriétaires**] | Sélectionnez n’importe quel propriétaire dans la liste des propriétaires. Seuls les projets appartenant aux utilisateurs que vous sélectionnez s’affichent. |
| [!UICONTROL **Autres filtres**] | Les filtres supplémentaires suivants sont disponibles : <ul><li>[!UICONTROL **Mine**]: affiche uniquement les projets pour lesquels vous êtes défini comme propriétaire.</li><li>[!UICONTROL **Partagé avec moi**]: affiche uniquement les projets qui ont été partagés avec vous.</li><li>[!UICONTROL **Favoris**]: affiche uniquement les projets marqués comme favoris. (Vous pouvez marquer un projet comme favori dans le [page d’entrée du projet](/help/analyze/landing.md).)</li><li>[!UICONTROL **Mensuel**]</li><li>[!UICONTROL **Annuel**]</li></ul> |

{style="table-layout:auto"}

### Tri de la liste des projets

Vous pouvez trier la liste des projets selon n’importe quelle colonne.

Pour trier la liste des projets :

1. Sélectionnez l’en-tête de colonne de la colonne à trier.

1. (Facultatif) Sélectionnez à nouveau le même en-tête de colonne pour inverser l’ordre de tri.

### Recherche d’un projet

Vous pouvez rechercher la liste des projets dans la page de migration des composants pour trouver le projet que vous souhaitez migrer.

1. Dans le champ de recherche situé en haut de la page Migration des composants, commencez à saisir le nom du projet que vous souhaitez migrer.

1. Sélectionnez le projet lorsqu’il apparaît dans le menu déroulant.

<!-- is there going to be a way to customize the columns that are displayed? -->
