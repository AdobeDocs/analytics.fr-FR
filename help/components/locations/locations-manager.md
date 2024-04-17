---
description: Configuration du compte d’importation dans le cloud et de l’emplacement où les données de classification peuvent être chargées
keywords: Analysis Workspace
title: Gestionnaire d’emplacements
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 7b293c962428c7b8fac62a9f70ce62a0fe8f0cea
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# Gestionnaire d’emplacements

Le gestionnaire des emplacements vous permet d’afficher, de créer, de modifier ou de supprimer des comptes et des emplacements. Ils peuvent être utilisés à l’une des fins suivantes :

* Exportation de fichiers à l’aide de [Flux de données](/help/export/analytics-data-feed/create-feed.md)
* Exporter des rapports à l’aide de [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Import de schémas à l’aide de [Jeux de classifications](/help/components/classifications/sets/overview.md)

## Affichage, filtrage et recherche des emplacements

Le gestionnaire d’emplacement vous permet d’afficher les emplacements que vous avez créés. Les administrateurs système peuvent afficher les emplacements créés par tous les utilisateurs.

1. Pour accéder au gestionnaire d’emplacements dans Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**.

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer la variable [!UICONTROL **Affichage des emplacements pour tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise. <!-- Maybe add a screenshot? This is new functionality -->

1. Filtrez ou recherchez dans la liste des emplacements :

   * **Filtre :** Sélectionnez l’icône Filtrer pour filtrer la liste des emplacements.

     Vous pouvez filtrer les emplacements par **[!UICONTROL Type d’emplacement]**, **[!UICONTROL Compte]**, ou **[!UICONTROL Créé par]**.

     ![Filtres des emplacements](assets/locations-filters.png)

   * **Rechercher :** Dans le champ de recherche, commencez à saisir le nom de l’emplacement à afficher. Les résultats sont filtrés au fur et à mesure que vous tapez. La recherche porte sur les colonnes suivantes : **Nom de l’emplacement**, **Type d’emplacement**, **Compte**, et **Créé par**.

1. (Facultatif) Si vous avez plus de 1 000 emplacements, seuls les 1 000 premiers s’affichent. Sélectionner [!UICONTROL **Charger plus**] pour charger 1 000 autres emplacements.

## Configuration des colonnes dans le gestionnaire d’emplacements

Les colonnes suivantes sont disponibles dans le gestionnaire d’emplacements. Pour personnaliser les colonnes affichées dans le tableau, sélectionnez la variable **Personnalisation du tableau** icon ![Icône Personnaliser le tableau](assets/customize-table-icon.png).

* **[!UICONTROL Nom de l’emplacement]**: nom de l’emplacement. Sélectionnez le menu à 3 points en regard du nom d’un emplacement pour effectuer l’une des opérations suivantes : [modifier l’emplacement ;](/help/components/locations/configure-import-locations.md) ou supprimez-le.
* **[!UICONTROL Type d’emplacement]**: type de compte associé à l’emplacement.
* **[!UICONTROL Compte]**: compte spécifique associé à l’emplacement.
* **Application**: type d’application avec lequel l’emplacement peut être utilisé (flux de données, Data Warehouse ou jeux de classifications, par exemple).
* **[!UICONTROL Dernière utilisation]**: date à laquelle l’emplacement a été utilisé pour la dernière fois.
* **[!UICONTROL Créé par]**: utilisateur qui a créé l’emplacement.
* **[!UICONTROL Date de création]**: date à laquelle l’emplacement a été créé.

## Création et gestion des emplacements

Vous pouvez créer, modifier et supprimer des emplacements.

### Création d’un emplacement

Pour plus d’informations sur la création d’un emplacement, voir [Configuration des emplacements d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### Modification d’un emplacement

Pour plus d’informations sur la modification d’un emplacement, voir [Configuration des emplacements d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-locations.md).

### Suppression d’un emplacement

>[!IMPORTANT]
>
>Si un emplacement est supprimé, les fichiers de flux de données, les rapports de Data Warehouse ou les schémas de jeu de classifications associés à l’emplacement supprimé échoueront la prochaine fois qu’ils seront utilisés.
>
>Si vous supprimez un emplacement, vous devez [modification des flux de données](/help/export/analytics-data-feed/create-feed.md), [Rapports de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), et [Schémas de jeux de classifications](/help/components/classifications/sets/manage/schema.md) pour utiliser un emplacement fonctionnel.

Pour supprimer un emplacement :

1. Sélectionnez le menu à 3 points dans le [!UICONTROL **Nom de l’emplacement**] pour l’emplacement à supprimer.

1. Sélectionnez [!UICONTROL **Supprimer**].

## Modifier des comptes

1. Pour modifier des comptes dans le gestionnaire d’emplacements d’Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**, puis sélectionnez la variable [!UICONTROL **Comptes d’emplacement**] .

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer la variable [!UICONTROL **Affichage des comptes de tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise. <!-- Maybe add a screenshot? This is new functionality -->


1. Sélectionner [!UICONTROL **Afficher les détails**] sur le compte que vous souhaitez modifier.

1. Effectuez les modifications souhaitées, puis sélectionnez [!UICONTROL **Enregistrer**].

## Afficher les clés de compte

Après avoir créé un compte, vous pouvez afficher toutes les clés de compte associées pour ce compte. Vous devrez peut-être afficher ces informations si vous n’avez pas terminé la configuration du compte avec votre fournisseur cloud lorsque vous [configuration initiale du compte](/help/components/locations/configure-import-accounts.md).

Pour visualiser les clés associées à un compte d&#39;export :

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**, puis sélectionnez la variable [!UICONTROL **Comptes d’emplacement**] .

1. Sélectionnez l’icône à 3 points sur le compte que vous souhaitez modifier, puis sélectionnez [!UICONTROL **Clés de compte**].

## Supprimer des comptes

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**, puis sélectionnez la variable [!UICONTROL **Comptes d’emplacement**] .

1. Sélectionnez l’icône à 3 points sur le compte que vous souhaitez modifier, puis sélectionnez [!UICONTROL **Supprimer un compte**]
