---
title: Gestionnaire de consolidation d’ensemble de classification
description: Consolidation d’un ou de plusieurs jeux de classifications dans un seul jeu de classifications.
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 6%

---

# Gestionnaire de consolidations de jeux de classifications

Si plusieurs jeux de classifications contiennent des données similaires, vous pouvez les consolider en un seul jeu de classifications. Lorsque vous consolidez plusieurs jeux de classifications, Adobe génère un nouveau jeu de classifications contenant toutes les données de classification de chaque jeu de classifications. Les consolidations sont utiles lorsque vous avez chargé des données dans de nombreuses suites de rapports ou dimensions qui contiennent les mêmes données de classification et que vous souhaitez les fusionner dans un seul workflow. Pour qu’Adobe Analytics puisse voir le gestionnaire de consolidation du jeu de classifications, vous devez disposer d’un accès administrateur de produit.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Consolidation]**

Une fois une consolidation exécutée, les jeux de classifications d’origine sont supprimés, le jeu de classifications consolidé prenant leur place. Cliquez sur **[!UICONTROL Ajouter]** to [Créer une consolidation](process.md).

## Filtrage des jeux de classifications

Le côté gauche du gestionnaire de consolidation des jeux de classifications fournit des paramètres de filtre pour localiser la consolidation souhaitée. Cliquez sur l’icône de filtre pour faire apparaître les paramètres de filtre. Vous pouvez filtrer les consolidations par **[!UICONTROL État]**, **[!UICONTROL Heure de fin]**, ou **[!UICONTROL Temps de création]**.

![Filtres de consolidation des jeux de classifications](../../assets/classification-set-consolidation-filters.png)

D’autres options de filtre sont disponibles au-dessus des colonnes du gestionnaire de consolidation du jeu de classifications :

* **[!UICONTROL Recherche par titre]**: recherchez des consolidations par nom.
* **Afficher/masquer les colonnes**: activation/désactivation de la visibilité pour n’importe quelle colonne en plus de [!UICONTROL Nom].

## Colonnes du gestionnaire de consolidation des jeux de classifications

Les colonnes suivantes sont disponibles dans le gestionnaire de consolidation des jeux de classifications :

* **[!UICONTROL Nom]**: nom de la consolidation.
* **[!UICONTROL Tâche actuelle]**: tâche en cours. <!-- todo: better description -->
* **[!UICONTROL État]**: état de la consolidation. <!-- todo: get list of possible statuses -->
* **[!UICONTROL Date de création]**: date et heure de création de la consolidation.
* **[!UICONTROL Date d’achèvement]**: date et heure auxquelles la consolidation s’est terminée (ou a échoué).
