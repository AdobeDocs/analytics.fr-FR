---
title: Région d’Activity Map
description: Région sur votre site sur laquelle l’utilisateur a cliqué.
feature: Dimensions
role: User, Admin
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 5%

---

# Région d’Activity Map

La [dimension](overview.md) de la &quot;région Activity Map&quot; affiche les régions de votre site qui ont reçu le plus grand nombre de clics. Cette dimension est utile lorsque vous souhaitez comparer des clics sur plusieurs régions principales de votre site au lieu de liens individuels. Il est également utile pour les zones de votre site qui diffusent du contenu dynamique. Par exemple, si vous disposez d’une page d’accueil avec des articles d’actualité rotatifs, l’utilisation de la dimension [Lien Activity Map](activity-map-link.md) serait difficile car le texte du lien change constamment. Cependant, comme ces liens utilisent la même région, vous pouvez analyser les performances de cette zone même si des liens individuels peuvent changer chaque jour.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la [variable de données contextuelles](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`. Si votre mise en oeuvre utilise [Activity Map](/help/analyze/activity-map/overview.md), cette variable de données contextuelles collecte automatiquement des données lorsque l’utilisateur clique sur des liens.

Pour un lien donné sur lequel l’utilisateur a cliqué, vérifiez les éléments DOM parent dans l’ordre suivant :

* Une valeur dans l’attribut défini par [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) - défini par défaut sur l’attribut `id`
* Une valeur dans l’attribut `aria-label` lorsque l’attribut `role="region"`
* Les éléments sémantiques `<header>`, `<main>`, `<footer>` ou `<nav>` (SDK Web uniquement)

Si l’élément DOM parent ne répond à aucun des critères ci-dessus, la recherche se poursuit récursivement dans la hiérarchie DOM. Si aucun élément correspondant n&#39;est trouvé, la valeur `BODY` est renvoyée.

## Éléments de dimension

Les éléments de Dimension comprennent les régions que vous avez étiquetées sur votre site. Les valeurs de région spécifiques dépendent des attributs utilisés et si des éléments d’HTML sémantique sont présents.
