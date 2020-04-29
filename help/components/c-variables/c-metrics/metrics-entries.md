---
description: Les entrées représentent le nombre de fois où une valeur donnée est capturée comme première valeur d’une visite. Une mesure Entrées peut survenir une seule fois par visite. Cependant, il ne s’agit pas nécessairement du premier accès si la variable n’est pas définie.
title: Entrées
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Entrées

&quot;Entrées&quot; représente le nombre de captures d’une valeur donnée en tant que première valeur d’une visite. Une mesure Entrées peut survenir une seule fois par visite. Cependant, il ne s’agit pas nécessairement du premier accès si la variable n’est pas définie.

Dans Analysis Workspace, depuis mars 2020, nous avons modifié la manière dont la valeur « Aucun » interagit avec les entrées/sorties.  Comme vous pouvez désormais activer et désactiver l’option &quot;Non&quot; dans  Workspace , nous appliquons l’option &quot;Aucun&quot; après l’entrée ou la sortie, alors que (pour les eVars) elle était appliquée avant.  Par exemple, supposons que le premier accès d’une visite n’ait aucune valeur pour, par exemple, eVar21, mais que le second accès l’est. Dans Reports &amp; Analytics, il s’affichera comme « Non spécifié » pour l’entrée, mais dans Analysis Workspace, il affichera la valeur pour le second accès.

Les pages d’entrée comportent une portée de ventilation de visites, signifiant qu’elles persistent sur l’ensemble des accès pour une visite. Pour plus d’informations, voir [Conteneurs de ventilation et de segmentation](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-overview.html).
