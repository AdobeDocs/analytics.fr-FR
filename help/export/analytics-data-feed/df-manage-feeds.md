---
title: Interface utilisateur du flux de données
description: Découvrez comment naviguer dans l’interface du flux de données.
translation-type: tm+mt
source-git-commit: c9b3471b138c2e056a5abadb4ace6bb4eccd1d72

---


# Gestion des flux de données

Le gestionnaire de flux de données vous permet de créer, de modifier et de supprimer des flux de données pour votre entreprise. Si vous êtes autorisé à accéder au gestionnaire de flux de données, vous pouvez gérer les flux de données pour toutes les suites de rapports qui vous sont visibles.

Accédez à la gestion des flux de données en procédant comme suit :

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com).
2. Cliquez sur le menu à 9 grilles dans le coin supérieur droit, puis sur [!UICONTROL Analytics].
3. Dans le menu supérieur, cliquez sur [!UICONTROL Admin] &gt; Flux de [!UICONTROL données].

![Menu du flux de données](assets/AdminMenu.png)

## Navigation dans l’interface

Lorsque vous accédez à la page du gestionnaire de flux de données, l’interface se présente comme suit :

![Flux de données](assets/feeds.png)

Si aucun flux n’a été défini, la page affiche un bouton [!UICONTROL Créer un flux de données].

### Filtres et recherches

Utilisez les filtres et recherchez le flux exact que vous recherchez.

A l’extrême gauche, cliquez sur l’icône de filtre pour afficher ou masquer les options de filtrage. Les filtres sont organisés par catégorie. Cliquez sur le chevron pour réduire ou développer les catégories de filtrage. Cochez la case pour appliquer ce filtre.

![Filtrer](assets/filters.jpg)

Utilisez la recherche pour localiser un flux par son nom.

![Recherche](assets/search.jpg)

### Flux et tâches

Cliquez sur l’onglet Tâches pour afficher les tâches individuelles créées par chacun de vos flux. Voir [Gestion des tâches](df-manage-jobs.md)de flux de données.

### Ajouter

Près des onglets Flux et Tâches, cliquez sur le bouton + [!UICONTROL Ajouter] pour créer un flux. Voir [Ajout d’un flux](create-feed.md) pour plus d’informations.

### Colonnes

Chaque flux créé affiche plusieurs colonnes fournissant des informations à son sujet. Cliquez sur un en-tête de colonne pour le trier par ordre croissant. Cliquez à nouveau sur un en-tête de colonne pour le trier dans l’ordre décroissant. Si une colonne spécifique n’est pas visible, cliquez sur l’icône de colonne en haut à droite.

![Icône Colonne](assets/cols.jpg)

* **Nom** du flux : Colonne obligatoire. Affiche le nom du flux.
* **ID** du flux : Affiche l’identifiant du flux, un identifiant unique.
* **Report Suite**: Suite de rapports à partir de laquelle le flux référence les données.
* **Identifiant** de suite de rapports : Identifiant unique de la suite de rapports.
* **Colonnes** de données : Quelles colonnes de données sont actives pour le flux ? Dans la plupart des cas, il y a trop de colonnes à afficher dans ce format.
* **Intervalle**: Indiquez si le flux est horaire ou quotidien.
* **Type** de destination : Type de destination du flux. Par exemple, FTP, Amazon S3 ou Azure.
* **Hôte** de destination : Emplacement du fichier. Par exemple : `ftp.example.com`.
* **Propriétaire**: Compte utilisateur qui a créé le flux.
* **État**: Etat du flux.
   * Actif : Le flux est opérationnel.
   * Approbation en attente : Dans certains cas, un flux doit être approuvé par Adobe avant de pouvoir commencer à générer des tâches.
   * Supprimé : Le flux est supprimé.
   * Terminé : Le flux a terminé son traitement. Un flux terminé peut être modifié, mis en attente ou annulé.
   * En attente : Le flux est créé mais pas encore actif. Les flux restent dans cet état pendant une courte période transitoire.
   * Inactif : Équivalent à un état "suspendu" ou "en attente". Lorsque le flux est réactivé, il reprend la livraison des tâches à partir du moment où il s’est arrêté.
* **Dernière modification**: date de la dernière modification du flux. La date et l’heure sont affichées dans le fuseau horaire de la suite de rapports avec décalage GMT.
* **Date** de début : Date de la première tâche pour ce flux. La date et l’heure sont affichées dans le fuseau horaire de la suite de rapports avec décalage GMT.
* **Date** de fin : Date de la dernière tâche pour ce flux. Les flux de données en cours n’ont pas de date de fin.

## Actions de flux de données

Cochez la case en regard d’un flux de données pour afficher les actions disponibles.

* **Historique** des tâches : Afficher toutes les tâches liées à ces flux de données. Vous conduit automatiquement à l’interface [de](df-manage-jobs.md)gestion des tâches.
* **Supprimer**: Supprime le flux de données, en définissant son état sur [!UICONTROL Supprimé].
* **Copier**: Vous permet de [créer un nouveau flux](create-feed.md) avec tous les paramètres du flux actuel. Vous ne pouvez pas copier un flux de données si plusieurs sont sélectionnés.
* **Pause**: Arrête le traitement du flux, en définissant son état sur [!UICONTROL Inactif].
* **Activer**: Disponible uniquement pour les flux inactifs. Récupère les données de traitement à l’endroit où elles ont été retirées, en renvoyant les dates si nécessaire.
