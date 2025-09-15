---
description: Explique comment migrer des composants et des projets d’Adobe Analytics vers Customer Journey Analytics.
title: Migration de composants et de projets d’Adobe Analytics vers Customer Journey Analytics
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: ec4475cdd8f0c3e89f528bd60155caa1ca3f0645
workflow-type: tm+mt
source-wordcount: '1641'
ht-degree: 4%

---

# Migration de composants et de projets d’Adobe Analytics vers Customer Journey Analytics

Les administrateurs Adobe Analytics peuvent migrer les projets Adobe Analytics et leurs composants associés vers Customer Journey Analytics.

Le processus de migration comprend :

* La recréation de projets Adobe Analytics dans Customer Journey Analytics.

* Le mappage des dimensions et des mesures des suites de rapports Adobe Analytics à des dimensions et des mesures dans les vues de données de Customer Journey Analytics.

  Certaines dimensions et mesures sont automatiquement mappées ; d’autres doivent être mappées manuellement dans le cadre du processus de migration. Les segments sont également migrés, mais ils n’ont pas besoin d’être mappés dans le cadre du processus de migration.

  Tous les composants migrés s’affichent dans le résumé de la migration une fois la migration terminée.

>[!NOTE]
>
>Les informations de cette page décrivent comment migrer des projets et leurs composants associés avec l’interface utilisateur.
>
>Vous pouvez également effectuer la migration à l’aide des API. Pour plus d’informations, consultez les [API Adobe Analytics](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Analytics%202.0%20APIs). Toutes les définitions d’API sont disponibles dans le menu déroulant **[!UICONTROL Sélectionner une définition]**.


## Préparation à une migration

Avant de migrer des projets vers Customer Journey Analytics, apprenez-en davantage sur la migration des projets dans la section [ Préparer la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).

Effectuez également un [inventaire Adobe Analytics](/help/admin/tools/analytics-inventory.md) à l’aide de l’outil disponible pour les administrateurs et administratrices Analytics.

## Migration de projets Adobe Analytics vers Customer Journey Analytics

>[!NOTE]
>
>Avant de migrer des projets vers Customer Journey Analytics comme décrit dans cette section, pour en savoir plus sur la migration des projets, reportez-vous à la section [ Préparer la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics ](/help/admin/tools/component-migration/prepare-component-migration.md).
>
>**Toutes les dimensions ou mesures que vous mappez s’appliquent à ce projet et à tous les projets futurs dans l’ensemble de votre organisation IMS, quel que soit l’utilisateur ou l’utilisatrice qui effectue la migration. Ces mappages peuvent être mis à jour lors de la migration de projets futurs.**

1. Dans Adobe Analytics, sous l’onglet [!UICONTROL **Administration**] , sélectionnez [!UICONTROL **Tous les administrateurs**].

1. Sous [!UICONTROL **Configuration et collecte des données**], sélectionnez [!UICONTROL **Migration des composants**].

