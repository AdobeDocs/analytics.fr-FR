---
title: Gestionnaire des jeux de classificactions
description: Gérez les ensembles de classifications dans Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 7%

---

# Gestionnaire des jeux de classificactions

Le gestionnaire des ensembles de classifications vous permet de créer, modifier ou supprimer des ensembles de classifications.

**[!UICONTROL Composants]** > **[!UICONTROL Ensembles de classifications]** > **[!UICONTROL Ensembles]**

Les ensembles de classifications se composent d’**abonnements** (combinaisons de suites de rapports et de dimensions) et **Noms de classification** (dimensions contenant des données de classification). Les abonnements sont configurés sous [Paramètres](settings.md), tandis que les noms de classification sont configurés sous [Schéma](schema.md).

## Filtrer des ensembles de classifications

Le côté gauche du gestionnaire des ensembles de classifications fournit des paramètres de filtre pour localiser l’ensemble de classifications souhaité. Cliquez sur l’icône de filtre pour faire apparaître les paramètres de filtre. Vous pouvez filtrer les ensembles de classifications par **[!UICONTROL Balises]** ou **[!UICONTROL Suite de rapports]**.

![Filtres des ensembles de classifications](../../assets/classification-set-filters.png)

Notez que 1 000 ensembles de classifications sont préchargés à la fois. Les filtres affichés dans le rail de gauche reflètent les options des visionneuses préchargées.

## Colonnes du gestionnaire des ensembles de classifications

Les colonnes suivantes sont disponibles dans le gestionnaire des ensembles de classifications :

* **[!UICONTROL Ensemble de classifications]** : le nom de l’ensemble de classifications. Cliquez sur le nom d’un ensemble de classifications pour modifier ses [paramètres](settings.md).
* **[!UICONTROL Abonnements]** : le nombre d’abonnements auxquels cet ensemble de classifications s’applique.
* **[!UICONTROL Classifications]** : le nombre de dimensions de classification que l’ensemble de classifications contient.
* **[!UICONTROL Automatisé]** : détermine si l’ensemble de classifications est configuré pour importer automatiquement les données d’un emplacement cloud. L’automatisation peut être configurée dans le [ schéma ](schema.md) de l’ensemble de classifications.
* **[!UICONTROL Dernière modification]** : date et heure de la dernière modification de l’ensemble de classifications.

## Créer ou modifier des options

Les boutons suivants sont disponibles dans le Gestionnaire des ensembles de classifications :

* **[!UICONTROL Ajouter]** : [Créer](create.md) un ensemble de classifications.
* **[!UICONTROL Recherche par titre]** : recherchez des ensembles de classifications par nom.
* **[!UICONTROL Charger plus]** : le gestionnaire des ensembles de classifications affiche initialement jusqu’à 1 000 ensembles de classifications. Ce bouton charge 1 000 ensembles de classifications supplémentaires.
* **Afficher/masquer les colonnes** : activez la visibilité de n’importe quelle colonne à part [!UICONTROL Ensemble de classifications].

Sélectionnez un ou plusieurs ensembles de classifications en cliquant sur la case à cocher en regard de l’ensemble de classifications souhaité. La sélection d’un ensemble de classifications fait apparaître les options suivantes :

* **[!UICONTROL Balise]** : ajoutez une ou plusieurs balises aux ensembles de classifications sélectionnés, ce qui vous permet d’organiser ou de regrouper les ensembles de classifications afin de les retrouver plus facilement à l’avenir.
* **[!UICONTROL Supprimer]** : supprime l’ensemble de classifications. Les dimensions de classification basées sur cet ensemble de classifications ne sont plus disponibles. Les projets planifiés utilisant l’ensemble de classifications supprimé continuent à utiliser des dimensions dépendantes jusqu’à ce que vous réenregistriez le projet planifié.
* **[!UICONTROL Consolider]** : démarrez une nouvelle [consolidation](../consolidations/process.md).
* **[!UICONTROL Renommer]** : renommez l’ensemble de classifications sélectionné.
