---
description: valeur nulle
title: Synthèse des chiffres et synthèse des changements
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# Synthèse des chiffres et synthèse des changements

## Visualisation Synthèse des chiffres

* Sélectionne le total de la colonne si aucune cellule n’est sélectionnée.
* Si une seule cellule est sélectionnée, le résumé de cette cellule s’affiche.
* Si plusieurs cellules sont sélectionnées, la première cellule est sélectionnée.
* Si la colonne est sélectionnée, elle sélectionne la première valeur de cellule de la colonne.

![](assets/summary-number.png)

## Visualisation Résumé des changements

* Si aucune cellule n’est sélectionnée, elle compare les deux premières valeurs de cellule de la colonne.
* Si une cellule est sélectionnée, elle affiche 0, car elle compare la valeur de la cellule à elle-même.
* Si deux cellules sont sélectionnées, la première cellule sélectionnée est utilisée comme numérateur et la seconde comme dénominateur.
* Si plus de deux cellules sont sélectionnées, seules les deux premières sont prises en compte pour la comparaison.
* Si une plage de cellules est sélectionnée, elle compare la première à la dernière cellule sélectionnée dans la plage.
* Si la colonne est sélectionnée, elle compare la première valeur à elle-même, ce qui indique une modification de 0.
* La couleur verte et rouge du résumé de la modification peut être contrôlée par :
   * [Polarité](https://marketing.adobe.com/resources/help/fr_FR/reference/success_event.html) personnalisée.
   * Option [Afficher la tendance à la hausse sous](https://marketing.adobe.com/resources/help/fr_FR/analytics/calcmetrics/cm_build_metrics.html) d’une mesure calculée.

## Paramètres du résumé des changements {#section_2581AC0107634FB4990AB8347E5897AA}

Cliquez sur l’icône d’engrenage en regard de la visualisation pour configurer les paramètres Résumé :

| Paramètre | Définition |
|--- |--- |
| Pourcentages | Utilisez des pourcentages plutôt que des chiffres bruts. |
| Légende visible | Affiche les mesures utilisées. |
| Options du numéro de résumé : Valeur abrégée | Vous pouvez choisir de 0 à 3 nombres de décimales pour les valeurs abrégées. |
| Options de modification récapitulative : Afficher la modification du pourcentage | Affiche le changement, en pourcentage, entre les deux nombres. |
| Options de modification récapitulative : Afficher la différence brute | Affiche la différence brute entre les 2 nombres. |
