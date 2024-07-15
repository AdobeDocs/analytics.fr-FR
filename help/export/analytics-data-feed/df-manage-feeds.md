---
title: Interface utilisateur du flux de données
description: Découvrez comment naviguer dans l’interface de flux de données.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: 3916115169f526bb91442d251e6159496efd547f
workflow-type: tm+mt
source-wordcount: '1142'
ht-degree: 28%

---

# Gestion des flux de données

Le gestionnaire des flux de données vous permet de créer, de modifier et de supprimer des flux de données pour votre entreprise. Si vous disposez d’autorisations pour accéder au gestionnaire des flux de données, vous pouvez gérer les flux de données pour toutes les suites de rapports qui s’affichent.

+++Affichez une vidéo sur la gestion des flux de données.

>[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

+++

## Affichage des flux de données

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Sélectionnez l’icône de 9 carrés en haut à droite, puis sélectionnez [!UICONTROL **Analytics**].
1. Dans la barre de navigation supérieure, accédez à [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

   Les flux de données de toutes les suites de rapports auxquelles vous avez accès s’affichent. Ou, si aucun flux n’a été configuré, la page affiche un bouton [!UICONTROL Créer un nouveau flux de données] .

   ![Flux de données](assets/feeds.png)

## Création d’un flux de données

Le bouton [!UICONTROL Ajouter] vous permet de créer un nouveau flux. Pour plus d’informations, voir [Création d’un flux de données](create-feed.md) .

## Modification d’un flux de données

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Recherchez le flux de données à modifier. Pour localiser un flux de données, vous pouvez [filtrer et rechercher la liste des flux de données](#filter-and-search-the-list-of-data-feeds).

1. Sélectionnez le flux de données dans la colonne [!UICONTROL **Nom du flux**].

1. Apportez les modifications souhaitées au flux de données.

   Lors de la mise à jour de la section [!UICONTROL **Destination**] pour un flux de données que vous modifiez, vous pouvez choisir un autre compte et un autre emplacement à utiliser pour le nouveau flux de données dans les champs déroulants [!UICONTROL **Compte**] et [!UICONTROL **Emplacement**] .

   Les comptes et les emplacements peuvent être modifiés comme décrit dans les sections [Configuration des comptes d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-accounts.md) et [Configuration des emplacements d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-locations.md). La modification d’un compte ou d’un emplacement affecte tous les éléments associés à ce compte ou cet emplacement.

   Les versions précédentes du gestionnaire de flux de données vous permettaient de créer des destinations FTP, SFTP, S3 et Azure Blob. Les destinations créées dans ces versions antérieures du gestionnaire des flux de données ne peuvent pas être modifiées ni copiées.

1. Sélectionnez [!UICONTROL **Enregistrer**].

## Filtrage et recherche dans la liste des flux de données

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Utilisez la recherche ou les filtres pour localiser un flux spécifique.

   * Dans le champ de recherche, commencez à saisir le nom d’un flux. Seuls les flux qui correspondent s’affichent dans la liste des flux disponibles.

   * Cliquez sur l’icône Filtrer située à l’extrême gauche pour afficher ou masquer les options de filtrage. Les filtres sont organisés par catégorie. Vous pouvez réduire ou développer des catégories de filtrage. Cochez la case en regard d’un filtre que vous souhaitez appliquer.

![Filtrer](assets/filters.png)

## Affichage des tâches relatives aux flux de données

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Sélectionnez l’onglet [!UICONTROL **Tâches**] pour afficher les tâches individuelles créées par chacun de vos flux.

   Ou

   Pour afficher les tâches de flux de données spécifiques, cochez la case en regard d’un ou plusieurs flux de données, puis sélectionnez [!UICONTROL **Historique des tâches**].

   Pour plus d’informations, voir [Gestion des tâches de flux de données](df-manage-jobs.md).

## Copie d’un flux de données

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Cochez la case en regard du flux de données à copier, puis sélectionnez [!UICONTROL **Copier**].

   Permet de [créer un nouveau flux](create-feed.md) avec tous les paramètres du flux actuel. Cette option n’est pas visible si plusieurs flux de données sont sélectionnés.

   Lors de la mise à jour de la section [!UICONTROL **Destination**] pour un flux de données que vous copiez, vous pouvez choisir un autre compte et emplacement pour le nouveau flux de données dans les champs déroulants [!UICONTROL **Compte**] et [!UICONTROL **Emplacement**] .

   Les comptes et les emplacements peuvent être modifiés comme décrit dans les sections [Configuration des comptes d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-accounts.md) et [Configuration des emplacements d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-locations.md). La modification d’un compte ou d’un emplacement affecte tous les éléments associés à ce compte ou cet emplacement.

   Les versions précédentes du gestionnaire de flux de données vous permettaient de créer des destinations FTP, SFTP, S3 et Azure Blob. Les destinations créées dans ces versions antérieures du gestionnaire des flux de données ne peuvent pas être modifiées ni copiées.

## Suspension d’un flux de données

Vous pouvez arrêter le traitement du flux, en définissant son état sur [!UICONTROL Inactif].

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Cochez la case en regard du flux de données que vous souhaitez mettre en pause, puis sélectionnez [!UICONTROL **Pause**].

## Activation d’un flux de données

Vous pouvez activer les flux inactifs.

Les flux de renvoi (flux qui traitent uniquement les données historiques) reprennent le traitement des données là où ils se sont arrêtés, renvoyant les dates si nécessaire. Les flux en direct reprennent également le traitement des données là où ils se sont arrêtés.

>[!AVAILABILITY]
>
>La modification suivante apportée à la manière dont les flux de production reprennent les données de traitement se trouve dans la phase de test limité de la version :
> 
>**Les flux actifs reprennent les données de traitement de l’heure actuelle.**
>
>Cette modification n’est peut-être pas encore disponible dans votre environnement.
>
>Cette note sera supprimée lorsque cette modification est disponible en général. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités Adobe Analytics](/help/release-notes/releases.md).

Pour activer un flux de données :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Cochez la case en regard du flux de données inactif que vous souhaitez activer, puis sélectionnez [!UICONTROL **Activer**].

## Suppression d’un flux de données

Lorsque vous supprimez un flux de données, son état est défini sur [!UICONTROL Supprimé].

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Cochez la case en regard du flux de données à supprimer, puis sélectionnez [!UICONTROL **Supprimer**].

## Configuration des colonnes dans le gestionnaire de flux de données

Chaque flux créé affiche plusieurs colonnes fournissant des informations la concernant. Sélectionnez un en-tête de colonne pour le trier par ordre croissant. Sélectionnez à nouveau un en-tête de colonne pour le trier dans l’ordre décroissant. Si vous ne pouvez pas afficher une colonne spécifique, cliquez sur l’icône de colonne en haut à droite.

![Icône Colonne](assets/cols.jpg)

Les colonnes suivantes sont disponibles :

* **Nom du flux** : colonne requise. Affiche le nom du flux.
* **Identifiant du flux** : affiche l’identifiant du flux, un identifiant unique.
* **Suite de rapports** : la suite de rapports à partir de laquelle le flux référence les données.
* **Identifiant de la suite de rapports** : identifiant unique de la suite de rapports.
* **Colonnes de données** : les colonnes de données actives pour le flux. Dans la plupart des cas, il y a trop de colonnes à afficher dans ce format.
* **Intervalle** : indique si le flux est horaire ou quotidien.
* **Type de destination** : le type de destination du flux. Par exemple, Amazon S3, GCP ou Azure.
* **Hôte de destination** : l’emplacement où le fichier est placé.
* **Propriétaire** : compte d’utilisateur qui a créé le flux.
* **Statut** : le statut du flux.
   * Actif : le flux est opérationnel.
   * En attente d’approbation : dans certaines circonstances, un flux nécessite l’approbation d’Adobe avant de pouvoir commencer à générer des tâches.
   * Supprimé : le flux est supprimé.
   * Terminé : le flux a terminé le traitement. Un flux terminé peut être modifié, mis en attente ou supprimé.
   * En attente : le flux est créé, mais n’est pas encore actif. Les flux restent dans cet état pendant une courte période de transition.
   * Inactif : équivaut à un état « en pause » ou « en attente ». Pour plus d’informations sur ce qui se passe avec les flux de renvoi et les flux actifs lorsqu’un flux inactif est réactivé, voir [Activation d’un flux de données](#activate-a-data-feed).
* **Dernière modification** : la date à laquelle le flux a été modifié pour la dernière fois. La date et l’heure s’affichent dans le fuseau horaire de la suite de rapports en tenant compte du décalage par rapport à GMT.
* **Date de début** : la date de la première tâche pour ce flux. La date et l’heure s’affichent dans le fuseau horaire de la suite de rapports en tenant compte du décalage par rapport à GMT.
* **Date de fin** : la date de la dernière tâche pour ce flux. Les flux de données continus ne possèdent pas de date de fin.

