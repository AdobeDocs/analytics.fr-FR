---
description: Configuration du compte d’importation dans le cloud et de l’emplacement où les données de classification peuvent être chargées
keywords: Analysis Workspace
title: Gestionnaire d’emplacements
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: a81cc80ddc884c3f908e66e37593e1ce1b829a50
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 1%

---

# Gestionnaire d’emplacements

Le gestionnaire des emplacements vous permet d’afficher, de créer, de modifier ou de supprimer des comptes et des emplacements. Ils peuvent être utilisés à l’une des fins suivantes :

* Exportation de fichiers à l’aide de [ flux de données](/help/export/analytics-data-feed/create-feed.md)
* Exportation de rapports à l’aide de [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importation de schémas à l’aide de [jeux de classifications](/help/components/classifications/sets/overview.md)

## Affichage, filtrage et recherche des emplacements

Le gestionnaire d’emplacement vous permet d’afficher les emplacements que vous avez créés ou qui sont partagés avec l’organisation. Les administrateurs système peuvent afficher les emplacements créés par tous les utilisateurs, qu’ils soient partagés ou non.

1. Pour accéder au gestionnaire d’emplacements dans Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**.

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer l’option [!UICONTROL **Afficher les emplacements pour tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise. <!-- Maybe add a screenshot? This is new functionality -->

1. Filtrez ou recherchez dans la liste des emplacements :

   * **Filtre :** Sélectionnez l’icône Filtrer pour filtrer la liste des emplacements.

     Vous pouvez filtrer les emplacements par **[!UICONTROL Type d’emplacement]**, **[!UICONTROL Compte]** ou **[!UICONTROL Créé par]**.

     ![Filtres d’emplacements](assets/locations-filters.png)

   * **Rechercher :** Dans le champ de recherche, commencez à saisir le nom de l’emplacement à afficher. Les résultats sont filtrés au fur et à mesure que vous tapez. Les colonnes suivantes font l’objet d’une recherche : **Nom de l’emplacement**, **Type d’emplacement**, **Compte** et **Créé par**.

1. (Facultatif) Si vous avez plus de 1 000 emplacements, seuls les 1 000 premiers s’affichent. Sélectionnez [!UICONTROL **Charger plus**] pour charger 1 000 autres emplacements.

## Configuration des colonnes dans le gestionnaire d’emplacements

Les colonnes suivantes sont disponibles dans le gestionnaire d’emplacements. Pour personnaliser les colonnes affichées dans le tableau, sélectionnez l’icône **Personnaliser la table** ![Icône Personnaliser la table](assets/customize-table-icon.png).

* **[!UICONTROL Nom de l’emplacement]** : nom de l’emplacement. Sélectionnez le menu à 3 points en regard d’un nom d’emplacement pour [modifier l’emplacement](/help/components/locations/configure-import-locations.md) ou le supprimer.
* **[!UICONTROL Type d’emplacement]** : type de compte associé à l’emplacement.
* **[!UICONTROL Compte]** : compte spécifique associé à l’emplacement.
* **Application** : type d’application avec lequel l’emplacement peut être utilisé (flux de données, Data Warehouse ou ensembles de classifications, par exemple).
* **[!UICONTROL Dernière utilisation]** : date à laquelle l’emplacement a été utilisé pour la dernière fois.
* **[!UICONTROL Créé par]** : utilisateur qui a créé l’emplacement.
* **[!UICONTROL Date de création]** : date de création de l’emplacement.

## Création et gestion des emplacements

Vous pouvez créer, modifier et supprimer des emplacements.

### Création d’un emplacement

Pour plus d’informations sur la création d’un emplacement, voir [Configuration des emplacements d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### Modification d’un emplacement

Un emplacement ne peut être modifié que par l’utilisateur qui l’a créé ou par un administrateur système.

Pour plus d’informations sur la modification d’un emplacement, voir [Configuration des emplacements d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-locations.md).

### Suppression d’un emplacement

>[!IMPORTANT]
>
>Si un emplacement est supprimé, les fichiers de flux de données, les rapports de Data Warehouse ou les schémas de jeu de classifications associés à l’emplacement supprimé échoueront la prochaine fois qu’ils seront utilisés.
>
>Si vous supprimez un emplacement, vous devez [ modifier vos flux de données](/help/export/analytics-data-feed/create-feed.md), [rapports de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) et [schémas de classification](/help/components/classifications/sets/manage/schema.md) pour utiliser un emplacement fonctionnel.

Un emplacement ne peut être supprimé que par l’utilisateur qui l’a créé ou par un administrateur système.

Pour supprimer un emplacement dans le gestionnaire d’emplacements d’Adobe Analytics :

1. Sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**, puis sélectionnez l’onglet [!UICONTROL **Emplacements**] .

1. Sélectionnez le menu à 3 points dans la colonne [!UICONTROL **Nom de l’emplacement**] pour l’emplacement que vous souhaitez supprimer.

1. Sélectionnez [!UICONTROL **Supprimer**].

## Création et gestion de comptes

Vous pouvez créer, modifier et supprimer des comptes.

### Créer un compte

Pour plus d&#39;informations sur la création d&#39;un compte, voir [Configuration de comptes d&#39;import et d&#39;export cloud](/help/components/locations/configure-import-accounts.md).

### Modification d’un compte

Un compte ne peut être modifié que par l’utilisateur qui l’a créé ou par un administrateur système.

Pour plus d&#39;informations sur la modification d&#39;un compte, voir [Configuration de comptes d&#39;import et d&#39;export cloud](/help/components/locations/configure-import-accounts.md).

### Afficher les clés de compte

Après avoir créé un compte, vous pouvez afficher toutes les clés de compte associées pour ce compte. Vous devrez peut-être afficher ces informations si vous n’avez pas terminé la configuration du compte avec votre fournisseur cloud lorsque vous [avez initialement configuré le compte](/help/components/locations/configure-import-accounts.md).

Pour visualiser les clés associées à un compte d&#39;export :

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**, puis sélectionnez l’onglet [!UICONTROL ****].

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer l’option [!UICONTROL **Afficher les emplacements pour tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise. <!-- Maybe add a screenshot? This is new functionality -->

1. Sélectionnez l’icône à 3 points sur le compte que vous souhaitez modifier, puis sélectionnez [!UICONTROL **Clés de compte**].

### Suppression d’un compte

>[!IMPORTANT]
>
>Les comptes ne peuvent être supprimés que s’il n’y a aucun emplacement qui les utilise. Avant de supprimer un compte, vous devez d’abord supprimer les emplacements du compte, comme décrit dans la section [Suppression d’un emplacement](#delete-a-location).

Un compte ne peut être supprimé que par l’utilisateur qui l’a créé ou par un administrateur système.

Pour supprimer un compte :

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**, puis sélectionnez l’onglet [!UICONTROL ****].

1. (Conditionnel) Si vous êtes administrateur système, vous pouvez activer l’option [!UICONTROL **Afficher les comptes de tous les utilisateurs**] pour afficher les emplacements créés par tous les utilisateurs de votre entreprise.

1. Sélectionnez l’icône à 3 points sur le compte à modifier, puis sélectionnez [!UICONTROL **Supprimer le compte**]

## Configuration des paramètres à l’échelle de l’entreprise (administrateurs uniquement)

Les administrateurs système peuvent empêcher les utilisateurs de créer des comptes et des emplacements ou limiter les types de comptes que les utilisateurs peuvent créer et utiliser.

![Onglet Paramètres d’administration](assets/locations-admin-settings.png)

### Configuration de la création et de la modification de comptes par les utilisateurs

Par défaut, tous les utilisateurs de l’organisation peuvent créer des comptes et modifier les comptes qu’ils créent dans votre environnement Adobe Analytics, comme décrit dans la section [Configuration des comptes d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-accounts.md).

Vous pouvez empêcher les utilisateurs de créer des comptes. Lorsque vous le faites, les utilisateurs peuvent toujours utiliser les comptes qu’ils ont déjà créés, mais ils ne peuvent plus les modifier. Vous pouvez supprimer les comptes créés par les utilisateurs, comme décrit dans la section [Suppression d’un compte](#delete-an-account).

Pour empêcher tous les utilisateurs de créer et de modifier des comptes :

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**, puis sélectionnez l’onglet [!UICONTROL **Paramètres d’administration**].

1. Dans la section [!UICONTROL **Comptes d’emplacements**], désélectionnez l’option [!UICONTROL **Autoriser les utilisateurs à créer et gérer des comptes d’emplacement**].

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. (Facultatif) Supprimez tous les comptes que les utilisateurs ont créés et que vous ne souhaitez plus utiliser, comme décrit dans la section [Suppression d’un compte](#delete-an-account).

### Configurer si les utilisateurs peuvent créer et modifier des emplacements

Par défaut, tous les utilisateurs de l’organisation peuvent créer des emplacements et modifier les emplacements qu’ils créent dans votre environnement Adobe Analytics, comme décrit dans la section [Configuration des emplacements d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-locations.md).

Vous pouvez empêcher les utilisateurs de créer des emplacements. Dans ce cas, les utilisateurs peuvent toujours utiliser les emplacements qu’ils ont déjà créés, mais ils ne peuvent plus les modifier. Vous pouvez supprimer les emplacements créés par les utilisateurs, comme décrit dans [Supprimer les emplacements](#delete-a-location).

Pour empêcher tous les utilisateurs de créer et de modifier des emplacements :

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**, puis sélectionnez l’onglet [!UICONTROL **Paramètres d’administration**].

1. Dans la section [!UICONTROL **Emplacements**], désélectionnez l’option [!UICONTROL **Autoriser les utilisateurs à créer et gérer des emplacements**].

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. (Facultatif) Supprimez tous les emplacements que les utilisateurs ont créés et que vous ne souhaitez plus utiliser, comme décrit dans la section [Suppression d’un emplacement](#delete-a-location).

### Limitation des types de comptes que les utilisateurs peuvent créer et utiliser

Vous pouvez limiter les types de compte que les utilisateurs voient dans les cas suivants :

* Lors de la [création de nouveaux comptes](/help/components/locations/configure-import-accounts.md).

* Lors du choix des comptes à utiliser lors de l’exportation de fichiers à l’aide de [flux de données](/help/export/analytics-data-feed/create-feed.md), de l’exportation de rapports à l’aide de [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) ou de l’importation de schémas à l’aide de [jeux de classifications](/help/components/classifications/sets/overview.md).

Lorsque vous limitez les types de compte comme décrit dans cette section, les comptes du type que vous limitez ne sont plus visibles par les utilisateurs. Cela signifie que de nouveaux comptes de ce type ne peuvent pas être créés et que les comptes existants de ce type ne peuvent pas être utilisés lors de la création de flux de données, de Data Warehouse ou de jeux de classifications.

Toutefois, les comptes existants configurés pour les exportations planifiées doivent être supprimés si vous souhaitez empêcher leur utilisation.

#### S’assurer que les comptes ne sont pas utilisés pour les exportations planifiées

Lorsque vous limitez les types de compte, les comptes existants sont masqués et non supprimés.

Si des plannings sont déjà configurés pour envoyer des données à un compte du type que vous limitez, les plannings continueront à s’exécuter même après avoir limité le type de compte et les données continueront à être envoyées au compte.  Par exemple, si un flux de données est programmé pour envoyer des données vers un type de compte que vous limitez, le planning continuera à s’exécuter.

Si vous devez vous assurer que les comptes d’un certain type ne sont pas utilisés dans les exportations planifiées, vous pouvez supprimer les comptes avant de [limiter les types de compte](#limit-the-account-types-that-are-available-to-users).

Pour supprimer des comptes :

1. Localisez les comptes du type de compte que vous prévoyez de limiter et qui sont utilisés pour les exportations planifiées.

1. Supprimez les comptes, comme décrit dans la section [Suppression d&#39;un compte](#delete-an-account).

1. Passez à la section suivante, [Limitez les types de compte disponibles pour les utilisateurs](#limit-the-account-types-that-are-available-to-users).

#### Limitation des types de compte disponibles pour les utilisateurs

Pour limiter les types de compte disponibles pour les utilisateurs lors de la création et de l’utilisation de comptes :

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Emplacements]**, puis sélectionnez l’onglet [!UICONTROL **Paramètres d’administration**].

1. Recherchez la section [!UICONTROL **Types de compte autorisé**] .

   Par défaut, les types de compte suivants sont disponibles pour les utilisateurs. Désélectionnez l’un de ces types de compte que vous souhaitez empêcher l’utilisation des utilisateurs.

   Vous devez sélectionner au moins un type de compte.

   * [!UICONTROL **{Amazon S3 Role ARN**]

   * [!UICONTROL **Plateforme cloud Google**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **Adresse électronique**]

   * Types de compte hérités, y compris [!UICONTROL **Amazon S3**], [!UICONTROL **Azure**], [!UICONTROL **FTP**] et [!UICONTROL **SFTP**]

1. Sélectionnez [!UICONTROL **Enregistrer**].


