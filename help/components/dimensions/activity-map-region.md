---
title: Région d’Activity Map
description: Région de votre site sur laquelle l’utilisateur a cliqué.
feature: Dimensions
role: User, Admin
exl-id: e262e537-ce73-492a-8ab3-b88cd77cb8c5
TQID: https://experienceleague.adobe.com/mmLp5-dgKGeovIOMPZxliyhfbpUSMLXca-3Qs6QA0SA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 7%
---
# Région d’Activity Map

La [dimension](overview.md) « Région Activity Map » affiche les régions de votre site qui ont reçu le plus grand nombre de clics. Cette dimension est utile lorsque vous souhaitez comparer des clics dans des régions globales de votre site plutôt que des liens individuels. Il est également utile pour les zones de votre site qui diffusent du contenu dynamique. Par exemple, si vous avez une page d’accueil avec des articles d’actualité rotatifs, l’utilisation de la dimension [Lien &#x200B;](activity-map-link.md) serait difficile, car le texte du lien change constamment. Cependant, comme ces liens utilisent la même région, vous pouvez analyser les performances de cette zone même si les liens individuels peuvent changer chaque jour.

## Renseigner cette dimension avec des données

Cette dimension récupère les données du `c.a.activitymap.region` [Variable de données contextuelles](/help/implement/vars/page-vars/contextdata.md). Si votre implémentation utilise [&#128279;](/help/analyze/activity-map/overview.md), cette variable de données contextuelles collecte automatiquement les données lorsque l’utilisateur clique sur les liens.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucune (collectée par le module [&#128279;](/help/analyze/activity-map/overview.md)) |
| **Champ Web SDK/XDM** | Aucune (collectée par le module [&#128279;](/help/analyze/activity-map/overview.md)) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | 255 octets |
| **Persistance** | S.O. |

Pour un lien donné sur lequel l’utilisateur a cliqué, vérifiez les éléments suivants dans l’élément DOM parent (dans l’ordre) :

* Une valeur dans l’attribut défini par [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) - défini sur l’attribut `id` par défaut
* Une valeur dans l’attribut `aria-label` lorsque l’attribut `role="region"`
* Les éléments sémantiques `<header>`, `<main>`, `<footer>` ou `<nav>` (Web SDK uniquement)

Si l’élément DOM parent ne répond à aucun des critères ci-dessus, la recherche se poursuit de manière récursive jusqu’à la hiérarchie DOM. Si aucun élément correspondant n’est trouvé, la valeur `BODY` est renvoyée.

## Éléments de dimension

Les éléments Dimension incluent les régions que vous avez étiquetées sur votre site. Les valeurs de région spécifiques dépendent des attributs utilisés et de la présence ou non d’éléments sémantiques HTML.
