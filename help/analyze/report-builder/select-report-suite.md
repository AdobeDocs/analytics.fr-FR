---
title: Sélectionner Une Suite De Rapports Dans Report Builder
description: Découvrez comment sélectionner une suite de rapports dans Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 96e24d5d-78fb-4e5c-8513-c5fe221d0aeb
source-git-commit: 6f7de360ac24261eabb46c6cfce99449261706de
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 1%

---

# Sélectionnez une suite de rapports

Vous pouvez sélectionner une suite de rapports dans le menu déroulant ou sélectionner une suite de rapports dans une cellule et mettre automatiquement à jour votre bloc de données avec une nouvelle suite de rapports.

## Sélection d’une suite de rapports depuis une cellule

La sélection d’une suite de rapports dans une cellule facilite l’actualisation des blocs de données à l’aide de différentes suites de rapports. Au lieu de créer des rapports entièrement nouveaux avec des blocs de données distincts, vous pouvez actualiser les blocs de données avec une suite de rapports sélectionnée à partir d’une cellule.

La sélection d’une suite de rapports dans une cellule s’avère utile lorsque vous disposez des éléments suivants :

* Plusieurs suites de rapports dont la structure est similaire ou identique.
* Formats de blocs de données complexes comprenant des composants et des mises en page personnalisés.

Pour sélectionner une suite de rapports dans une cellule, commencez par créer un bloc de données et affectez plusieurs suites de rapports à une cellule à l’extérieur de votre bloc de données. Ensuite, utilisez le panneau **[!UICONTROL Suite de rapports depuis la cellule]** pour actualiser vos blocs de données à partir de différentes suites de rapports.

1. Créez un bloc de données. Pour plus d’informations sur la création d’un bloc de données, voir [Créer un bloc de données](/help/analyze/report-builder/create-a-data-block.md).

1. Sélectionnez ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) dans **[!UICONTROL Suites de rapports]**.

1. Sélectionnez une cellule à l’aide de ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) en dehors du bloc de données.

1. Ajoutez une ou plusieurs suites de rapports à partir de la **[!UICONTROL Sélectionner les suites de rapports à ajouter à la suite de rapports à partir de la cellule]** en procédant par glisser-déposer. Vous pouvez également sélectionner deux fois une suite de rapports pour l’ajouter à la liste **[!UICONTROL Suites de rapports incluses]**.

   * Vous pouvez utiliser ![Rechercher](/help/assets/icons/Search.svg) **[!UICONTROL _Sélectionner des suites de rapports_]** pour rechercher des suites de rapports.
   * Utilisez ![MoreSmall](/help/assets/icons/MoreSmall.svg) pour ouvrir un menu contextuel afin de déplacer les suites de rapports vers le haut ou vers le bas dans la liste **[!UICONTROL Suites de rapports incluses]**.
   * Utilisez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une suite de rapports de la liste **[!UICONTROL Suites de rapports incluses]**.

   ![Sélectionner une suite de rapports depuis une cellule](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer les suites de rapports sélectionnées à la cellule sélectionnée.


## Modification de la suite de rapports à partir d’une cellule

1. Sélectionnez l’emplacement de la cellule de la suite de rapports dans votre feuille.
1. Dans le hub Report Builder, cliquez sur le lien **[!UICONTROL Suites de rapports à partir de la cellule]** dans **[!UICONTROL Modification rapide]**.
1. Sélectionnez une suite de rapports dans le menu déroulant **[!UICONTROL Suite de rapports]**.

   ![Modifier la suite de rapports depuis une cellule](assets/change-data-view-from-cell.png){zoomable="yes"}
1. Facultatif, sélectionnez **[!UICONTROL Actualiser le(s) bloc(s) de données lors de la modification]**.

1. Sélectionnez **[!UICONTROL Appliquer]**. Report Builder actualise le bloc de données en fonction de la suite de rapports sélectionnée.
