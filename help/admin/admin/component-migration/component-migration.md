---
description: Explique comment migrer des composants et des projets d’Adobe Analytics vers Customer Journey Analytics.
title: Migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: 03c8b0e08ac524216d7d9383fa12751e573601ee
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 5%

---

# Migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics

Les administrateurs Adobe Analytics peuvent migrer les projets Adobe Analytics et leurs composants associés vers Customer Journey Analytics.

Le processus de migration comprend :

* La recréation de projets Adobe Analytics dans Customer Journey Analytics.

* Le mappage des dimensions et des mesures des suites de rapports Adobe Analytics à des dimensions et des mesures dans les vues de données de Customer Journey Analytics.

  Certaines dimensions et mesures sont automatiquement mappées ; d’autres doivent être mappées manuellement dans le cadre du processus de migration. Les segments sont également migrés, mais il n’est pas nécessaire de les mapper dans le cadre du processus de migration.

  Tous les composants migrés s’affichent dans le résumé de migration une fois la migration terminée.

## Préparation d’une migration

Avant de migrer des projets vers Customer Journey Analytics, découvrez-en plus sur la migration des projets dans la section [Préparation à la migration des composants et projets d’Adobe Analytics vers Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).

## Migration de projets Adobe Analytics vers Customer Journey Analytics

>[!IMPORTANT]
>
>Avant de migrer des projets vers Customer Journey Analytics comme décrit dans cette section, découvrez-en plus sur la migration des projets dans la section [Préparation à la migration des composants et projets d’Adobe Analytics vers Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).
>
>**Toutes les dimensions ou mesures que vous mappez sont permanentes, à la fois pour ce projet et pour tous les projets futurs migrés dans l’ensemble de votre organisation IMS, quel que soit l’utilisateur qui effectue la migration. Ces mappages ne peuvent pas être modifiés ou annulés, sauf en contactant l&#39;assistance clientèle.**

1. Dans Adobe Analytics, sous l’onglet [!UICONTROL **Administration**] , sélectionnez [!UICONTROL **Tous les administrateurs**].

1. Sous [!UICONTROL **Configuration et collecte de données**], sélectionnez [!UICONTROL **Migration des composants**].

