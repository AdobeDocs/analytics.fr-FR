---
title: Meilleures pratiques de segmentation
description: Créez des segments optimaux qui renvoient efficacement les données.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---


# Meilleures pratiques de segmentation

Des segments complexes sont souvent nécessaires pour obtenir les données souhaitées. Si les segments complexes sont inefficaces et utilisés dans une suite de rapports volumineuse, l’exécution des rapports est considérablement plus longue. Tenez compte des ressources suivantes lors de la création ou de la modification d’un segment afin de minimiser la complexité.

## Utiliser uniquement l&#39;opérateur &quot;Contient&quot; en dernier recours

L’opérateur &quot;Contient&quot; est l’une des fonctionnalités de segmentation les plus gourmandes en traitement, car il doit analyser l’ensemble du contenu de chaque valeur. Utilisez d’autres opérateurs tels que &quot;Débuts avec&quot; ou &quot;Se termine avec&quot; si les valeurs souhaitées se trouvent au début ou à la fin d’une chaîne.

Si un opérateur &quot;Contient&quot; dans un segment renvoie un grand nombre de résultats, le rapport expire généralement. Par exemple, si vous avez créé un segment où `Referrer equals "."`le segment recherche dans le contenu de chaque valeur. Utilisez plutôt l&#39;opérateur &quot;Exists&quot;.

## Utiliser des classifications pour regrouper des éléments de dimension

Si vous avez de nombreuses conditions de segment, elles peuvent rapidement dégrader les performances des segments. Par exemple, `Page equals X or Page equals Y or Page equals Z` répétée avec des centaines de valeurs différentes. Au lieu d’écrire ces centaines de conditions, classifiez toutes les valeurs souhaitées dans un segment, puis utilisez la valeur classée dans un segment.

1. Créez une classification pour la variable que vous utilisez.
2. Téléchargez le modèle de classification et ouvrez-le dans la feuille de calcul ou l’éditeur de texte de votre choix.
3. Donnez à chaque élément de dimension que vous souhaitez inclure dans votre segment la même valeur.
4. Utiliser l&#39;importateur de classifications pour réimporter la feuille de calcul en Adobe Analytics
5. Une fois le traitement de la classification terminé, créez un segment à l’aide de la valeur classifiée.

Cette méthode augmente considérablement les performances et permet de modifier facilement les conditions de segment. Au lieu de modifier le segment avec des valeurs différentes, vous pouvez ajouter ou supprimer des éléments de dimension de la classification.
