---
description: Chacun des principaux tableaux de comparaison présente un score de différence calculé par plusieurs tests statistiques, selon le mode de comparaison. Toutefois, quel que soit le test utilisé, le score de différence est présenté comme une valeur comprise entre 0 et 1.
keywords: Analysis Workspace ; Segment IQ
title: Tests statistiques utilisés dans la comparaison de segments
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 100%

---

# Tests statistiques utilisés dans la comparaison de segments

Chacun des principaux tableaux de comparaison présente un score de différence calculé par plusieurs tests statistiques, selon le mode de comparaison. Toutefois, quel que soit le test utilisé, le score de différence est présenté comme une valeur comprise entre 0 et 1.

Un score nul signifie qu’il n’y a aucune différence entre les deux segments ; un score de 1 signifie qu’il existe une très grande différence entre les deux segments. Deux types de tests statistiques sont employés pour générer ces scores de différence : un test U de Mann-Whitney pour le tableau des mesures principales, une comparaison des différences de risque pour les principaux éléments de dimension et les principaux segments.

## Score de différence des mesures principales {#section_5E8047464EB945C78543B25F8F30F17A}

Dans le tableau Mesures principales, l’outil Comparaison des segments applique un test U de Mann-Whitney à deux échantillons, à savoir un test d’égalité non paramétrique servant à comparer les distributions de probabilité unidimensionnelles de chaque mesure pour chaque segment pris en compte. Le score de différence dans le tableau de mesures est une combinaison de la valeur p de la statistique U calculée (qui représente le degré stochastique (aléatoire) de différence de distribution des deux segments pour une mesure particulière) et la magnitude relative de la différence observée. Un score de différence élevé (proche de 1) signifie que la mesure particulière présente une différence relative élevée ainsi qu’une forte fiabilité statistique que les segments diffèrent.

## Scores de différences des principaux éléments de dimension et des principaux segments {#section_8073ADA6053B44C9A23FDC5ED4AF2AC4}

Pour calculer le score de différence des tableaux Principaux éléments de dimension et Principaux segments, un algorithme de différenciation des risques relatifs est appliqué (semblable au ratio de risque, bien qu’une différence soit utilisée à la place d’un ratio). Une différence de risque est calculée en soustrayant les incidences cumulées d’un élément de dimension (ou le chevauchement avec un segment du tableau de segments) du segment sélectionné par rapport à un autre. Un score de différence élevé (proche de 1) signifie que l’élément de dimension particulier ou le segment tertiaire était prédominant dans l’un des segments sélectionnés mais pas dans l’autre.

>[!NOTE]
>
>Dans les trois tableaux, la statistique de différence repose sur un échantillon approprié de visiteurs afin que le processus s’exécute aussi rapidement que possible tout en restant statistiquement exact. Même si le score de différence repose sur un échantillon, les résultats présentés dans le tableau ne sont pas échantillonnés. Pour garantir une signification statistique, chaque test statistique s’appuie sur un algorithme d’allocation dynamique de sorte que le segment le plus petit contienne une taille d’échantillon garantissant une marge d’erreur de moins de 3 %. Si un segment contient très peu de visiteurs (moins de 1 000), nous utilisons toutes les données disponibles et ne les échantillons pas lors du calcul du score de différence.
