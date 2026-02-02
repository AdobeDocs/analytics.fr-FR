---
title: Création D’Un Bloc De Données Dans Report Builder
description: Découvrez comment créer un bloc de données.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: fd3ff12a-14de-46f6-ab89-a0152fb11b0d
source-git-commit: ff1722416fe5062d16c12185d17271ebc2d6b624
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 20%

---

# Créer un bloc de données

Un *bloc de données* est le tableau de données créé par une requête de données unique. Un classeur Report Builder peut contenir plusieurs blocs de données. Lorsque vous créez un bloc de données, vous devez dʼabord le configurer avant de le créer.

## Configuration du bloc de données

Configurez les paramètres initiaux du bloc de données : son emplacement, la suite de rapports et une période.

1. Sélectionnez ![AjouterCercle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Créer]**.

   ![Capture d’écran affichant l’option Créer un bloc de données &#x200B;](./assets/create-data-block.png){zoomable="yes"}


1. Définissez lʼ&#x200B;**[!UICONTROL Emplacement du bloc de données]**.

   L&#39;option d&#39;emplacement des blocs de données définit l&#39;emplacement de la feuille de calcul où Report Builder ajoute les données à votre feuille de calcul.

   Pour spécifier l&#39;emplacement du bloc de données, sélectionnez une seule cellule dans la feuille de calcul ou saisissez une adresse de cellule, telle que `a3`, `\\\$a3`, `a\\\$3` ou `sheet1!a2`. La cellule spécifiée devient le coin supérieur gauche du bloc de données lors de la récupération des données.

   Utilisez ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) pour sélectionner un emplacement de bloc de données à partir de la cellule sélectionnée dans la feuille.

1. Choisissez l’option **[!UICONTROL Suites de rapports]**.

   L’option Suites de rapports vous permet de choisir une suite de rapports dans un menu déroulant ou de référencer une suite de rapports à partir d’un emplacement de cellule.

   Sélectionnez ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) pour créer une suite de rapports à partir d’une cellule.

1. Définissez la **[!UICONTROL Période]**.

   L’option **[!UICONTROL Période]** vous permet de choisir une période. Les périodes peuvent être fixes ou variables.

   Sélectionnez **[!UICONTROL Calendrier]** pour sélectionner une période à l’aide de ![Calendrier](/help/assets/icons/Calendar.svg) ou saisissez manuellement une période. Vous pouvez éventuellement sélectionner un paramètre prédéfini dans le menu déroulant **[!UICONTROL _Paramètres prédéfinis de recherche_]**.

   Sélectionnez **[!UICONTROL À partir de la cellule]** pour définir des données de début et de fin en fonction d&#39;une cellule de la feuille active.

   Pour plus d’informations sur les options de période, voir [&#x200B; Sélectionner une période &#x200B;](select-date-range.md).

1. Sélectionnez **[!UICONTROL Suivant]**.

   ![Capture d’écran affichant l’option de période et le bouton Suivant actif.](./assets/choose_date_data_view3.png)

   Une fois le bloc de données configuré, sélectionnez des dimensions, des mesures et des segments pour le créer. Les onglets **[!UICONTROL Dimensions]**, **[!UICONTROL Mesures]** et **[!UICONTROL Segments]** s’affichent au-dessus du volet **[!UICONTROL Tableau]**.

## Création du bloc de données

Pour créer le bloc de données, sélectionnez les composants du rapport et personnalisez leur disposition.

1. Ajoutez les composants **[!UICONTROL Dimensions]**, **[!UICONTROL Mesures]** et **[!UICONTROL Segments]**.

   Faites défiler les listes de composants ou utilisez le champ ![Rechercher](/help/assets/icons/Search.svg) **[!UICONTROL _Rechercher des composants_]** pour localiser les composants. Faites glisser et déposez des composants dans le volet [!UICONTROL Tableau] ou sélectionnez deux fois le nom d’un composant dans la liste pour l’ajouter au volet [!UICONTROL Tableau].

   Sélectionnez deux fois un composant pour l’ajouter à une section par défaut du tableau.

   - Les composants Dimension sont ajoutés à la section ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]** ou à la section ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]** si une dimension figure déjà dans les colonnes.
   - Les composants de date sont ajoutés à la section ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**.
   - Les composants de segment sont ajoutés à la section ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]**.
   - Les composants de mesures sont ajoutés à la section ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Valeurs]**.

1. Organisez les éléments dans le volet Tableau pour personnaliser la disposition de votre bloc de données.

   Faites glisser et déposez des composants dans chaque liste du volet Tableau pour réorganiser les composants ou sélectionnez ![PlusPetit](/help/assets/icons/MoreSmall.svg) et sélectionnez ![ArrowUp](/help/assets/icons/ArrowUp.svg) Déplacer vers le haut, ![ArrowDown](/help/assets/icons/ArrowDown.svg) Déplacer vers le bas, etc. pour déplacer les composants dans une liste.

   Lorsque vous ajoutez des composants au tableau, une prévisualisation du bloc de données sʼaffiche à lʼemplacement du bloc de données dans la feuille de calcul. La disposition de la prévisualisation du bloc de données est automatiquement mise à jour lorsque vous ajoutez, déplacez ou supprimez des éléments du tableau.

   ![Capture d’écran montrant les composants ajoutés et la feuille de calcul mise à jour.](./assets/image10.png)


