---
title: URL de la page
description: L’URL de la page.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 92%

---


# URL de la page

La dimension « URL de la page » répertorie les adresses URL de votre site.

>[!IMPORTANT]
>
>Cette dimension est uniquement disponible dans Data Warehouse. Si vous souhaitez utiliser une dimension URL dans d’autres solutions Analytics, utilisez une [eVar](evar.md).

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`g`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Renseignement d’une eVar avec une URL

Adobe recommande de définir une eVar sur la chaîne concaténée `window.location.hostname + window.location.pathname`. Cette chaîne fonctionne généralement mieux que `window.location.href` parce qu’elle omet le protocole, les chaînes de requête et les balises d’ancrage.

Si vous souhaitez que l’eVar corresponde exactement à la dimension « URL de la page » dans Data Warehouse, vous pouvez utiliser des [variables dynamiques](/help/implement/vars/page-vars/dynamic-variables.md) et définir l’eVar sur `D=g` pour chaque accès. Notez que cette méthode ne fonctionne pas pour les accès aux liens personnalisés, car l’URL de la page est supprimée pour tous les appels [`tl()`](/help/implement/vars/functions/tl-method.md).

## Éléments de Dimension

Les éléments de Dimension incluent les URL des pages de votre site.