1. Recherchez chaque projet à migrer. Vous pouvez filtrer, trier ou rechercher la liste des projets.

   Par défaut, seuls les projets partagés avec vous s’affichent. Pour afficher tous les projets de votre organisation, sélectionnez l’icône **Filtre**, puis développez [!UICONTROL **Autres filtres**] et sélectionnez [!UICONTROL **Tout afficher**]. (Pour plus d’informations sur le filtrage, le tri et la recherche dans la liste des projets, voir [Filtrer, trier et rechercher dans la liste des projets](#filter-sort-and-search-the-list-of-projects).)

1. (Conditionnel) Pour migrer plusieurs projets en même temps, cochez la case située à gauche de chaque projet à migrer, puis sélectionnez [!UICONTROL **Migrer vers Customer Journey Analytics**].

   Tenez compte des points suivants lors de la migration de plusieurs projets :

   * Vous pouvez sélectionner jusqu’à 20 projets à migrer en même temps.

   * Le statut de migration doit être le même pour tous les projets que vous migrez.

     Par exemple, si vous sélectionnez un projet à migrer dont le statut de migration est **[!UICONTROL Non démarré]**, vous ne pouvez pas sélectionner un autre projet dont le statut de migration est **[!UICONTROL Échec]**.

   * Vous devez désigner le même propriétaire de projet pour tous les projets que vous migrez.

   * Les dimensions et les mesures doivent être mappées à la même vue de données pour tous les projets que vous migrez.

   La boîte de dialogue [!UICONTROL **Migrer project_name vers Customer Journey Analytics**] s’affiche.

   <!-- add screenshot -->

1. (Conditionnel) Pour migrer un seul projet, placez le pointeur de la souris sur le projet à migrer, puis sélectionnez l’icône **Migrer** ![Migrer le projet](assets/migrate.svg).

   La boîte de dialogue [!UICONTROL **Migrer project_name vers Customer Journey Analytics**] s’affiche.

   <!-- add screenshot -->

1. Dans le champ [!UICONTROL **Propriétaire du projet**], commencez à saisir le nom de l’utilisateur que vous souhaitez définir comme propriétaire des projets migrés dans Customer Journey Analytics, puis sélectionnez son nom dans le menu déroulant.

   Le propriétaire que vous spécifiez dispose de droits de gestion complets sur les projets migrés. Le propriétaire doit être un administrateur dans Customer Journey Analytics. Vous pouvez modifier la propriété des projets à une étape ultérieure.

1. Dans la section [!UICONTROL **Mapper le schéma pour les suites de rapports**] sélectionnez une suite de rapports.

1. Dans le menu déroulant [!UICONTROL **Vue de données**], sélectionnez la vue de données Customer Journey Analytics dans laquelle vous souhaitez que les projets et les composants soient migrés.

   Lorsque vous migrez plusieurs projets, tous ceux que vous migrez sont combinés dans le mappage de vue de données unique.

1. Sélectionnez [!UICONTROL **Mapper le schéma**].

1. Dans la section [!UICONTROL **Mapper le schéma**], développez les sections [!UICONTROL **Dimensions**] et [!UICONTROL **Mesures**].

   Certaines dimensions et mesures d’Adobe Analytics sont automatiquement mappées à une dimension ou à une mesure dans Customer Journey Analytics. Les autres doivent être mappés manuellement.

   **Mapper automatiquement les dimensions et les mesures**

   >[!NOTE]
   >
   >   Si vous avez utilisé le SDK Web pour ingérer des données dans Adobe Experience Platform, les dimensions et les mesures ne peuvent pas être automatiquement mappées. Pour plus d’informations, voir [Conditions préalables](/help/admin/tools/component-migration/prepare-component-migration.md#prerequisites) dans [Préparation de la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).

   Certaines dimensions et mesures d’Adobe Analytics sont automatiquement mappées à une dimension ou à une mesure dans Customer Journey Analytics. Vous ne pouvez prendre aucune décision de mappage pour ces dimensions et mesures.

   Par exemple, la mesure **Visites** dans Adobe Analytics est automatiquement mappée à la mesure **Sessions** dans Customer Journey Analytics.

   Vous pouvez sélectionner n’importe quelle dimension ou mesure pour afficher les identifiants associés.

   <!-- update screenshot after I can see the Status column -->

   ![Schéma de migration du projet](assets/project-migration-schema.png)

   **Mapper manuellement des dimensions et des mesures**

   Certaines dimensions et mesures dans Adobe Analytics ne peuvent pas être automatiquement mappées à une dimension ou à une mesure dans Customer Journey Analytics.

   Lorsqu’une dimension ou une mesure ne peut pas être mappée automatiquement, un compteur orange s’affiche en regard de l’en-tête de section [!UICONTROL **Dimensions**] ou [!UICONTROL **Mesures**], indiquant le nombre de dimensions ou de mesures qui doivent être mappées manuellement. Dans le tableau, une icône d’avertissement ![icône d’avertissement](assets/schema-warning.png) s’affiche en regard de chaque dimension ou mesure qui doit être mappée manuellement.

   En outre, la colonne [!UICONTROL **Statut**] indique [!UICONTROL **Non mappé**].

   <!-- update screenshot after I can see the Status column -->

   ![Carte manuelle du schéma de migration](assets/schema-manual-map.png)

1. Pour mapper manuellement des dimensions et des mesures, sélectionnez une dimension ou une mesure contenant une icône d’avertissement ![icône d’avertissement](assets/schema-warning.png), puis, dans le champ [!UICONTROL **Mesure Customer Journey Analytics mappée**] (ou le champ [!UICONTROL **Dimension Customer Journey Analytics mappée**] si vous mappez une dimension), sélectionnez la dimension ou la mesure dans Customer Journey Analytics que vous souhaitez mapper à la dimension ou à la mesure que vous avez sélectionnée.

   ![mapper des dimensions et des mesures](assets/schema-manual-map-drop-down.png)

   Une fois une dimension ou une mesure mappée, l’icône d’avertissement disparaît et la colonne [!UICONTROL **Statut**] devient [!UICONTROL **Mappé**] avec un point vert. (Un statut [!UICONTROL **Mappé**] avec un point gris indique que la dimension ou la mesure a été mappée lors d’une migration précédente ; les mappages précédents ne peuvent pas être mis à jour.)

   Répétez ce processus pour chaque dimension ou mesure contenant l’icône d’avertissement.

   Une fois que toutes les dimensions et mesures de la suite de rapports Adobe Analytics sont mappées à une dimension ou à une mesure de la suite de rapports Customer Journey Analytics, une coche verte ![coche](assets/report-suite-check.png) s’affiche en regard du nom de la suite de rapports dans la section [!UICONTROL **Mapper le schéma aux suites de rapports**].

1. (Conditionnel) Si les projets que vous migrez contiennent plusieurs suites de rapports, sélectionnez une autre suite de rapports dans la section [!UICONTROL **Mapper le schéma aux suites de rapports**], puis répétez les étapes 6 à 10. <!-- double-check that the step numbers are still correct -->

1. Sélectionnez [!UICONTROL **Migrer**].

   >[!WARNING]
   >
   >Un message d’avertissement s’affiche à l’écran après avoir sélectionné [!UICONTROL **Migrer**]. Avant de choisir de continuer, sachez que toutes les dimensions ou mesures que vous mappez s’appliquent à ce projet et à tous les projets futurs dans l’ensemble de votre organisation IMS, quel que soit l’utilisateur ou l’utilisatrice qui effectue la migration. Ces mappages peuvent être mis à jour lors de la migration de projets futurs.

   Une fois la migration terminée, la page [!UICONTROL **Statut de migration**] fournit un résumé des éléments migrés.

   Si la migration échoue, consultez la section [Réessayer une migration ayant échoué](#retry-a-failed-migration) ci-dessous pour plus d’informations.

1. (Facultatif) Une fois les projets migrés, vous pouvez transférer la propriété des projets à n’importe quel utilisateur dans Customer Journey Analytics. Pour plus d’informations, voir [Transfert de ressources](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/tools/asset-transfer/transfer-assets) dans le guide de Customer Journey Analytics.

## Reprise d’une migration ayant échoué

Si une migration échoue, vous pouvez réessayer.

Avant de retenter une migration ayant échoué, veillez à supprimer du projet tous les [éléments non pris en charge](/help/admin/tools/component-migration/prepare-component-migration.md#understand-unsupported-elements-that-cause-errors).

>[!NOTE]
>
>Si l’échec de la migration persiste après de nouvelles tentatives, contactez l’assistance clientèle en indiquant l’ID de projet. L’ID du projet se trouve sur la page Statut de migration . <!-- when does this page display? How can they get there -->

Pour réessayer une migration ayant échoué :

1. Dans Adobe Analytics, sous l’onglet [!UICONTROL **Administration**] , sélectionnez [!UICONTROL **Tous les administrateurs**].

1. Sous [!UICONTROL **Configuration et collecte des données**], sélectionnez [!UICONTROL **Migration des composants**].

1. Sélectionnez [!UICONTROL **Échec**] dans la colonne [!UICONTROL **Statut de migration**] en regard du projet que vous souhaitez réessayer.

   ![échec de la colonne du statut de migration](assets/migration-failed.png)

   La page [!UICONTROL **Statut de migration**] s’affiche.

   Cette page s’affiche également immédiatement après avoir suivi les étapes de migration décrites dans la section [Migration des projets Adobe Analytics vers Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) ci-dessus.

1. Sélectionnez [!UICONTROL **Réessayer la migration**].

## Filtrer, trier et rechercher la liste des projets

Vous pouvez filtrer, trier et rechercher la liste des projets sur la page Migration des composants .

### Filtrer la liste des projets

Vous pouvez filtrer selon les critères suivants :

| Filtre | Description |
|---------|----------|
| [!UICONTROL **Statut**] | Statut de la migration : <ul><li>[!UICONTROL **Non démarré**]</li><li>[!UICONTROL **Commencé**]</li><li>[!UICONTROL **Terminé**]</li><li>[!UICONTROL **Échec**]</li></ul>. |
| [!UICONTROL **Balises**] | Sélectionnez une balise dans la liste des balises. Seuls les projets pour lesquels les balises sélectionnées sont appliquées s’affichent. |
| [!UICONTROL **Suite de rapports**] | Sélectionnez une suite de rapports dans la liste des suites de rapports. Seuls les projets qui utilisent les suites de rapports sélectionnées s’affichent. |
| [!UICONTROL **Propriétaires**] | Sélectionnez un propriétaire dans la liste des propriétaires. Seuls les projets appartenant aux utilisateurs que vous sélectionnez s’affichent. |
| [!UICONTROL **Autres filtres**] | Les filtres supplémentaires suivants sont disponibles : <ul><li>[!UICONTROL **À moi**] : affiche uniquement les projets dont vous êtes défini comme propriétaire.</li><li>[!UICONTROL **Partagé avec moi**] : affiche uniquement les projets qui ont été partagés avec vous.</li><li>[!UICONTROL **Favoris**] : affiche uniquement les projets marqués comme favoris. (Vous pouvez marquer un projet comme favori à partir de la [page de destination du projet](/help/analyze/landing.md).)</li><li>[!UICONTROL **Mensuel**]</li><li>[!UICONTROL **Annuel**]</li></ul> |

{style="table-layout:auto"}

### Trier la liste des projets

Vous pouvez trier la liste des projets en fonction de n’importe quelle colonne.

Pour trier la liste des projets :

1. Sélectionnez l’en-tête de colonne de la colonne selon laquelle vous souhaitez effectuer le tri.

1. (Facultatif) Sélectionnez à nouveau le même en-tête de colonne pour inverser l’ordre de tri.

### Rechercher un projet

Vous pouvez rechercher la liste des projets sur la page Migration des composants pour trouver le projet à migrer.

1. Dans le champ de recherche en haut de la page Migration des composants, commencez à saisir le nom du projet à migrer.

1. Sélectionnez le projet lorsqu’il apparaît dans le menu déroulant.

<!-- is there going to be a way to customize the columns that are displayed? -->
