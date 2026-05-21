---
description: Découvrez comment sélectionner une plage de cellules, les techniques de sélection des cellules et la résolution des problèmes de mappage.
title: En savoir plus sur le mappage de mesures et de dimensions à des cellules
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
feature: Report Builder
role: User, Admin
exl-id: e63fc679-39eb-417b-9a2b-6620db63a824
TQID: https://experienceleague.adobe.com/yeU4gugMR2nSKwjo4LuX79spXIaD4UtuaTQ52bZwGrU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 676
ht-degree: 22%

---

# Mappage de mesures et de dimensions avec des cellules

{{legacy-arb}}

Avant de commencer à mapper des éléments à la feuille de calcul, assurez-vous que celle-ci n’est pas protégée. Si le schéma de protection de votre feuille de calcul empêche toute action de l&#39;utilisateur, vous ne pourrez pas sélectionner de cellules dans la feuille de calcul. Tout d&#39;abord, annulez la protection de la feuille, puis ajoutez des mappages de cellules.

Le nombre de zones et de cellules à mapper diffère en fonction de la mesure que vous sélectionnez, de la granularité, de la période et des filtres que vous définissez. Par exemple, si vous sélectionnez [!UICONTROL Mesure du site] > [!UICONTROL Rapport de trafic], définissez la granularité [!UICONTROL Semaine] et définissez la période pour les [!UICONTROL 2 dernières semaines], vous êtes invité à mapper trois cellules (lors de l’utilisation de [!UICONTROL Mise en page personnalisée]) sur l’assistant [!UICONTROL Requête : étape 2]. La requête récupère les données de la première semaine et les données de la deuxième semaine, où chaque valeur de point de données est égale à la valeur d’une page vue. Votre troisième cellule sert d’en-tête de ligne. Vous pouvez la configurer à l’aide des [!UICONTROL &#x200B; Options de format &#x200B;].

Si vous mappez par erreur des emplacements incompatibles sur la feuille de calcul, Report Builder génère une erreur.

Pour plus d’informations, consultez les sections suivantes :

* [Sélection d’une plage de cellules &#x200B;](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Techniques de sélection des cellules &#x200B;](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problèmes Lors Du Mappage](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Sélectionner une plage de cellules {#section_1E37FB46DA194FB7A1050B8833A48AC6}

Sur le formulaire [!UICONTROL Assistant Requête : Étape 2], lorsque vous activez [!UICONTROL Disposition personnalisée] pour une requête de tendance, vous pouvez la mapper sur une plage de cellules.

Cliquez sur le **[!UICONTROL sélecteur de plage]** ![select_cell_icon.png](assets/select_cell_icon.png) en regard de l’élément à mapper.

* **Toutes les cellules dans la plage** : cette option exige que vous sélectionniez un groupe de cellules pour une requête de type [!UICONTROL Disposition personnalisée].
* **Première cellule de la plage** : cette option permet de sélectionner la cellule supérieure gauche de la plage. Elle affiche également l’orientation [!UICONTROL Plage] afin d’indiquer l’orientation horizontale ou verticale des cellules d’entrée et de sortie (colonne ou ligne). Utilisez cette option pour que Report Builder sélectionne les cellules à votre place.
* **Orientation de plage** : cette option permet d’orienter les plages de cellules sous la forme de colonnes ou de lignes.
* **Sélectionnez l’emplacement de la cellule supérieure de la plage** : affiche les références de cellule.

## Techniques de sélection des cellules {#section_760421C3D7F84D67A639174710C93B22}

Pour sélectionner les données, cliquez sur l’icône **[!UICONTROL Sélection de plages]** ![select_cell_icon.png](assets/select_cell_icon.png)

et, tout en maintenant le bouton de la souris enfoncé, faites glisser le pointeur sur la plage de cellules de votre choix. Une sélection continue est entourée d’une bordure noire.

![](assets/twenty_cells.gif)

Les lignes sélectionnées distinctes sont entourées d’une fine bordure blanche.

![](assets/twoXten_cells_highlighted.gif)

Pour mapper des lignes distinctes dans une requête, utilisez la touche [!UICONTROL Contrôle], puis cliquez sur les cellules souhaitées et faites glisser le curseur dessus. Vous procédez de la sorte si votre requête appelle quatre zones de dix cellules chacune, plutôt qu’une zone continue de 40 cellules ensemble.

![](assets/map4.png)

Après avoir sélectionné les cellules, cliquez de nouveau sur le formulaire **[!UICONTROL Sélection de plage]** pour revenir à l&#39;Assistant [!UICONTROL Requête : étape 2] dans le formulaire [!UICONTROL Sélection de plage].

## Résolution des problèmes de mappage{#section_CC1BCF841291447EB3A994EB08F3A099}

Si vous choisissez par erreur de mapper à une cellule qui possède déjà un mappage actif, aucune référence de cellule n’apparaît dans la zone de texte en regard de l’icône du sélecteur de plage. Lorsque vous cliquez sur [!UICONTROL OK], Report Builder affiche l’erreur *La plage sélectionnée chevauche la plage d’une autre requête. Veuillez modifier votre sélection.*

* Si vous devez encore utiliser la cellule, cliquez avec le bouton droit de la souris sur la ou les cellules souhaitées, puis sélectionnez **[!UICONTROL Supprimer la demande]**.

Deux méthodes peuvent être utilisées pour éviter l’affichage de ce message :

* Planifiez le format du rapport en ajoutant une mise en forme aux cellules comportant des requêtes et des mappages
* Tester les zones de la feuille de calcul contenant les mappages

Pour tester les zones avec des requêtes incorporées, vous pouvez :

* Lancez le [!UICONTROL Gestionnaire de requêtes] et cliquez sur les requêtes individuelles répertoriées dans le tableau. Un clic sur la requête met en surbrillance les cellules de la feuille de calcul où la requête est mappée.
* Sélectionnez les cellules de la feuille de calcul que vous souhaitez utiliser pour un nouveau mappage, puis cliquez sur [!UICONTROL À partir de la feuille]. Le [!UICONTROL Gestionnaire de requêtes] sélectionne la requête dans la liste dont un élément de sortie croise la cellule sélectionnée. Si aucune requête n’est sélectionnée, la cellule est disponible.
* Sélectionnez des cellules dans la feuille de calcul, cliquez avec le bouton droit de la souris dans le menu contextuel et vérifiez si l&#39;option [!UICONTROL Modifier la demande] est disponible. Si tel est le cas, une requête est associée à ces cellules.
