---
title: Page d’Activity Map
description: Nom de la page lorsqu’un utilisateur a cliqué sur un lien.
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# Page d’Activity Map

La [dimension](overview.md) « Page Activity Map » affiche la page sur laquelle se trouvait un visiteur lorsqu’il a cliqué sur un lien. Vous pouvez utiliser cette dimension pour déterminer les pages qui contiennent les liens les plus consultés. Cette dimension est également utilisée par le recouvrement Activity Map pour déterminer les liens à afficher.

## Renseigner cette dimension avec des données

Cette dimension récupère les données du [&#x200B; &#x200B;](/help/implement/vars/page-vars/contextdata.md)Variable de données contextuelles`c.a.activitymap.page`. Si votre implémentation utilise [Activity Map](/help/analyze/activity-map/overview.md), cette variable de données contextuelles collecte automatiquement les données lorsque l’utilisateur clique sur les liens.

Pour un lien donné sur lequel l’utilisateur a cliqué, cette variable de données contextuelles collecte la valeur de la dimension [Page](page.md). Si la dimension Page ne contient pas de valeur, la dimension [URL de la page](page-url.md) est utilisée à la place (de manière similaire à la version de secours utilisée par la dimension Page). Les données Activity Map sont généralement envoyées lors de l’accès suivant après l’utilisation d’un lien. Cette dimension vous permet de déterminer la valeur de la page lorsque l’utilisateur a cliqué sur le lien, au lieu de la valeur de la page lors de l’envoi des données.

## Éléments de dimension

Les éléments Dimension incluent toutes les valeurs trouvées dans la dimension [Page](page.md).
