---
title: Gestionnaire des jeux de classificactions
description: Gestion des jeux de classifications dans Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: 2b81c0df0e2bb68a73f9d24888758a433c6f5423
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 7%

---

# Gestionnaire des jeux de classificactions

Le gestionnaire des jeux de classifications vous permet de créer, de modifier ou de supprimer des jeux de classifications.

**[!UICONTROL Composants]** > **[!UICONTROL Ensembles de classifications]** > **[!UICONTROL Ensembles]**

Les jeux de classifications se composent de **Abonnements** (combinaisons de suite de rapports et de dimensions) et de **Noms de classification** (dimensions contenant des données de classification). Les abonnements sont configurés sous [Paramètres](settings.md), tandis que les noms de classification sont configurés sous [Schéma](schema.md).

## Filtrage des jeux de classifications

Le côté gauche du gestionnaire de jeux de classifications fournit des paramètres de filtre pour localiser le jeu de classifications souhaité. Cliquez sur l’icône de filtre pour faire apparaître les paramètres de filtre. Vous pouvez filtrer les jeux de classifications par **[!UICONTROL Balises]** ou **[!UICONTROL Suite de rapports]**.

![Filtres des ensembles de classifications](../../assets/classification-set-filters.png)

## Colonnes du gestionnaire de jeux de classifications

Les colonnes suivantes sont disponibles dans le gestionnaire de jeux de classifications :

* **[!UICONTROL Jeu de classifications]** : nom du jeu de classifications. Cliquer sur le nom d&#39;un jeu de classifications [modifie ses paramètres](settings.md).
* **[!UICONTROL Abonnements]** : nombre d’abonnements auxquels ce jeu de classifications s’applique.
* **[!UICONTROL Classifications]** : nombre de dimensions de classification contenues par le jeu de classifications.
* **[!UICONTROL Automatisé]** : détermine si le jeu de classifications est configuré pour importer automatiquement des données d’un emplacement cloud. L’automatisation peut être configurée dans le [schéma](schema.md) du jeu de classifications.
* **[!UICONTROL Dernière modification]** : date et heure de la dernière modification du jeu de classifications.

## Créer ou modifier des options

Les boutons suivants sont disponibles dans le Gestionnaire de jeux de classifications :

* **[!UICONTROL Ajouter]** : [Créer](create.md) un jeu de classifications.
* **[!UICONTROL Recherche par titre]** : recherchez des jeux de classifications par nom.
* **[!UICONTROL Charger plus]** : le gestionnaire des jeux de classifications affiche initialement jusqu’à 1 000 jeux de classifications. Ce bouton charge 1 000 jeux de classifications supplémentaires.
* **Afficher/masquer les colonnes** : basculez la visibilité de n’importe quelle colonne en plus du [!UICONTROL jeu de classifications].

Sélectionnez un ou plusieurs jeux de classifications en cochant la case en regard du jeu de classifications souhaité. La sélection d’un jeu de classifications fait apparaître les options suivantes :

* **[!UICONTROL Balise]** : ajoutez une ou plusieurs balises aux jeux de classifications sélectionnés, ce qui vous permet d’organiser ou de regrouper des jeux de classifications pour les rendre plus faciles à localiser à l’avenir.
* **[!UICONTROL Supprimer]** : supprime le jeu de classifications. Les dimensions de classification basées sur ce jeu de classifications ne sont plus disponibles. Les projets planifiés qui utilisent le jeu de classifications supprimé continuent à utiliser des dimensions dépendantes jusqu’à ce que vous réenregistrez le projet planifié.
* **[!UICONTROL Consolidation]** : commencez une nouvelle [consolidation](../consolidations/process.md).
* **[!UICONTROL Renommer]** : renommez le jeu de classifications sélectionné.
