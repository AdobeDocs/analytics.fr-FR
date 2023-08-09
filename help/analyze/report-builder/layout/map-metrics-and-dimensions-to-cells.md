---
description: Découvrez comment sélectionner une plage de cellules, des techniques de sélection des cellules et résoudre les problèmes de mappage.
title: En savoir plus sur le mappage des mesures et des dimensions aux cellules
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
feature: Report Builder
role: User, Admin
exl-id: e63fc679-39eb-417b-9a2b-6620db63a824
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 72%

---

# Mappage de mesures et de dimensions avec des cellules

Avant de commencer le mappage des éléments sur la feuille de calcul, assurez-vous que cette dernière n’est pas protégée. Si le schéma de protection de votre feuille de calcul empêche toute opération de l’utilisateur, il vous sera impossible d’y sélectionner des cellules. Commencez par annuler la protection de la feuille, puis ajoutez des mappages de cellules.

Le nombre de zones et de cellules à mapper varie en fonction de la mesure sélectionnée, de la granularité, de la période et des filtres définis. Par exemple, si vous sélectionnez [!UICONTROL Mesure du site] > [!UICONTROL Rapport Trafic], définit [!UICONTROL Semaine] et définissez la plage de dates pour la variable [!UICONTROL 2 dernières semaines], vous êtes invité à mapper trois cellules (lors de l’utilisation de la fonction [!UICONTROL Disposition personnalisée]) sur le [!UICONTROL Assistant Requête : Étape 2]. La requête récupère les données de la semaine 1 et celles de la semaine 2, où chaque valeur de point de données est égale à la valeur d’une page vue. Votre troisième cellule fait office d’en-tête de ligne, que vous pouvez configurer à l’aide des [!UICONTROL Options de format].

Si vous mappez par erreur des emplacements incompatibles sur la feuille de calcul, Report Builder génère une erreur.

Pour plus d’informations, reportez-vous aux sections suivantes :

* [Sélection d’une plage de cellules ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Techniques de sélection des cellules ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problèmes en cours de mappage ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Sélection d’une plage de cellules {#section_1E37FB46DA194FB7A1050B8833A48AC6}

Sur le formulaire [!UICONTROL Assistant Requête : Étape 2], lorsque vous activez [!UICONTROL Disposition personnalisée] pour une requête de tendance, vous pouvez la mapper sur une plage de cellules.

Cliquez sur le **[!UICONTROL Sélecteur de plage]** ![select_cell_icon.png](assets/select_cell_icon.png) en regard de l’élément que vous souhaitez mapper.

* **Toutes les cellules dans la plage** : cette option exige que vous sélectionniez un groupe de cellules pour une requête de type [!UICONTROL Disposition personnalisée].
* **Première cellule de la plage** : cette option permet de sélectionner la cellule supérieure gauche de la plage. Elle affiche également l’orientation [!UICONTROL Plage] afin d’indiquer l’orientation horizontale ou verticale des cellules d’entrée et de sortie (colonne ou ligne). Utilisez cette option pour que le Report Builder sélectionne les cellules à votre place.
* **Orientation de plage** : cette option permet d’orienter les plages de cellules sous la forme de colonnes ou de lignes.
* **Sélectionnez l’emplacement de la cellule supérieure de la plage** : affiche les références de cellule.

## Techniques de sélection des cellules {#section_760421C3D7F84D67A639174710C93B22}

Pour sélectionner les données, cliquez sur l’icône **[!UICONTROL Sélection de plages]** ![select_cell_icon.png](assets/select_cell_icon.png)

et, tout en maintenant le bouton de la souris enfoncé, faites glisser le pointeur sur la plage de cellules de votre choix. Une sélection continue est indiquée par une bordure noire.

![](assets/twenty_cells.gif)

Dans le cas d’une sélection composée de lignes distinctes, chaque ligne est entourée par une fine bordure blanche.

![](assets/twoXten_cells_highlighted.gif)

Pour mapper des lignes distinctes dans une seule requête, appuyez sur la touche [!UICONTROL Ctrl], puis cliquez et faites glisser le curseur sur les cellules de votre choix. Vous procéderez de la sorte si votre requête nécessite quatre zones composées, chacune, de 10 cellules, plutôt qu’une zone continue de 40 cellules.

![](assets/map4.png)

Après avoir sélectionné les cellules, cliquez à nouveau sur le **[!UICONTROL Sélecteur de plage]** sur le formulaire [!UICONTROL Sélection de plages] afin de revenir au formulaire [!UICONTROL Assistant Requête : Étape 2].

## Résolution des problèmes de mappage{#section_CC1BCF841291447EB3A994EB08F3A099}

Si vous choisissez par erreur de mapper à une cellule qui dispose déjà d’un mappage principal, aucune référence de cellule n’apparaît dans la zone de texte en regard de l’icône de sélecteur de plage. Lorsque vous cliquez [!UICONTROL OK], Report Builder affiche l’erreur, *La plage sélectionnée chevauche une autre plage de la requête. Veuillez modifier votre sélection.*

* Le cas échéant, cliquez avec le bouton droit sur la ou les cellules de votre choix, puis sélectionnez **[!UICONTROL Supprimer la requête]**.

Deux méthodes peuvent être utilisées pour éviter l’affichage de ce message :

* Planifiez le format du rapport en ajoutant une mise en forme aux cellules qui comportent des requêtes et des mappages.
* Testez les zones de la feuille de calcul contenant des mappages.

Pour tester les zones présentant des requêtes incorporées, vous pouvez procéder comme suit :

* Lancez le [!UICONTROL Gestionnaire de requêtes] et cliquez sur les différentes requêtes répertoriées dans le tableau. Si vous cliquez sur une requête, les cellules de la feuille de calcul où elle est mappée sont mises en surbrillance.
* Sélectionnez des cellules dans la feuille de calcul que vous avez l’intention d’utiliser pour un nouveau mappage, puis cliquez sur [!UICONTROL De la feuille]. Le [!UICONTROL Gestionnaire de requêtes] sélectionne, dans la liste, la requête dont un élément de sortie chevauche la cellule sélectionnée. Si aucune requête n’est sélectionnée, la cellule est disponible.
* Sélectionnez des cellules dans la feuille de calcul, cliquez avec le bouton droit dans le menu contextuel et vérifiez si l’option [!UICONTROL Modifier la requête] est disponible. Si elle l’est, cela signifie qu’une requête est associée à ces cellules.
