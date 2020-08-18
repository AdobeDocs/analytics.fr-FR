---
description: Utilisez la visualisation en ligne pour représenter les jeux de données de tendances (temporels).
title: Ligne
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 34db4e99589827fd41f642788e3409834b96d78a
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 16%

---


# Ligne

Dans cette visualisation, les mesures sont représentées sous la forme d’une ligne afin d’indiquer de quelle façon changent les valeurs au fil du temps. Pour pouvoir utiliser un graphique en courbes, le temps doit être défini comme une dimension.

## Paramètres de visualisation

>[!IMPORTANT]
>
> Certains paramètres de visualisation en ligne, tels que Afficher la courbe de tendance, sont actuellement en cours de test limité. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/landing/an-releases.html).

Cliquez sur l’icône en forme d’engrenage en haut à droite de la visualisation en ligne pour accéder aux paramètres [**de**](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html#section_D3BB5042A92245D8BF6BCF072C66624B) visualisation disponibles. Les paramètres sont classés par :

* Général - paramètres communs à tous les types de visualisation
* Axe : paramètres qui auront un impact sur l’axe x ou y de la visualisation en ligne.
* Overlays : options permettant d’ajouter un contexte supplémentaire à la série affichée dans la visualisation en ligne.

### Modifier la granularité

Une liste déroulante de granularité accessible dans les [paramètres de visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_D3BB5042A92245D8BF6BCF072C66624B) permet de modifier une visualisation avec suivi des tendances (ex. ligne, barre) de chaque jour à chaque mois, etc. La granularité est également mise à jour dans le tableau de la source de données.

### Afficher min ou max

Sous Paramètres de **visualisation > Overlays > Afficher min/max**, vous pouvez superposer une étiquette de valeur minimale et maximale pour mettre rapidement en surbrillance les pics et les vallées d’une mesure.

### Afficher le recouvrement de tendance

Sous Paramètres de **visualisation > Overlays > Afficher la courbe de tendance**, vous pouvez choisir d’ajouter une courbe de tendance de régression à votre série de lignes. Les lignes de tendances permettent de représenter un schéma plus clair dans les données.

Tous les modèles sont ajustés en utilisant les moindres carrés ordinaires :

| Modèle | Description |
|---|---|
| Linéaire | Crée une ligne droite parfaitement adaptée aux jeux de données linéaires simples et est utile lorsque les données augmentent ou diminuent à un rythme régulier. Équation : y = a + b * x |
| Logarithmique | Crée une ligne incurvée qui convient le mieux et s’avère utile lorsque le taux de changement des données augmente ou diminue rapidement, puis diminue. Une courbe de tendance logarithmique peut utiliser des valeurs négatives et positives. Équation : y = a + b * log(x) |
| Exponentielle | Crée une ligne incurvée et est utile lorsque les données augmentent ou diminuent à un rythme constamment croissant. Cette option ne doit pas être utilisée si vos données contiennent des valeurs nulles ou négatives. Équation : y = a +<sup>eb * x |
| Alimentation | Crée une ligne incurvée et est utile pour les jeux de données qui comparent les mesures qui augmentent à un rythme spécifique. Cette option ne doit pas être utilisée si vos données contiennent des valeurs nulles ou négatives. Équation : y = a *<sup>xb |
| Quadratique | Trouve le meilleur ajustement pour un jeu de données en forme de parabole (concave vers le haut ou vers le bas). Équation : y = a + b * x + c * x<sup>2 |
| Polynomial | Utile lorsque votre jeu de données fluctue, par exemple en analysant les gains et les pertes sur un jeu de données volumineux. Équation : y = a + b * x + ... + k *<sup>xorder |
