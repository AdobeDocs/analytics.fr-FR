---
description: Les entrées représentent le nombre de fois où une valeur donnée est capturée comme première valeur d’une visite. Les entrées ne peuvent avoir lieu qu’une seule fois par visite. Cependant, il ne s’agit pas nécessairement du premier accès si la variable n’est pas définie.
title: Entrées
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# Entrées

&quot;Entrées&quot; représente le nombre de captures d’une valeur donnée en tant que première valeur d’une visite. Les entrées ne peuvent avoir lieu qu’une seule fois par visite. Cependant, il ne s’agit pas nécessairement du premier accès si la variable n’est pas définie.

Dans  Espace de travail , depuis mars 2020, nous avons modifié la manière dont la valeur &quot;Aucun&quot; interagit avec les entrées/sorties.  Comme vous pouvez désormais activer et désactiver l’option &quot;Non&quot; dans  Workspace , nous appliquons l’option &quot;Aucun&quot; après l’entrée ou la sortie, alors que (pour les eVars) elle était appliquée avant.  Par exemple, supposons que le premier accès d’une visite n’ait aucune valeur pour, par exemple, eVar21, mais que le second accès l’est. Dans les rapports et analyses, il s’affichera comme &quot;Non spécifié&quot; pour l’entrée, mais dans  espace de travail , il s’affichera comme la valeur du second accès.

Les pages d’entrée ont une portée de ventilation de visite, ce qui signifie qu’elles persistent sur tous les accès pour une visite. Pour plus d’informations, reportez-vous à la ventilation et à la segmentation [de segmentation](https://marketing.adobe.com/resources/help/en_US/sc/user/c_Breakdown_and_segmentation_containers.html) .
