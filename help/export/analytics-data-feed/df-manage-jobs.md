---
title: Gestion des tâches de flux de données
description: Découvrez comment gérer des tâches individuelles dans des flux de données.
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Gestion des tâches de flux de données

Les tâches sont des tâches individuelles qui génèrent un fichier compressé. Ils sont créés et gérés par des flux.

Accédez à la gestion des tâches du flux de données en procédant comme suit :

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com).
2. Cliquez sur le menu à 9 grilles dans le coin supérieur droit, puis sur [!UICONTROL Analytics].
3. Dans le menu supérieur, cliquez sur [!UICONTROL Admin] &gt; Flux de [!UICONTROL données].
4. Cliquez sur l’onglet Tâches en haut de l’écran.

![Menu du flux de données](assets/AdminMenu.png)

## Navigation dans l’interface

Une tâche de flux de données est une instance unique où Adobe traite et génère un fichier compressé pour une fenêtre de rapport donnée. Le gestionnaire de tâches offre une vue améliorée de l’état des tâches individuelles.

![liés aux tâches](assets/jobs.jpg)

### Filtres et recherche

Utilisez les filtres et recherchez pour localiser exactement la tâche que vous recherchez.

A l’extrême gauche, cliquez sur l’icône de filtre pour afficher ou masquer les options de filtrage. Les filtres sont organisés par catégorie. Cliquez sur le chevron pour réduire ou développer les catégories de filtrage. Cochez la case pour appliquer ce filtre.

![Filtrer](assets/jobs-filter.jpg)

Utilisez la recherche pour localiser une tâche par son nom.

![Recherche](assets/search.jpg)

### Flux et tâches

Cliquez sur l’onglet Flux pour afficher les flux globaux qui créent ces tâches. See [Manage data feeds](df-manage-feeds.md).

### Colonnes

Chaque tâche affiche plusieurs colonnes fournissant des informations à son sujet. Cliquez sur un en-tête de colonne pour le trier par ordre croissant. Cliquez à nouveau sur un en-tête de colonne pour le trier dans l’ordre décroissant. Si une colonne spécifique n’est pas visible, cliquez sur l’icône de colonne en haut à droite.

![Icône Colonne](assets/job-cols.jpg)

* **ID** du flux : Affiche l’identifiant du flux, un identifiant unique. Les tâches créées par le même flux ont le même ID de flux.
* **ID** de tâche : Identifiant unique de la tâche. Toutes les tâches ont un ID de tâche différent.
* **Nom** du flux : Colonne obligatoire. Affiche le nom du flux. Les tâches créées par le même flux portent le même nom de flux.
* **Report Suite**: La suite de rapports à partir de laquelle la tâche fait référence aux données.
* **Identifiant** de suite de rapports : Identifiant unique de la suite de rapports.
* **Heure** de début : Heure à laquelle la tâche a commencé. La date et l’heure sont affichées dans le fuseau horaire de la suite de rapports avec décalage GMT. Les flux quotidiens commencent généralement vers minuit dans le fuseau horaire de la suite de rapports.
* **État**: Etat du flux.
   * En attente de données : La tâche est opérationnelle et les données de la fenêtre de rapport sont en cours de collecte.
   * Traitement : La tâche crée les fichiers de données et se prépare à les envoyer.
   * Terminé : La tâche s'est terminée sans aucun problème.
   * Échec : La tâche n'a pas été terminée. Voir [Dépannage des tâches](jobs-troubleshooting.md) pour déterminer la cause de l’échec.
   * En attente d’exportation : Les données de la fenêtre de création de rapports n'ont pas encore été entièrement traitées.
   * Aucune donnée : La suite de rapports ne contient aucune donnée pour la fenêtre de rapport demandée.
* **Heure** de fin : Heure à laquelle le travail a été terminé. La date et l’heure sont affichées dans le fuseau horaire de la suite de rapports avec décalage GMT.
* **Date** demandée : Fenêtre de création de rapports du fichier. Les flux quotidiens affichent généralement de 00:00 à 23:59 avec un décalage GMT, indiquant un jour complet en fonction du fuseau horaire de la suite de rapports. Les flux horaires indiquent l’heure de la tâche.
