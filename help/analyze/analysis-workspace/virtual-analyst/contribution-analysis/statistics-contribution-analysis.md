---
description: L’analyse des contributions est un processus intensif d’apprentissage automatique, conçu pour déterminer quels facteurs sont à l’origine d’une anomalie observée dans Adobe Analytics. Elle permet à l’utilisateur de repérer, bien plus rapidement qu’il ne serait normalement possible, les opportunités ou les centres d’intérêt justifiant une analyse supplémentaire.
seo-description: L’analyse des contributions est un processus intensif d’apprentissage automatique, conçu pour déterminer quels facteurs sont à l’origine d’une anomalie observée dans Adobe Analytics. Elle permet à l’utilisateur de repérer, bien plus rapidement qu’il ne serait normalement possible, les opportunités ou les centres d’intérêt justifiant une analyse supplémentaire.
seo-title: Techniques statistiques de l’analyse des contributions
title: Techniques statistiques de l’analyse des contributions
uuid: f77eb4e4-4fd6-4397-b8a8-a063f199b676
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Techniques statistiques de l’analyse des contributions

L’analyse des contributions est un processus intensif d’apprentissage automatique, conçu pour déterminer quels facteurs sont à l’origine d’une anomalie observée dans Adobe Analytics. Elle permet à l’utilisateur de repérer, bien plus rapidement qu’il ne serait normalement possible, les opportunités ou les centres d’intérêt justifiant une analyse supplémentaire.

Pour ce faire, l’analyse des contributions exécute un algorithme en deux parties pour chaque élément de dimension disponible pour le rapport Analyse des contributions de l’utilisateur. L’algorithme s’exécute dans cet ordre :

1. Pour chaque dimension, il calcule la statistique de test V de Cramer. Dans l’exemple suivant, on utilise une table de contingence avec les pages vues par pays au cours de deux périodes :

   ![](assets/contingency_table.png)

   Dans le tableau 1, le V de Cramer peut servir à mesurer l'association entre les pages vues par pays pour la période 1 (historique, par exemple) et la période 2 (par exemple, le jour où l'anomalie est survenue). Une faible valeur pour le V de Cramer implique un faible niveau d'association. Le V de Cramer varie de 0 (aucune association) à 1 (association complète). La statistique V de Cramer peut être calculée :

   ![](assets/cramers-v.png)

1. Pour chaque élément de dimension, le résiduel (PR) de la personne est utilisé pour mesurer l’association entre la mesure anormale et chaque élément de dimension. Le résiduel par personne applique une distribution normale standard, ce qui permet à l’algorithme de comparer cette valeur pour deux variables aléatoires même si l’écart n’est pas comparable. En pratique, l’erreur est indéterminée et est estimée en appliquant une correction d’échantillonnage finie.

   Dans le tableau 1 du précédent exemple, le résiduel par personne, avec la correction d’échantillonnage finie pour le pays i et la période 2 est calculé comme suit :

   ![](assets/persons-residual.png)

   Ici,

   ![](assets/pr-example.png)

   (Une formule semblable peut être obtenue pour la période 1.)

   Pour les résultats finaux, le score de chaque élément de dimension est ensuite pondéré par la mesure V de Cramer et redimensionné à un nombre compris entre 0 et 1 pour fournir son score de contribution.