1. Vous pouvez éventuellement définir la **[!UICONTROL Date de début]** en tant que dimension pour identifier la date de début de votre bloc de données. L’ajout des données de début en tant que dimension s’avère utile si vous disposez d’un rapport régulièrement planifié avec une période variable. Ou si vous disposez d’une période non conventionnelle et que vous devez être explicite sur la date de début.

   ![Capture d’écran affichant la date de début dans la liste des dimensions.](./assets/start-date-dimension.png)

1. Vous pouvez éventuellement afficher ou masquer les en-têtes de ligne et de colonne. Pour ce faire, procédez comme suit :

   1. Sélectionnez l’icône **[!UICONTROL Tableau]** ![Paramètre](/help/assets/icons/Setting.svg)paramètres .

      ![Capture d’écran affichant l’option Paramètres du tableau.](./assets/table-settings.png)

   1. Cochez ou désélectionnez l’option **[!UICONTROL Afficher les en-têtes de ligne et de colonne]**. Les en-têtes s’affichent par défaut.

1. Vous pouvez également masquer ou afficher les libellés de dimension et les en-têtes de mesure. Pour ce faire, procédez comme suit :

   1. Sélectionnez ![PlusPetit](/help/assets/icons/MoreSmall.svg) sur le libellé de la dimension ou l’en-tête de colonne pour afficher le menu contextuel.

      ![Icône représentant des points de suspension dans la section Ligne.](./assets/row-heading.png)

   1. Sélectionnez ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** ou ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** pour activer/désactiver le libellé de dimension ou l’en-tête de colonne. Tous les libellés sont affichés par défaut.

1. Sélectionnez **[!UICONTROL Terminer]** pour terminer la configuration de votre bloc de données.

1. Un message de traitement **[!UICONTROL #BUSY]** s’affiche lors de la récupération des données d’analyse.

   ![Message de traitement.](./assets/image11.png)

1. Report Builder récupère les données et affiche le bloc de données renseigné dans la feuille de calcul.

   ![Bloc de données terminé.](./assets/image12.png)


>[!MORELIKETHIS]
>
>[Sélectionnez une suite de rapports](select-report-suite.md)
>[Sélectionnez une période](select-date-range.md)
>[Filtrer les dimensions &#x200B;](filter-dimensions.md)
>[Utiliser les segments](work-with-segments.md)
>


<!--

A *data block* is the table of data created by a single data request. A Report Builder workbook can contain multiple data blocks. When you create a data block, first configure the data block and then build the data block.

## Configure the data block

Configure the initial data block parameters for the data block location, report suite, and a date range.

1. Click **[!UICONTROL Create]**.

    ![Screenshot showing the Create data block option.](./assets/create_db.png)

1. Set the **[!UICONTROL Data block location]**.

    The data block location option defines the worksheet location where report builder adds the data to your worksheet.

    To specify the data block location, select a single cell in the worksheet and click the icon next to **[!UICONTROL Data block location]**: 
    
    You can also enter a cell address such as a3, \\\$a3, a\\\$3 or sheet1!a2. The cell specified marks the upper-left corner of the data block when the data is retrieved.

1. Choose a **Report Suite**.

    The report suites option allows you to choose a report suite from a drop-down menu or to reference a report suite from a cell location.

1. Set the **[!UICONTROL Date range]**.

    The Date range option allows you to choose a date range. Date ranges may be fixed or rolling. For information about data range options, see [Select a Date Range](select-date-range.md).

1. Click **[!UICONTROL Next]**.

    ![Screenshot showing the date range option and the active Next button.](./assets/choose_date_report_suite.png)

    After you configure the data block, you can select dimensions, metrics, and segments to build your data block. The Dimensions, Metrics, and Filters tabs are displayed above the Table builder pane.

## Build the data block

To build the data block, select report components, and then customize the layout.

1. Add Dimensions, Metrics, and Segments.

    Scroll the component lists or use the **[!UICONTROL Search]** field to locate components. Drag and drop components to the Table pane or double-click a component name in the list to automatically add the component to the Table pane.

    Double-click a component to add it to a default section of the table.

    - Dimension components are added to the Row section or to the Column section if you have a dimension already in the columns.
    - Date components are added to the Column section.
    - Segment components are added to the Segments section.

    **Start date as a Dimension**

    Set the **[!UICONTROL Start date]** as a dimension to clearly identify the start date of your data block. This is helpful if you have a regularly scheduled report that has a rolling date range or if you have an unconventional date range and you need to be clear on the start date.

    ![Screenshot showing the Start date in the list of dimensions.](./assets/start-date-dimension.png){width="30%"}

1. Arrange the items in the Table pane to customize the layout of your data block.

    Drag and drop components in the Table pane to reorder components or right-click a component name and select from the options menu.

    When you add components to the table, a preview of the data block is displayed at the Data block location in the worksheet. The layout of the data block preview automatically updates as you add, move, or remove items in the table.

    ![Screenshot showing the added components and updated worksheet.](./assets/image10.png)

    **Display or hide row and column headers**

1. Click the **[!UICONTROL Table settings]** icon.

    ![Screenshot showing the Table settings option.](./assets/table-settings.png){width="35%"}

1. Check or uncheck the option to Display row and column headers. The headers are displayed by default.

    **Hide or show dimension labels and metric headers**

1. Click the ellipsis icon on either the dimensions or the column headers to display the settings.

    ![The ellipsis icon in the Row section.](./assets/row-heading.png){width="35%"}

1. Click Hide or Show to toggle the dimension labels or column headers. All labels are displayed by default.

1. Click **[!UICONTROL Finish]**.

    A processing message is displayed while the analytics data is retrieved.

    Report Builder retrieves the data and displays the completed data block in the worksheet.

    ![The completed data block.](./assets/image12.png)

-->