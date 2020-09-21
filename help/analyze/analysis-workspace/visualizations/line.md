---
description: Utilisation de la visualisation en ligne pour représenter les jeux de données des tendances (temporels).
title: Ligne
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: e9982ff662396fbdd2f5c9645d768fb373764968
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 79%

---


# Ligne

Dans la visualisation en ligne, les mesures sont représentées sous la forme d’une ligne afin d’indiquer l’évolution des valeurs dans le temps. Pour pouvoir utiliser un graphique en courbes, le temps doit être défini comme une dimension.

![Visualisation en ligne](assets/line-viz.png)

Cliquez sur l’icône en forme d’engrenage en haut à droite de la visualisation en ligne pour accéder aux [**paramètres de visualisation**](freeform-analysis-visualizations.md) disponibles. Les paramètres sont classés comme suit :

* **Général** : paramètres communs à tous les types de visualisation
* **Axes** : paramètres qui affectent l’axe x ou y de la visualisation en ligne
* **Superpositions** : options permettant d’ajouter du contexte à la série affichée dans la visualisation en ligne.

![Paramètres de visualisation](assets/viz-settings-modal.png)

## Modification de la granularité

Une liste déroulante de granularité accessible dans les [paramètres de visualisation](freeform-analysis-visualizations.md) permet de modifier une visualisation avec suivi des tendances (ex. ligne, barre) de chaque jour à chaque mois, etc. La granularité est également mise à jour dans le tableau de la source de données.

## Affichage des min. et max.

Sous **[!UICONTROL Paramètres de visualisation]** > **[!UICONTROL Superpositions]** > **[!UICONTROL Afficher les min./max.]**, vous pouvez superposer une étiquette de valeur minimale et maximale pour rapidement mettre en relief les pics et les creux d’une mesure. Remarque : Les valeurs min/max sont dérivées des points de données visibles dans la visualisation, et non du jeu complet de valeurs dans une dimension.

![Afficher les min./max.](assets/min-max-labels.png)

## Affichage de courbes de tendance superposées

Sous **[!UICONTROL Paramètres de visualisation]** > **[!UICONTROL Superpositions]** > **[!UICONTROL Afficher la courbe de tendance]**, vous pouvez choisir d’ajouter une courbe de tendance de régression à votre série de lignes. Les courbes de tendance permettent d’illustrer plus clairement un schéma dans les données.

>[!TIP]
>
>Nous vous recommandons d’appliquer des lignes de tendances aux données qui n’incluent pas de dates d’aujourd’hui (données partielles) ou futures, car elles faussent la ligne de tendance. Toutefois, si vous devez inclure des dates futures, supprimez des zéros des données afin d’éviter les bizutages de ces jours. Pour ce faire, accédez au tableau de source de données de la visualisation et choisissez votre colonne de mesures. Accédez ensuite à Paramètres [!UICONTROL de] colonne et cochez la case **[!UICONTROL Interpréter zéro comme aucune valeur]**.)

![Courbe de tendance linéaire](assets/show-linear-trendline.png)

Tous les modèles sont ajustés à l’aide de moindres carrés ordinaires :

| Modèle | Description |
| --- | --- |
| Linéaire | Crée une ligne droite adaptée aux jeux de données linéaires simples. Utile lorsque les données augmentent ou diminuent à un rythme régulier. Équation : `y = a + b * x` |
| Logarithmique | Crée une courbe adaptée. Utile lorsque le taux de changement des données augmente ou diminue rapidement, puis s’équilibre. Une courbe de tendance logarithmique peut utiliser des valeurs négatives et positives. Équation : `y = a + b * log(x)` |
| Exponentiel | Crée une courbe. Utile lorsque les données augmentent ou diminuent à un rythme constamment croissant. Cette option ne doit pas être utilisée si vos données contiennent des valeurs nulles ou négatives. Équation : `y = a + e^(b * x)` |
| Puissance | Crée une courbe. Utile pour les jeux de données comparant des mesures qui augmentent à un rythme spécifique. Cette option ne doit pas être utilisée si vos données contiennent des valeurs nulles ou négatives. Équation : `y = a * x^b` |
| Quadratique | Trouve la courbe la plus adaptée pour un jeu de données en forme de parabole (concave vers le haut ou vers le bas). Équation : `y = a + b * x + c * x^2` |
