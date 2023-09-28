---
description: Explique comment migrer des composants et des projets d’Adobe Analytics vers Customer Journey Analytics.
title: Migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics
feature: Admin Tools
source-git-commit: 8a9c3b4d6c7a59582a6fd8bdc5464c2dbed3ad1b
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 5%

---

# Migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics

Les administrateurs Adobe Analytics peuvent migrer les composants et les projets Adobe Analytics vers Customer Journey Analytics.

Le processus de migration comprend :

* Recréation de projets Adobe Analytics dans Customer Journey Analytics.

* Correspondance de dimensions et de mesures des suites de rapports Adobe Analytics aux dimensions et aux mesures dans les vues de données de Customer Journey Analytics.

  Certaines dimensions et mesures correspondent automatiquement ; d’autres doivent correspondre manuellement dans le cadre du processus de migration.

## Conditions préalables

Avant que vos projets et les dimensions et mesures associées ne soient prêts à migrer, vous devez d’abord :

* Utilisez le connecteur source Analytics pour afficher les données de la suite de rapports Adobe Analytics dans Customer Journey Analytics. Pour ce faire, vous devez :

   * [Configuration de suites de rapports pour l’ingestion dans Adobe Experience Platform et Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [Ingérer et utiliser les données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=fr)

* Assurez-vous que les utilisateurs de Customer Journey Analytics sont configurés pour les vues de données où les données correspondent.

  Pour plus d’informations, voir [Autorisations du Customer Journey Analytics dans le Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Contrôle d’accès Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  L’onglet Autorisations fait partie de chaque profil de produit dans Admin Console. Vous pouvez ajouter des utilisateurs à des profils de produit spécifiques. Ensuite, vous attribuez des droits à des vues de données spécifiques et spécifiez les autorisations dont disposent les utilisateurs dans un profil de produits.

## Création d’un plan de migration en tant qu’organisation

Étant donné que tous les composants qui correspondent à une migration de projet donnée s’appliquent à toute migration de projet future pour l’ensemble de l’organisation, il est important que votre organisation planifie toutes les migrations de projet à l’avance.

En tant qu’organisation, vous devez décider quelles dimensions et mesures seront mises en correspondance avec ce qui sera mis en correspondance, afin d’éviter que des administrateurs individuels ne prennent des décisions dans un silo au moment de la migration d’un projet.

## Migration de projets Adobe Analytics vers Customer Journey Analytics

>[!IMPORTANT]
>
>Avant de migrer des projets vers Customer Journey Analytics comme décrit dans cette section, découvrez-en plus sur la migration des projets dans la section [Planification de la migration](#plan-the-migration) ci-dessus.
>
>Toutes les dimensions ou mesures que vous faites correspondre sont permanentes, à la fois pour ce projet et pour tous les futurs projets migrés dans l’ensemble de votre organisation. Si vous continuez, les correspondances que vous effectuez ne peuvent pas être modifiées.



1. Dans Adobe Analytics, sélectionnez la variable [!UICONTROL **Administration**] , puis sélectionnez [!UICONTROL **Tous les administrateurs**].

1. Sous [!UICONTROL **Configuration et collecte des données**], sélectionnez [!UICONTROL **Migration des composants**].

1. (Conditionnel) Pour trouver rapidement le projet que vous souhaitez migrer, vous pouvez effectuer l’une des opérations suivantes :

   * Filtrez la liste des projets en sélectionnant l&#39;icône Filtrer .

     Vous pouvez filtrer selon les critères suivants :

      * État

      * Balises

      * Suite de rapports

      * Propriétaires

      * Autres filtres

   * Utilisez le champ de recherche pour rechercher le projet à migrer.

1. Passez la souris sur le projet que vous souhaitez migrer, puis sélectionnez l’option **Migrer** icon ![Migration du projet](assets/migrate.svg).

   Ou

   Sélectionnez le projet que vous souhaitez migrer, puis sélectionnez [!UICONTROL **Migration vers Customer Journey Analytics**].

   Vous ne pouvez sélectionner qu’un seul projet à la fois pour la migration.

   La variable [!UICONTROL **Migration du nom du projet vers Customer Journey Analytics**] s’affiche.

   <!-- add screenshot -->

1. Dans le [!UICONTROL **Propriétaire du projet**] , commencez à saisir le nom de l’utilisateur que vous souhaitez définir comme propriétaire du projet dans Customer Journey Analytics, puis sélectionnez son nom dans le menu déroulant.

   Le propriétaire que vous spécifiez dispose de droits de gestion complets pour le projet.

1. Dans le [!UICONTROL **Schéma de correspondance pour les suites de rapports**] , sélectionnez une suite de rapports.

1. Dans le [!UICONTROL **Vue des données**] dans le menu déroulant, sélectionnez la vue de données du Customer Journey Analytics dans laquelle vous souhaitez migrer le projet et les composants.

1. Sélectionner [!UICONTROL **Schéma de correspondance**].

1. Dans le [!UICONTROL **Schéma de correspondance**] , développez la section [!UICONTROL **Dimensions**] et [!UICONTROL **Mesures**] sections.

   Certaines dimensions et mesures dans Adobe Analytics sont automatiquement associées à une dimension ou à une mesure dans Customer Journey Analytics. D’autres doivent correspondre manuellement.

   **Dimensions et mesures automatiquement correspondantes**

   Certaines dimensions et mesures dans Adobe Analytics sont automatiquement associées à une dimension ou à une mesure dans Customer Journey Analytics. Vous ne pouvez prendre aucune décision correspondante pour ces dimensions et mesures.

   Par exemple, la variable **Visites** dans Adobe Analytics, une correspondance automatique est établie avec la variable **Sessions** en Customer Journey Analytics.

   Vous pouvez sélectionner n’importe quelle dimension ou mesure pour afficher les identifiants associés.

   <!-- update screenshot after I can see the Status column -->

   ![Schéma de migration de projet](assets/project-migration-schema.png)

   **Faire correspondre manuellement les dimensions et les mesures**

   Les autres dimensions et mesures d’Adobe Analytics ne peuvent pas être automatiquement associées à une dimension ou à une mesure dans Customer Journey Analytics.

   Lorsqu’une dimension ou une mesure ne peut pas être mise en correspondance automatiquement, un compteur orange s’affiche en regard de la variable [!UICONTROL **Dimensions**] ou [!UICONTROL **Mesures**] en-tête de section, indiquant le nombre de dimensions ou de mesures qui doivent faire l’objet d’une correspondance manuelle. Dans le tableau, une icône d’avertissement ![icône d’avertissement](assets/schema-warning.png) s’affiche en regard de chaque dimension ou mesure qui doit faire l’objet d’une correspondance manuelle.

   <!-- update screenshot after I can see the Status column -->

   ![Correspondance manuelle du schéma de migration](assets/schema-manual-map.png)

1. Pour faire correspondre manuellement des dimensions et des mesures, sélectionnez une dimension ou une mesure contenant une icône d’avertissement. ![icône d’avertissement](assets/schema-warning.png), puis dans la variable [!UICONTROL **Mesure de Customer Journey Analytics correspondante**] (ou la variable [!UICONTROL **Dimension Customer Journey Analytics correspondante**] si vous faites correspondre une dimension), sélectionnez la dimension ou la mesure en Customer Journey Analytics que vous souhaitez faire correspondre à la dimension ou à la mesure que vous avez sélectionnée.

   ![dimensions et mesures correspondantes](assets/schema-manual-map-drop-down.png)

   Répétez cette procédure pour chaque dimension ou mesure contenant l’icône d’avertissement.

   Une fois que toutes les dimensions et mesures de la suite de rapports Adobe Analytics sont associées à une dimension ou à une mesure dans la vue de données du Customer Journey Analytics, une coche verte s’affiche. ![coche](assets/report-suite-check.png) apparaît en regard du nom de la suite de rapports dans la variable [!UICONTROL **Schéma de correspondance pour les suites de rapports**] .

1. (Conditionnel) Si le projet que vous migrez contient plusieurs suites de rapports, sélectionnez-en une autre dans la variable [!UICONTROL **Schéma de correspondance pour les suites de rapports**] , puis répétez les étapes 6 à 10. <!-- double-check that the step numbers are still correct -->

1. Sélectionner [!UICONTROL **Migrer**].

   >[!WARNING]
   >
   >   Un message d’avertissement s’affiche après avoir sélectionné [!UICONTROL **Migrer**]. Avant de choisir de continuer, vous devez comprendre que toutes les dimensions ou mesures auxquelles vous faites correspondre sont permanentes, à la fois pour ce projet et pour tous les projets futurs migrés dans l’ensemble de l’organisation. Si vous continuez, les correspondances que vous effectuez ne peuvent pas être modifiées.
