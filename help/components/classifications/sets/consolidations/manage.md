---
title: Gestionnaire de consolidation d’ensemble de classification
description: Consolidation d’un ou de plusieurs jeux de classifications dans un seul jeu de classifications.
exl-id: 032e93f6-9c11-4522-a02e-376eb4fd98bf
feature: Classifications
source-git-commit: c697530103ea7cd279cc3560c1daec796759e7a1
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# Gestionnaire de consolidation des ensembles de classifications

Si plusieurs jeux de classifications contiennent des données similaires, vous pouvez les consolider en un seul jeu de classifications. Lorsque vous consolidez plusieurs jeux de classifications, Adobe génère un nouveau jeu de classifications contenant toutes les données de classification de chaque jeu de classifications. Les consolidations sont utiles lorsque vous avez chargé des données dans de nombreuses suites de rapports ou dimensions qui contiennent les mêmes données de classification et que vous souhaitez les fusionner dans un seul workflow.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Consolidation]**

Une fois une consolidation exécutée, les jeux de classifications d’origine sont supprimés, le jeu de classifications consolidé prenant leur place. Cliquez sur **[!UICONTROL Ajouter]** to [Créer une consolidation](process.md).

## Filtrage des jeux de classifications

Le côté gauche du gestionnaire de consolidation des jeux de classifications fournit des paramètres de filtre pour localiser la consolidation souhaitée. Cliquez sur l’icône de filtre pour faire apparaître les paramètres de filtre. Vous pouvez filtrer les consolidations par **[!UICONTROL État]**, **[!UICONTROL Heure de fin]** ou **[!UICONTROL Temps de création]**.

![Filtres de consolidation des jeux de classifications](../../assets/classification-set-consolidation-filters.png)

D’autres options de filtre sont disponibles au-dessus des colonnes du gestionnaire de consolidation du jeu de classifications :

* **[!UICONTROL Recherche par titre]**: Recherchez des consolidations par nom.
* **Afficher/masquer les colonnes**: Activer/désactiver la visibilité de n’importe quelle colonne en plus de [!UICONTROL Nom].

## Colonnes du gestionnaire de consolidation des jeux de classifications

Les colonnes suivantes sont disponibles dans le gestionnaire de consolidation des jeux de classifications :

* **[!UICONTROL Nom]**: Nom de la consolidation.
* **[!UICONTROL Traitement actuel]**: La tâche en cours. <!-- todo: better description -->
* **[!UICONTROL État]**: Etat de la consolidation. <!-- todo: get list of possible statuses -->
* **[!UICONTROL Date de création]**: Date et heure de création de la consolidation.
* **[!UICONTROL Date d’achèvement]**: Date et heure auxquelles la consolidation s’est terminée (ou a échoué).
