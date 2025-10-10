---
title: Région d’Activity Map
description: Région de votre site sur laquelle l’utilisateur a cliqué.
feature: Dimensions
role: User, Admin
exl-id: e262e537-ce73-492a-8ab3-b88cd77cb8c5
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 5%

---

# Région d’Activity Map

La [dimension](overview.md) « Région Activity Map » affiche les régions de votre site qui ont reçu le plus grand nombre de clics. Cette dimension est utile lorsque vous souhaitez comparer des clics dans des régions globales de votre site plutôt que des liens individuels. Il est également utile pour les zones de votre site qui diffusent du contenu dynamique. Par exemple, si vous avez une page d’accueil avec des articles d’actualité rotatifs, l’utilisation de la dimension [Lien Activity Map](activity-map-link.md) serait difficile, car le texte du lien change constamment. Cependant, comme ces liens utilisent la même région, vous pouvez analyser les performances de cette zone même si les liens individuels peuvent changer chaque jour.

## Renseigner cette dimension avec des données

Cette dimension récupère les données du [&#x200B; &#x200B;](/help/implement/vars/page-vars/contextdata.md)Variable de données contextuelles`c.a.activitymap.region`. Si votre implémentation utilise [Activity Map](/help/analyze/activity-map/overview.md), cette variable de données contextuelles collecte automatiquement les données lorsque l’utilisateur clique sur les liens.

Pour un lien donné sur lequel l’utilisateur a cliqué, vérifiez les éléments suivants dans l’élément DOM parent (dans l’ordre) :

* Une valeur dans l’attribut défini par [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) - défini sur l’attribut `id` par défaut
* Une valeur dans l’attribut `aria-label` lorsque l’attribut `role="region"`
* Les éléments sémantiques `<header>`, `<main>`, `<footer>` ou `<nav>` (Web SDK uniquement)

Si l’élément DOM parent ne répond à aucun des critères ci-dessus, la recherche se poursuit de manière récursive jusqu’à la hiérarchie DOM. Si aucun élément correspondant n’est trouvé, la valeur `BODY` est renvoyée.

## Éléments de dimension

Les éléments Dimension incluent les régions que vous avez étiquetées sur votre site. Les valeurs de région spécifiques dépendent des attributs utilisés et de la présence ou non d’éléments sémantiques HTML.