1. Localisez le projet que vous souhaitez migrer. Vous pouvez filtrer, trier ou rechercher la liste des projets.

   Par défaut, seuls les projets partagés avec vous sont affichés. Pour afficher tous les projets de votre organisation, cliquez sur l’icône **Filtrer**, puis développez [!UICONTROL **Autres filtres**] et sélectionnez [!UICONTROL **Tout afficher**]. (Pour plus d’informations sur le filtrage, le tri et la recherche dans la liste des projets, voir [Filtrage, tri et recherche dans la liste des projets](#filter-sort-and-search-the-list-of-projects).)

1. Pointez sur le projet que vous souhaitez migrer, puis sélectionnez l’icône **Migrer** ![Migrer le projet](assets/migrate.svg).

   Ou

   Sélectionnez le projet que vous souhaitez migrer, puis sélectionnez [!UICONTROL **Migrer vers Customer Journey Analytics**].

   Vous ne pouvez sélectionner qu’un seul projet à la fois pour la migration.

   La boîte de dialogue [!UICONTROL **Migrer le nom du projet vers Customer Journey Analytics**] s’affiche.

   <!-- add screenshot -->

1. Dans le champ [!UICONTROL **Propriétaire du projet**], commencez à saisir le nom de l’utilisateur que vous souhaitez définir comme propriétaire du projet en Customer Journey Analytics, puis sélectionnez son nom dans le menu déroulant.

   Le propriétaire que vous spécifiez dispose de droits de gestion complets pour le projet.

1. Dans la section [!UICONTROL **Mapper le schéma pour les suites de rapports**] , sélectionnez une suite de rapports.

1. Dans le menu déroulant [!UICONTROL **Vue des données**], sélectionnez la vue de données du Customer Journey Analytics dans laquelle vous souhaitez migrer le projet et les composants.

1. Sélectionnez [!UICONTROL **Schéma de carte**].

1. Dans la section [!UICONTROL **Mapper le schéma**] , développez les sections [!UICONTROL **Dimensions**] et [!UICONTROL **Mesures**] .

   Certaines dimensions et mesures dans Adobe Analytics sont automatiquement mappées à une dimension ou à une mesure dans Customer Journey Analytics. D’autres doivent être mappés manuellement.

   **Mappage automatique des dimensions et des mesures**

   >[!NOTE]
   >
   >   Si vous avez utilisé le WebSDK pour ingérer des données dans Adobe Experience Platform, les dimensions et les mesures ne peuvent pas être mappées automatiquement. Pour plus d’informations, voir [Conditions préalables](/help/admin/admin/component-migration/prepare-component-migration.md#prerequisites) dans [Préparation à la migration des composants et projets d’Adobe Analytics vers Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).

   Certaines dimensions et mesures dans Adobe Analytics sont automatiquement mappées à une dimension ou à une mesure dans Customer Journey Analytics. Vous ne pouvez pas prendre de décisions de mappage pour ces dimensions et mesures.

   Par exemple, la mesure **Visites** dans Adobe Analytics est automatiquement mappée à la mesure **Sessions** dans Customer Journey Analytics.

   Vous pouvez sélectionner n’importe quelle dimension ou mesure pour afficher les identifiants associés.

   <!-- update screenshot after I can see the Status column -->

   ![Schéma de migration de projet](assets/project-migration-schema.png)

   **Mappage manuel des dimensions et des mesures**

   Certaines dimensions et mesures dans Adobe Analytics ne peuvent pas être automatiquement mappées à une dimension ou à une mesure dans Customer Journey Analytics.

   Lorsqu’une dimension ou une mesure ne peut pas être mappée automatiquement, un compteur orange s’affiche en regard de l’en-tête de section [!UICONTROL **Dimensions**] ou [!UICONTROL **Mesures**], indiquant le nombre de dimensions ou de mesures à mapper manuellement. Dans le tableau, une icône d’avertissement ![icône d’avertissement](assets/schema-warning.png) s’affiche en regard de chaque dimension ou mesure qui doit être mappée manuellement.

   En outre, la colonne [!UICONTROL **Status**] indique [!UICONTROL **Non mappé**].

   <!-- update screenshot after I can see the Status column -->

   ![Mappage manuel du schéma de migration](assets/schema-manual-map.png)

1. Pour mapper manuellement des dimensions et des mesures, sélectionnez une dimension ou une mesure contenant une icône d’avertissement ![icône d’avertissement](assets/schema-warning.png), puis, dans le champ [!UICONTROL **Mesure de Customer Journey Analytics mappée**] (ou le champ [!UICONTROL **Dimension de Customer Journey Analytics mappée**] si vous mappez une dimension), sélectionnez la dimension ou la mesure dans le Customer Journey Analytics que vous souhaitez mapper à la dimension ou la mesure sélectionnée.

   ![ dimensions et mesures de mappage ](assets/schema-manual-map-drop-down.png)

   Une fois qu’une dimension ou une mesure est mappée, l’icône d’avertissement disparaît et la colonne [!UICONTROL **État**] devient [!UICONTROL **Mappé**] avec un point vert. (Un état de [!UICONTROL **Mapped**] avec un point gris indique que la dimension ou la mesure a été mappée lors d’une migration précédente ; les mappages précédents ne peuvent pas être mis à jour.)

   Répétez cette procédure pour chaque dimension ou mesure contenant l’icône d’avertissement.

   Une fois que toutes les dimensions et mesures de la suite de rapports Adobe Analytics sont mappées à une dimension ou à une mesure dans la suite de rapports du Customer Journey Analytics, une coche verte ![coche](assets/report-suite-check.png) s’affiche en regard du nom de la suite de rapports dans la section [!UICONTROL **Mapper le schéma des suites de rapports**] .

1. (Conditionnel) Si le projet que vous migrez contient plusieurs suites de rapports, sélectionnez une autre suite de rapports dans la section [!UICONTROL **Mapper le schéma pour les suites de rapports**], puis répétez les étapes 6 à 10. <!-- double-check that the step numbers are still correct -->

1. Sélectionnez [!UICONTROL **Migrer**].

   >[!WARNING]
   >
   >   Un message d’avertissement s’affiche après que vous avez sélectionné [!UICONTROL **Migrer**]. Avant de choisir de continuer, vous devez comprendre que toutes les dimensions ou mesures que vous mappez sont permanentes, à la fois pour ce projet et pour tous les projets futurs migrés dans l’ensemble de l’organisation. Si vous continuez, les mappages que vous effectuez ne peuvent pas être modifiés.

   Une fois la migration terminée, la page [!UICONTROL **Migration status**] fournit un résumé de ce qui a été migré.

   Si la migration échoue, reportez-vous à la section [Retry a failed migration](#retry-a-failed-migration) ci-dessous pour plus d’informations.

## Réessayer une migration ayant échoué

Si une migration échoue, vous pouvez effectuer une nouvelle tentative.

Avant de retenter une migration ayant échoué, veillez à supprimer du projet les [éléments non pris en charge](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html#understand-unsupported-elements-that-cause-errors).

>[!NOTE]
>
>Si la migration continue d’échouer après une nouvelle tentative, contactez l’assistance clientèle avec l’identifiant de projet. L’ID de projet est accessible sur la page État de la migration. <!-- when does this page display? How can they get there -->

Pour réessayer une migration ayant échoué :

1. Dans Adobe Analytics, sous l’onglet [!UICONTROL **Administration**] , sélectionnez [!UICONTROL **Tous les administrateurs**].

1. Sous [!UICONTROL **Configuration et collecte de données**], sélectionnez [!UICONTROL **Migration des composants**].

1. Sélectionnez [!UICONTROL **Failed**] dans la colonne [!UICONTROL **Migration status**] en regard du projet que vous souhaitez réessayer.

   ![Échec de la colonne d’état de migration](assets/migration-failed.png)

   La page [!UICONTROL **État de migration**] s’affiche.

   Cette page s’affiche également immédiatement après avoir suivi les étapes de migration décrites dans la section [Migration des projets Adobe Analytics vers Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) ci-dessus.

1. Sélectionnez [!UICONTROL **Retry migration**].

## Filtrage, tri et recherche dans la liste des projets

Vous pouvez filtrer, trier et rechercher la liste des projets sur la page de migration des composants.

### Filtrage de la liste des projets

Vous pouvez filtrer selon les critères suivants :

| Filtre | Description |
|---------|----------|
| [!UICONTROL **Statut**] | L’état de la migration : <ul><li>[!UICONTROL **Non démarré**]</li><li>[!UICONTROL **Démarré**]</li><li>[!UICONTROL **Terminé**]</li><li>[!UICONTROL **Échec**]</li></ul>. |
| [!UICONTROL **Balises**] | Sélectionnez une balise dans la liste des balises. Seuls les projets auxquels sont appliquées les balises sélectionnées sont affichés. |
| [!UICONTROL **Suite de rapports**] | Sélectionnez une suite de rapports dans la liste des suites de rapports. Seuls les projets qui utilisent les suites de rapports sélectionnées s’affichent. |
| [!UICONTROL **Propriétaires**] | Sélectionnez n’importe quel propriétaire dans la liste des propriétaires. Seuls les projets appartenant aux utilisateurs que vous sélectionnez s’affichent. |
| [!UICONTROL **Autres filtres**] | Les filtres supplémentaires suivants sont disponibles : <ul><li>[!UICONTROL **À moi**] : affiche uniquement les projets pour lesquels vous êtes défini comme propriétaire.</li><li>[!UICONTROL **Partagé avec moi**] : affiche uniquement les projets qui ont été partagés avec vous.</li><li>[!UICONTROL **Favoris**] : affiche uniquement les projets marqués comme favoris. (Vous pouvez marquer un projet comme favori à partir de la [page d’entrée du projet](/help/analyze/landing.md).)</li><li>[!UICONTROL **Mensuel**]</li><li>[!UICONTROL **Annuel**]</li></ul> |

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
