---
title: Tableau à structure libre
description: En savoir plus sur les tableaux à structure libre et le créateur de tableaux à structure libre
translation-type: tm+mt
source-git-commit: ce06a5ca2caeb266c729947c76e93c611502e6d9

---


# Tableau à structure libre

Dans Analysis Workspace, un tableau à structure libre n’est pas simplement un tableau de données, mais également une visualisation interactive. Vous pouvez faire glisser et déposer une combinaison de [composants](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) dans les lignes et les colonnes afin de créer un tableau personnalisé pour votre analyse. Lorsque chaque composant est déposé, le tableau est mis à jour immédiatement afin que vous puissiez effectuer une analyse rapide.

Vous pouvez personnaliser le tableau de différentes manières :

* **Lignes**
   * Chaque ligne de dimension peut afficher jusqu’à 400 lignes avant la pagination. Vous pouvez ajuster davantage de lignes dans un seul écran en ajustant la densité [d’](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)affichage du projet.
   * Les lignes peuvent être ventilées par composants supplémentaires. Pour ventiler plusieurs lignes à la fois, sélectionnez simplement plusieurs lignes, puis faites glisser le composant suivant sur les lignes sélectionnées. En savoir plus sur les [ventilations](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html).
   * Les lignes peuvent être [filtrées](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html) pour afficher un ensemble réduit d’éléments. D’autres paramètres sont disponibles sous Paramètres [de](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.html)ligne.

* **Colonnes**
   * Les composants peuvent être empilés dans des colonnes afin de créer des mesures segmentées, des analyses sur plusieurs onglets, etc.
   * La vue de chaque colonne peut être ajustée sous les paramètres [de la](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)colonne.
   * Plusieurs actions sont disponibles via le menu [de](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html)clic droit. Le menu propose différentes actions selon que vous cliquez sur l’en-tête, les lignes ou les colonnes du tableau.

## Générateur de tableau à structure libre

Si vous préférez d’abord ajouter plusieurs composants à votre tableau, puis effectuer le rendu des données, vous pouvez activer le Générateur de tableau à structure libre. Le créateur étant activé, vous pouvez faire glisser et déposer de nombreuses dimensions, ventilations, mesures et segments afin de créer des tableaux qui répondent à des questions plus complexes. Les données ne sont pas mises à jour à la volée, elles le sont une fois que vous avez cliqué sur **[!UICONTROL Créer]**.

Le Générateur de tableau est une option qui vous permet de gagner du temps lorsque vous avez une question complexe à poser sur les données et que vous avez une idée du tableau à construire pour répondre à votre question. Le créateur de tableaux offre d’autres avantages :

* Organisez le tableau dans le format exact dont vous avez besoin, sans avoir à attendre le rendu de chaque action.
* Exécutez rapidement jusqu’à 4 niveaux de ventilations.
* Définissez les paramètres Ligne et Ventilation pour chaque ligne de tableau et colonne de dimension.
* **[!UICONTROL Ventilation par position]**pour chaque niveau du tableau par défaut (dans les tableaux à structure libre traditionnels, la valeur par défaut est**[!UICONTROL  Ventilation par élément]**).
* Organisez manuellement les lignes statiques dans le tableau. Par exemple, si vous souhaitez que les lignes de mesure apparaissent dans un certain ordre.
* Prévisualisez le format de votre tableau avant de générer des données réelles.

Regardez le Générateur de tableau à structure libre en action [ici](https://youtu.be/GUMWiJAmMGI).

## Exporter des données de tableau à structure libre

Les données d’un tableau à structure libre peuvent être copiées depuis Analysis Workspace de plusieurs manières :

* Cliquez avec le bouton droit sur l’en-tête du tableau et sélectionnez **[!UICONTROL Copier dans le Presse-papiers]**. Le tableau complet (visible) est alors exporté.
* Mettez en surbrillance des cellules spécifiques du tableau, cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Copier dans le Presse-papiers]**ou utilisez la touche Ctrl + C.
* **[!UICONTROL Projet > Télécharger CSV]**. Cette opération exporte toutes les tables visibles du projet au format CSV.
