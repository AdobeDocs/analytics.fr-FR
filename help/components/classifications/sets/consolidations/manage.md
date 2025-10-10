---
title: Gestionnaire de consolidation d’ensemble de classification
description: Consolidez un ou plusieurs ensembles de classifications en un seul ensemble de classifications.
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 6%

---

# Gestionnaire de consolidations de jeux de classifications

Si plusieurs ensembles de classifications contiennent des données similaires, vous pouvez les consolider en un seul ensemble de classifications. Lorsque vous consolidez plusieurs ensembles de classifications, Adobe génère un nouvel ensemble de classifications qui contient toutes les données de classification de chaque ensemble de classifications. Les consolidations sont utiles lorsque vous avez chargé des données vers de nombreuses suites de rapports ou dimensions contenant les mêmes données de classification et que vous souhaitez les fusionner dans un seul workflow. Vous devez disposer d’un accès administrateur de produit pour Adobe Analytics afin de voir le gestionnaire de consolidation des ensembles de classifications.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Consolidations]**

Une fois une consolidation exécutée, les ensembles de classifications d’origine sont supprimés, et l’ensemble de classifications consolidé prend leur place. Cliquez sur **[!UICONTROL Ajouter]** pour [Créer une consolidation](process.md).

## Filtrer des ensembles de classifications

Le côté gauche du gestionnaire de consolidation des ensembles de classifications fournit des paramètres de filtre permettant de localiser la consolidation souhaitée. Cliquez sur l’icône de filtre pour afficher ou masquer les paramètres de filtre. Vous pouvez filtrer les consolidations par **[!UICONTROL Statut]**, **[!UICONTROL Heure de fin]** ou **[!UICONTROL Heure de création]**.

![Filtres de consolidation des ensembles de classifications](../../assets/classification-set-consolidation-filters.png)

D’autres options de filtre sont disponibles au-dessus des colonnes du gestionnaire de consolidation des ensembles de classifications :

* **[!UICONTROL Rechercher par titre]** : recherchez des consolidations par nom.
* **Afficher/masquer les colonnes** : activez ou désactivez la visibilité de n’importe quelle colonne en plus de [!UICONTROL Nom].

## Colonnes du gestionnaire de consolidation des ensembles de classifications

Les colonnes suivantes sont disponibles dans le gestionnaire de consolidation des ensembles de classifications :

* **[!UICONTROL Nom]** : nom de la consolidation.
* **[!UICONTROL Tâche en cours]** : la tâche en cours. <!-- todo: better description -->
* **[!UICONTROL Statut]** : statut de la consolidation. <!-- todo: get list of possible statuses -->
* **[!UICONTROL Date de création]** : date et heure auxquelles la consolidation a été créée.
* **[!UICONTROL Date d’achèvement]** : date et heure auxquelles la consolidation s’est achevée (ou a échoué).
