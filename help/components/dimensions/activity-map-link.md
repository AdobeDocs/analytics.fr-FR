---
description: Nom du lien sur lequel l’utilisateur a cliqué.
title: Lien d’Activity Map
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 8%

---

# Lien d’Activity Map

La [dimension](overview.md) &quot;Lien Activity Map&quot; affiche les liens les plus populaires sur lesquels l’utilisateur a cliqué. Vous pouvez utiliser cette dimension pour comparer les liens de votre site les plus utilisés, quel que soit l’endroit où vous avez cliqué sur ces liens.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la [variable de données contextuelles](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`. Si votre mise en oeuvre utilise [Activity Map](/help/analyze/activity-map/overview.md), cette variable de données contextuelles collecte automatiquement des données lorsque l’utilisateur clique sur des liens.

Pour un lien donné sur lequel l’utilisateur a cliqué, l’Activity Map recherche les éléments suivants (dans l’ordre) :

1. La variable `s_objectID`
1. Texte interne du lien
1. L’attribut `alt` pour les images
1. Attribut `title`
1. L’attribut `src` pour les images
1. L’attribut `action` pour les formulaires

Si l’élément sur lequel l’utilisateur a cliqué ne contient aucun des critères ci-dessus, l’Activity Map ne collecte pas de données pour ce clic.

## Éléments de dimension

Les éléments de Dimension incluent le texte du lien ou d’autres attributs de lien sur lesquels les visiteurs cliquent. La structure et l’implémentation du site de votre entreprise déterminent les valeurs exactes collectées.
