---
title: Bonnes pratiques de la segmentation
description: Créez des segments optimaux qui renvoient efficacement les données.
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 100%

---

# Bonnes pratiques de la segmentation

Des segments complexes sont souvent nécessaires pour obtenir les données souhaitées. Si les segments complexes sont inefficaces et utilisés dans une suite de rapports volumineuse, l’exécution des rapports est considérablement plus longue. Tenez compte des ressources suivantes lors de la création ou de la modification d’un segment afin de minimiser la complexité.

## Utilisez l’opérateur « Contient » en dernier recours uniquement

L’opérateur « Contient » est l’une des fonctionnalités de segmentation les plus gourmandes en traitement, car il doit analyser l’ensemble du contenu de chaque valeur. Utilisez d’autres opérateurs, tels que « Commence par » ou « Se termine par » si les valeurs souhaitées se trouvent au début ou à la fin d’une chaîne.

Si l’opérateur « Contient » d’un segment renvoie un grand nombre de résultats, il est fréquent que le rapport expire. Par exemple, si vous avez créé un segment où `Referrer equals "."`, le segment effectue la recherche dans le contenu de chaque valeur. Utilisez plutôt l’opérateur « Existe ».

## Utilisez des classifications pour regrouper des éléments de dimension

Si vous avez de nombreuses conditions de segment, elles peuvent rapidement dégrader les performances des segments. Par exemple, la répétition de `Page equals X or Page equals Y or Page equals Z` pour des centaines de valeurs différentes. Au lieu d’écrire ces centaines de conditions, classifiez toutes les valeurs souhaitées dans un segment, puis utilisez la valeur classifiée dans un segment.

1. Créez une classification pour la variable que vous utilisez.
2. Téléchargez le modèle de classification et ouvrez-le dans la feuille de calcul ou l’éditeur de texte de votre choix.
3. Donnez la même valeur à chaque élément de dimension que vous souhaitez inclure dans votre segment.
4. Utilisez l’importateur de classifications pour réimporter la feuille de calcul dans Adobe Analytics.
5. Une fois le traitement de la classification terminé, créez un segment à l’aide de la valeur classifiée.

Cette méthode augmente considérablement les performances et permet de modifier facilement les conditions de segment. Au lieu de modifier le segment avec des valeurs différentes, vous pouvez ajouter ou supprimer des éléments de dimension de la classification.
