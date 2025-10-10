---
title: Gestion des flux de données
description: Découvrez comment naviguer dans l’interface du flux de données. Découvrez comment créer, modifier et afficher un flux de données.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: 5bf3f561c471410e4ce1ca576ba34ea3849b0325
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 21%

---

# Gestion des flux de données

Le gestionnaire des flux de données vous permet de créer, de modifier et de supprimer des flux de données pour votre entreprise. Si vous disposez d’autorisations pour accéder au gestionnaire des flux de données, vous pouvez gérer les flux de données pour toutes les suites de rapports qui s’affichent.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Gestion des flux de données](https://video.tv.adobe.com/v/3428562?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Affichage des flux de données

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Sélectionnez l’icône des 9 carrés dans le coin supérieur droit, puis sélectionnez [!UICONTROL **Analytics**].
1. Dans la barre de navigation supérieure, accédez à [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

   Les flux de données de toutes les suites de rapports auxquelles vous avez accès s’affichent. Si aucun flux n’a été configuré, la page affiche également un bouton [!UICONTROL Créer un flux de données].

   ![Flux de données](assets/feeds.png)

## Créer un flux de données

Le bouton [!UICONTROL Ajouter] permet de créer un flux. Voir [Créer un flux de données](create-feed.md) pour plus d’informations.

## Modification d’un flux de données

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Recherchez le flux de données à modifier. Pour localiser un flux de données, vous pouvez [filtrer et rechercher la liste des flux de données](#filter-and-search-the-list-of-data-feeds).

1. Sélectionnez le flux de données dans la colonne [!UICONTROL **Nom du flux**].

1. Apportez les modifications souhaitées au flux de données.

   Lors de la mise à jour de la section [!UICONTROL **Destination**] pour un flux de données que vous modifiez, vous pouvez choisir un compte et un emplacement différents à utiliser pour le nouveau flux de données dans les champs déroulants [!UICONTROL **Compte**] et [!UICONTROL **Emplacement**].

   Les comptes et emplacements peuvent être modifiés comme décrit dans [Configuration des comptes d’importation et d’exportation cloud](/help/components/locations/configure-import-accounts.md) et [Configuration des emplacements d’importation et d’exportation cloud](/help/components/locations/configure-import-locations.md). La modification d’un compte ou d’un emplacement affecte tous les éléments associés à ce compte ou emplacement.

   Les versions antérieures du gestionnaire des flux de données vous permettaient de créer des destinations FTP, SFTP, S3 et Azure Blob. Les destinations créées dans ces versions antérieures du gestionnaire des flux de données ne peuvent pas être modifiées ni copiées.

1. Sélectionnez [!UICONTROL **Enregistrer**].

## Filtrer et rechercher la liste des flux de données

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Utilisez la recherche ou les filtres pour localiser un flux spécifique.

   * Dans le champ de recherche, commencez à saisir le nom d’un flux. Seuls les flux qui correspondent s’affichent dans la liste des flux disponibles.

   * Cliquez sur l’icône Filtrer située à l’extrême gauche pour afficher ou masquer les options de filtrage. Les filtres sont organisés par catégorie. Vous pouvez réduire ou développer des catégories de filtrage. Cochez la case en regard de tout filtre à appliquer.

![Filtrer](assets/filters.png)

## Affichage des tâches relatives aux flux de données

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Sélectionnez l’onglet [!UICONTROL **Tâches**] pour afficher les tâches individuelles créées par chacun de vos flux.

   Ou

   Pour afficher des tâches pour des flux de données spécifiques, cochez la case en regard d’un ou de plusieurs flux de données, puis sélectionnez [!UICONTROL **Historique des tâches**].

   Pour plus d’informations, voir [Gestion des tâches liées aux flux de données](df-manage-jobs.md).

## Copier un flux de données

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Cochez la case en regard du flux de données à copier, puis sélectionnez [!UICONTROL **Copier**].

   Cela vous permet de [créer un flux](create-feed.md) avec tous les paramètres du flux actuel. Cette option n’est pas visible si plusieurs flux de données sont sélectionnés.

   Lors de la mise à jour de la section [!UICONTROL **Destination**] pour un flux de données que vous copiez, vous pouvez choisir un compte et un emplacement différents à utiliser pour le nouveau flux de données dans les champs déroulants [!UICONTROL **Compte**] et [!UICONTROL **Emplacement**].

   Les comptes et emplacements peuvent être modifiés comme décrit dans [Configuration des comptes d’importation et d’exportation cloud](/help/components/locations/configure-import-accounts.md) et [Configuration des emplacements d’importation et d’exportation cloud](/help/components/locations/configure-import-locations.md). La modification d’un compte ou d’un emplacement affecte tous les éléments associés à ce compte ou emplacement.

   Les versions antérieures du gestionnaire des flux de données vous permettaient de créer des destinations FTP, SFTP, S3 et Azure Blob. Les destinations créées dans ces versions antérieures du gestionnaire des flux de données ne peuvent pas être modifiées ni copiées.

## Mettre en pause un flux de données

Lorsque vous mettez en pause un flux de données, il arrête le traitement du flux et définit son statut sur [!UICONTROL Inactif].

Lorsque vous réactivez le flux après l’avoir mis en pause, les données pendant la période de pause du flux sont traitées pour les flux de renvoi, mais pas pour les flux actifs. Pour plus d’informations, voir [Activer un flux de données](#activate-a-data-feed).

Pour suspendre un flux de données :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Cochez la case en regard du flux de données à suspendre, puis sélectionnez [!UICONTROL **Pause**].

## Activer un flux de données

Vous pouvez activer les flux inactifs.

Lorsqu’un flux est réactivé, les données peuvent ne pas être traitées automatiquement pendant la période d’inactivité du flux. Le traitement des données dépend s’il s’agit d’un flux de renvoi ou d’un flux dynamique :

* **Les flux de renvoi** (flux qui traitent uniquement des données historiques) reprennent le traitement des données à partir de l’endroit où ils se sont arrêtés, en renvoyant les dates si nécessaire.

* **Flux en direct** reprenez le traitement des données à partir du moment où elles sont activées. Cela signifie que les données ne sont pas traitées pendant la durée de mise en pause du flux par rapport à sa date d’activation. Si vous avez besoin des données pendant cette période, vous devez configurer un renvoi.

Pour activer un flux de données :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Cochez la case en regard du flux de données inactif que vous souhaitez activer, puis sélectionnez [!UICONTROL **Activer**].

## Suppression d’un flux de données

Lorsque vous supprimez un flux de données, son statut est défini sur [!UICONTROL Supprimé]. Les flux de données doivent avoir le statut Actif pour pouvoir être supprimés.

Pour supprimer un flux de données :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Cochez la case en regard du flux de données à supprimer, puis sélectionnez [!UICONTROL **Supprimer**].

## Configurer les colonnes dans le gestionnaire des flux de données

Chaque flux créé affiche plusieurs colonnes fournissant des informations la concernant. Sélectionnez un en-tête de colonne pour le trier par ordre croissant. Sélectionnez à nouveau un en-tête de colonne pour le trier par ordre décroissant. Si vous ne pouvez pas voir une colonne spécifique, cliquez sur l’icône de colonne en haut à droite.

![Icône Colonne](assets/cols.jpg)

Les colonnes suivantes sont disponibles :

* **Nom du flux** : colonne obligatoire. Affiche le nom du flux.
* **Identifiant du flux** : affiche l’identifiant du flux, un identifiant unique.
* **Suite de rapports** : la suite de rapports à partir de laquelle le flux référence les données.
* **Identifiant de suite de rapports** : identifiant unique de la suite de rapports.
* **Colonnes de données** : les colonnes de données actives pour le flux. Dans la plupart des cas, il y a trop de colonnes à afficher dans ce format.
* **Intervalle** : indique si le flux est horaire ou quotidien.
* **Type de destination** : le type de destination du flux. Par exemple, Amazon S3, GCP ou Azure.
* **Hôte de destination** : emplacement où le fichier est placé.
* **Propriétaire** : compte d’utilisateur qui a créé le flux.
* **Statut** : le statut du flux.
   * Actif : le flux est opérationnel.
   * En attente d’approbation : dans certaines circonstances, un flux nécessite l’approbation d’Adobe avant de pouvoir commencer à générer des tâches.
   * Supprimé : le flux est supprimé.
   * Terminé : le flux a terminé le traitement. Un flux terminé peut être modifié, mis en attente ou annulé.
   * En attente : le flux est créé, mais n’est pas encore actif. Les flux restent dans cet état pendant une courte période de transition.
   * Inactif : équivaut à un état « en pause » ou « en attente ». Pour plus d’informations sur ce qui se passe avec les flux de renvoi et les flux actifs lorsqu’un flux inactif est réactivé, voir [&#x200B; Activer un flux de données &#x200B;](#activate-a-data-feed).
* **Dernière modification** : la date à laquelle le flux a été modifié pour la dernière fois. La date et l’heure s’affichent dans le fuseau horaire de la suite de rapports avec décalage GMT.
* **Date de début** : la date de la première tâche pour ce flux. La date et l’heure s’affichent dans le fuseau horaire de la suite de rapports avec décalage GMT.
* **Date de fin** : la date de la dernière tâche pour ce flux. Les flux de données continus ne possèdent pas de date de fin.

