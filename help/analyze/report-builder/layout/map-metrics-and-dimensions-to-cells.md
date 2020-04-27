---
description: Avant de commencer le mappage des éléments sur la feuille de calcul, assurez-vous que cette dernière n’est pas protégée. Si le schéma de protection de votre feuille de calcul empêche toute opération de l’utilisateur, il vous sera impossible d’y sélectionner des cellules. Commencez par annuler la protection de la feuille, puis ajoutez des mappages de cellules.
title: Mappage de mesures et de dimensions avec des cellules
topic: Report builder
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mappage de mesures et de dimensions avec des cellules

Avant de commencer le mappage des éléments sur la feuille de calcul, assurez-vous que cette dernière n’est pas protégée. Si le schéma de protection de votre feuille de calcul empêche toute opération de l’utilisateur, il vous sera impossible d’y sélectionner des cellules. Commencez par annuler la protection de la feuille, puis ajoutez des mappages de cellules.

Le nombre de zones et de cellules à mapper varie en fonction de la mesure sélectionnée, de la granularité, de la plage de dates, ainsi que des filtres définis. Par exemple, si vous sélectionnez [!UICONTROL Site Metric] > [!UICONTROL Traffic Report], définissez [!UICONTROL Week] la granularité et définissez la plage de dates [!UICONTROL Last 2 Weeks], vous êtes invité à mapper trois cellules (lors de l’utilisation [!UICONTROL Custom Layout]) sur le [!UICONTROL Request Wizard: Step 2]. La requête récupère les données de la semaine 1 et de la semaine 2, où chaque valeur de point de données est égale à la valeur d’une page vue. Your third cell serves as the row heading, which you can configure using [!UICONTROL Format Options].

Si vous mappez, par erreur, des emplacements incompatibles sur la feuille de calcul, le Créateur de rapports génère une erreur.

Les sections suivantes comprennent davantage d’informations :

* [Sélection d’une plage de cellules ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Techniques de sélection des cellules ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problèmes en cours de mappage ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Sélection d’une plage de cellules {#section_1E37FB46DA194FB7A1050B8833A48AC6}

On the [!UICONTROL Request Wizard: Step 2], when you enable [!UICONTROL Custom Layout] for a trended request, you can map the request to a range of cells.

Cliquez sur **[!UICONTROL Range Selector]** ![select_cell_icon.png](assets/select_cell_icon.png)

en regard de l’élément que vous souhaitez mapper.

* **Toutes les cellules dans la plage :** Vous oblige à sélectionner un groupe de cellules pour une requête de [!UICONTROL Custom Layout] style.
* **Première cellule de la plage :** Permet de sélectionner la cellule supérieure gauche de la plage et d’afficher l’ [!UICONTROL Range] orientation pour spécifier l’orientation horizontale ou verticale des cellules d’entrée et de sortie (colonne ou ligne). Utilisez cette option si vous souhaitez que le Créateur de rapports sélectionne les cellules à votre place.
* **Orientation de plage** : cette option permet d’orienter les plages de cellules sous la forme de colonnes ou de lignes.
* **Sélectionnez l’emplacement de la cellule supérieure de la plage** : affiche les références de cellule.

## Techniques de sélection des cellules {#section_760421C3D7F84D67A639174710C93B22}

You select the data by clicking the **[!UICONTROL Range Selection]** icon  ![select_cell_icon.png](assets/select_cell_icon.png)

et, tout en maintenant le bouton de la souris enfoncé, faites glisser le pointeur sur la plage de cellules de votre choix. Une sélection continue est indiquée par une bordure noire.

![](assets/twenty_cells.gif)

Dans le cas d’une sélection composée de lignes distinctes, chaque ligne est entourée par une fine bordure blanche.

![](assets/twoXten_cells_highlighted.gif)

To map separate rows in one request, use the [!UICONTROL Control] key, then click and drag the cursor over the desired cells. Vous procéderez de la sorte si votre requête nécessite quatre zones composées, chacune, de 10 cellules, plutôt qu’une zone continue de 40 cellules.

![](assets/map4.png)

Après avoir sélectionné des cellules, cliquez de **[!UICONTROL Range Selector]** nouveau sur le [!UICONTROL Range Selection] formulaire pour revenir au [!UICONTROL Request Wizard: Step 2].

## Problèmes en cours de mappage {#section_CC1BCF841291447EB3A994EB08F3A099}

Si vous effectuez, à tort, un mappage sur une cellule qui comporte déjà un mappage actif, vous constaterez qu’aucune référence de cellule n’est affichée dans la zone de texte en regard de l’icône du Sélecteur de plage. Lorsque vous cliquez sur [!UICONTROL OK], le Créateur de rapports affiche l’erreur « La plage sélectionnée chevauche une autre plage de la requête. Veuillez modifier votre sélection. »

* If you still need to use the cell, right-click on the desired cell or cells, and select **[!UICONTROL Delete Request]**.

Deux méthodes peuvent être utilisées pour éviter l’affichage de ce message :

* Planifiez le format du rapport en ajoutant une mise en forme aux cellules qui comportent des requêtes et des mappages.
* Testez les zones de la feuille de calcul contenant des mappages.

Pour tester les zones présentant des requêtes incorporées, vous pouvez procéder comme suit :

* Launch the [!UICONTROL Request Manager] and click on individual requests listed in the table. Si vous cliquez sur une requête, les cellules de la feuille de calcul où elle est mappée sont mises en surbrillance.
* Select cells in the spreadsheet you intend to use for a new mapping and click [!UICONTROL From Sheet]. The [!UICONTROL Request Manager] selects the request in the list which has an output item that intersects the selected cell. Si aucune requête n’est sélectionnée, la cellule est disponible.
* Select cells in the spreadsheet, right-click in the context menu and verify if [!UICONTROL Edit Request] is available. Si elle l’est, cela signifie qu’une requête est associée à ces cellules.
