---
title: Interface utilisateur du flux de données
description: Découvrez comment naviguer dans l’interface de flux de données.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 68%

---

# Gestion des flux de données

Le gestionnaire des flux de données vous permet de créer, de modifier et de supprimer des flux de données pour votre entreprise. Si vous disposez d’autorisations pour accéder au gestionnaire des flux de données, vous pouvez gérer les flux de données pour toutes les suites de rapports qui s’affichent.

Regardez une vidéo sur l’interface utilisateur de la gestion des flux de données :

>[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

Pour accéder à la gestion des flux de données, procédez comme suit :

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Sélectionnez l’icône de 9 carrés dans le coin supérieur droit, puis sélectionnez [!UICONTROL **Analytics**].
1. Dans la barre de navigation supérieure, accédez à [!UICONTROL **Administration**] > [!UICONTROL **Flux de données**].

## Navigation dans l’interface

Lorsque vous atteignez la page du gestionnaire des flux de données, l’interface ressemble beaucoup à ce qui suit :

![Flux de données](assets/feeds.png)

Si aucun flux n’a été défini, la page affiche un bouton [!UICONTROL Créer un flux de données].

### Filtres et recherches

Utilisez la recherche ou les filtres pour localiser un flux spécifique.

* Dans le champ de recherche, commencez à saisir le nom d’un flux. Seuls les flux qui correspondent s’affichent dans la liste des flux disponibles.

* Cliquez sur l’icône Filtrer située à l’extrême gauche pour afficher ou masquer les options de filtrage. Les filtres sont organisés par catégorie. Vous pouvez réduire ou développer des catégories de filtrage. Cochez la case en regard d’un filtre que vous souhaitez appliquer.

  ![Filtrer](assets/filters.png)

### Flux et tâches

Sélectionnez la variable [!UICONTROL **Tâches**] pour afficher les tâches individuelles créées par chacun de vos flux. Voir [Gestion des tâches relatives aux flux de données](df-manage-jobs.md).

### Ajouter

La variable [!UICONTROL Ajouter] vous permet de créer un nouveau flux. Voir [Création d’un flux de données](create-feed.md) pour plus d’informations.

### Colonnes

Chaque flux créé affiche plusieurs colonnes fournissant des informations la concernant. Sélectionnez un en-tête de colonne pour le trier par ordre croissant. Sélectionnez à nouveau un en-tête de colonne pour le trier dans l’ordre décroissant. Si vous ne pouvez pas afficher une colonne spécifique, cliquez sur l’icône de colonne en haut à droite.

![Icône Colonne](assets/cols.jpg)

* **Nom du flux** : colonne requise. Affiche le nom du flux.
* **Identifiant du flux** : affiche l’identifiant du flux, un identifiant unique.
* **Suite de rapports** : la suite de rapports que le flux donne en référence pour ses données.
* **Identifiant de la suite de rapports** : l’identifiant unique de la suite de rapports.
* **Colonnes de données** : les colonnes de données actives pour le flux. Dans la plupart des cas, il y a trop de colonnes à afficher dans ce format.
* **Intervalle** : indique si le flux est horaire ou quotidien.
* **Type de destination** : le type de destination du flux. Par exemple, Amazon S3, GCP ou Azure.
* **Hôte de destination**: emplacement du fichier.
* **Propriétaire** : compte d’utilisateur qui a créé le flux.
* **Statut** : le statut du flux.
   * Actif : le flux est opérationnel.
   * En attente d’approbation : dans certaines circonstances, un flux nécessite l’approbation d’Adobe avant de pouvoir commencer à générer des tâches.
   * Supprimé : le flux est supprimé.
   * Terminé : le flux a terminé le traitement. Un flux terminé peut être modifié, mis en attente ou supprimé.
   * En attente : le flux est créé, mais n’est pas encore actif. Les flux restent dans cet état pendant une courte période de transition.
   * Inactif : équivaut à un état « en pause » ou « en attente ». Si un flux de renvoi (un flux qui ne traite que les données historiques) est réactivé, il reprend la diffusion des tâches à partir de l’arrêt. Si un flux actif est réactivé, il reprend la diffusion des tâches à partir du moment où il s’est arrêté.
* **Dernière modification** : la date à laquelle le flux a été modifié pour la dernière fois. La date et l’heure s’affichent dans le fuseau horaire de la suite de rapports en tenant compte du décalage par rapport à GMT.
* **Date de début** : la date de la première tâche pour ce flux. La date et l’heure s’affichent dans le fuseau horaire de la suite de rapports en tenant compte du décalage par rapport à GMT.
* **Date de fin** : la date de la dernière tâche pour ce flux. Les flux de données continus ne possèdent pas de date de fin.

## Action des flux de données

Cochez la case en regard d’un flux de données pour afficher les actions possibles.

* **Historique des tâches** : affiche toutes les tâches liées à ces flux de données. Vous emmène automatiquement à l’[interface de gestions des tâches](df-manage-jobs.md).
* **Supprimer** : supprime le flux de données et définit son statut sur [!UICONTROL Supprimé].
* **Copier** : vous permet de [créer un nouveau flux](create-feed.md) avec tous les paramètres du flux actuel. Si plusieurs flux sont sélectionnés, il n’est pas possible de copier.
* **Pause** : arrête le traitement de ce flux et définit son statut sur [!UICONTROL Inactif].
* **Activer** : disponible uniquement pour les flux inactifs. Les flux de renvoi (flux qui traitent uniquement les données historiques) reprennent le traitement des données là où ils se sont arrêtés, renvoyant les dates si nécessaire. Les flux en direct reprennent le traitement des données à l’heure actuelle.
