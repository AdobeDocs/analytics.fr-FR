---
title: URL de la page
description: L’URL de la page.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 64%

---


# URL de la page

La dimension « URL de la page » répertorie les adresses URL de votre site.

>[!IMPORTANT]
>
>Cette dimension est uniquement disponible dans Data Warehouse. Si vous souhaitez utiliser une dimension URL dans d’autres solutions Analytics, pensez à copier la valeur dans un [eVar](evar.md) sur chaque accès.

## Renseignement de cette dimension avec des données

This dimension retrieves data from the [`g` and `-g` query strings](/help/implement/validate/query-parameters.md) in [Page view calls (`t()`)](/help/implement/vars/functions/t-method.md). [Les appels de suivi de lien (`tl()`)](/help/implement/vars/functions/tl-method.md) dépouillent toujours cette dimension, même si la chaîne de `g` requête existe.

Les URL dépassent parfois 255 octets. AppMeasurement utilise le paramètre de chaîne de requête `g` pour les 255 premiers octets de l’URL dans les demandes d’image. Si une URL dépasse 255 octets, le reste de l’URL est stocké dans le paramètre de chaîne de requête `-g`. Les chaînes de protocole et de requête de l’URL sont incluses dans cette variable.

AppMeasurement collecte automatiquement ces données en fonction de l’URL de la page. Vous pouvez remplacer la valeur collectée à l’aide de la [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Renseignement d’une eVar avec une URL

Adobe recommande de définir une eVar sur la chaîne concaténée `window.location.hostname + window.location.pathname`. Cette chaîne fonctionne généralement mieux que `window.location.href` parce qu’elle omet le protocole, les chaînes de requête et les balises d’ancrage.

Si vous souhaitez que l’eVar corresponde exactement à la dimension « URL de la page » dans Data Warehouse, vous pouvez utiliser des [variables dynamiques](/help/implement/vars/page-vars/dynamic-variables.md) et définir l’eVar sur `D=g` pour chaque accès.

## Éléments de Dimension

Les éléments de Dimension incluent les URL des pages de votre site.
