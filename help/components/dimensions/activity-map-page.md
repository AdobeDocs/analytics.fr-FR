---
title: Page d’Activity Map
description: Nom de la page sur laquelle un utilisateur a cliqué sur un lien.
feature: Dimensions
role: User, Admin
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# Page d’Activity Map

La [dimension](overview.md) &quot;Page Activity Map&quot; affiche la page sur laquelle se trouvait un visiteur lorsqu’un utilisateur a cliqué sur un lien. Vous pouvez utiliser cette dimension pour déterminer les pages qui contiennent le plus de clics sur les liens. Cette dimension est également utilisée par la superposition Activity Map pour déterminer les liens à afficher.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la [variable de données contextuelles](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. Si votre mise en oeuvre utilise [Activity Map](/help/analyze/activity-map/overview.md), cette variable de données contextuelles collecte automatiquement des données lorsque l’utilisateur clique sur des liens.

Pour un lien donné sur lequel l’utilisateur a cliqué, cette variable de données contextuelles collecte la valeur dans la dimension [Page](page.md). Si la dimension Page ne contient pas de valeur, la dimension [URL de la page](page-url.md) est utilisée à la place (comme la dimension Page utilisée). Les données Activity Map sont généralement envoyées lors de l’accès suivant après qu’un lien a été cliqué. Cette dimension vous permet de déterminer la valeur de page lorsque l’utilisateur a cliqué sur le lien, au lieu de la valeur de page lors de l’envoi des données.

## Éléments de dimension

Les éléments de Dimension incluent toutes les valeurs trouvées dans la dimension [Page](page.md).
