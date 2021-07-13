---
description: Utilisez les visualisations Synthèse des chiffres et Synthèse des changements pour afficher des points de données importants dans un projet.
title: Synthèse des chiffres et synthèse des changements
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualisations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 100%

---

# Synthèse des chiffres et synthèse des changements

## Visualisation Synthèse des chiffres  {#summary-number}

Utilisez la visualisation Synthèse des chiffres pour mettre en évidence un grand nombre d’éléments importants dans un projet. Cette visualisation fonctionne comme suit :

* Sélectionne toutes les colonnes si aucune cellule n’est sélectionnée.
* Si une seule cellule est sélectionnée, son résumé s’affiche.
* Si plusieurs cellules sont sélectionnées, la première cellule sélectionnée s’affiche.
* Si la colonne est sélectionnée, la valeur de la première cellule de la colonne est affichée.

Cliquez sur l’engrenage **Paramètres de visualisation** dans le coin supérieur droit pour configurer les paramètres de Synthèse des chiffres :

| Paramètre | Définition |
|--- |--- |
| Pourcentages | Affichent des pourcentages plutôt que des chiffres bruts. |
| Légende visible | Affiche des informations sur la mesure affichée. |
| Abréger la valeur | Abrège les valeurs et affiche jusqu’à 3 chiffres après la virgule. |
| Résumer la valeur par | Affiche le maximum, le minimum, la moyenne, la médiane ou la somme pour une sélection de données. |


Cliquez sur l’engrenage **Paramètres de visualisation** dans le coin supérieur droit pour configurer les paramètres de Synthèse des chiffres :

| Paramètre | Définition |
|--- |--- |
| Pourcentages | Affichent des pourcentages plutôt que des chiffres bruts. |
| Légende visible | Affiche des informations sur la mesure affichée. |
| Abréger la valeur | Abrège les valeurs et affiche jusqu’à 3 chiffres après la virgule. |
| Résumer la valeur par | Affiche le maximum, le minimum, la moyenne, la médiane ou la somme pour une sélection de données. |


## Visualisation Résumé des changements {#summary-change}

Utilisez la visualisation Synthèse des changements pour afficher le delta (changement) entre deux chiffres. La couleur verte et la couleur rouge de la Synthèse des changements peuvent être contrôlées par [polarité d’événement personnalisé](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html?lang=fr) ou par l’option [Tendance à la hausse affichée](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=fr) d’une mesure calculée.

Cette visualisation fonctionne comme suit :

* Si aucune cellule n’est sélectionnée, les valeurs de deux premières cellules de la colonne sont comparées.
* Si une seule cellule est sélectionnée, 0 s’affiche, car la valeur de la cellule est comparée à elle-même.
* Si deux cellules sont sélectionnées, la première cellule sélectionnée sert de numérateur, la deuxième de dénominateur.
* Si plus de deux cellules sont sélectionnées, seules les deux premières sont prises en compte pour la comparaison.
* Si une rangée de cellules est sélectionnée, la première et la dernière cellules de la rangée sont comparées.
* Si la colonne est sélectionnée, la première valeur est comparée à elle-même ; 0 s’affiche.


![](assets/summary-change.png)


Cliquez sur l’engrenage **Paramètres de visualisation** dans le coin supérieur droit pour configurer les paramètres de Synthèse des changements :

| Paramètre | Définition |
|--- |--- |
| Pourcentages | Affichent des pourcentages plutôt que des chiffres bruts. |
| Légende visible | Affiche des informations sur la mesure affichée. |
| Afficher le pourcentage de changement | Affiche le pourcentage de changement entre les 2 chiffres. |
| Afficher la différence brute | Affiche la différence brute entre 2 nombres. Vous pouvez également abréger des valeurs et afficher jusqu’à 3 chiffres après la virgule avec cette option. |
