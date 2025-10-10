---
description: Découvrez comment les tests statistiques sont utilisés dans la comparaison de segments.
keywords: Analysis Workspace ; Segment IQ
title: Tests Statistiques Utilisés Dans La Comparaison De Segments
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 43%

---

# Tests statistiques utilisés dans la comparaison de segments

Chacun des principaux tableaux de comparaison affiche un score de différence. Ce score est calculé par plusieurs tests statistiques en fonction de la comparaison effectuée. Cependant, quel que soit le test utilisé, le score de différence s’affiche sous la forme d’une valeur comprise entre 0 et 1.

Un score de 0 signifie qu’il n’y a aucune différence entre les deux segments et un score de 1 signifie qu’il y a une très grande différence entre les deux segments. Deux types de tests statistiques sont utilisés pour générer ces scores de différence :

* Pour le tableau **[!UICONTROL Mesures principales]** un test U de Mann-Whitney est utilisé,
* Une comparaison des différences de risque est utilisée pour les tableaux **[!UICONTROL Principaux éléments de Dimension]** et **[!UICONTROL Principaux segments]**.

## Score de différence des mesures principales

Dans le tableau Mesures principales , l’outil de comparaison des segments utilise deux exemples de test U de Mann-Whitney. Ce test est un test d’égalité non paramétrique utilisé pour comparer les distributions de probabilité unidimensionnelles de chaque mesure pour chaque segment pris en compte. Le score de différence dans le tableau de mesures est une combinaison de la valeur p de la statistique U calculée (qui représente le degré stochastique (aléatoire) de différence de distribution des deux segments pour une mesure particulière) et la magnitude relative de la différence observée. Un score de différence élevé (proche de 1) signifie que la mesure particulière présente une différence relative importante ainsi qu’une confiance statistique élevée quant à la différence des segments.

## Scores de différences des principaux éléments de dimension et des principaux segments

Pour calculer le score de différence des tableaux Principaux éléments de dimension et Principaux segments, un algorithme de différenciation des risques relatifs est appliqué (semblable au ratio de risque, bien qu’une différence soit utilisée à la place d’un ratio). Une différence de risque est calculée en soustrayant les incidences cumulées d’un élément de dimension (ou le chevauchement avec un segment du tableau de segments) du segment sélectionné par rapport à un autre. Un score de différence élevé (proche de 1) signifie que l’élément de dimension ou le segment tertiaire particulier était très important dans l’un des segments sélectionnés et pas dans l’autre.

>[!NOTE]
>
>Dans les trois tableaux, la statistique de différence repose sur un échantillon approprié de visiteurs afin que le processus s’exécute aussi rapidement que possible tout en restant statistiquement exact. Même si le score de différence repose sur un échantillon, les résultats présentés dans le tableau ne sont pas échantillonnés. Pour garantir une signification statistique, chaque test statistique s’appuie sur un algorithme d’allocation dynamique de sorte que le segment le plus petit contienne une taille d’échantillon garantissant une marge d’erreur de moins de 3 %. Si un segment contient très peu de visiteurs (moins de 1 000), toutes les données disponibles sont utilisées à la place de l’exemple pour calculer le score de différence.
