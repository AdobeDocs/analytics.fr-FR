---
title: URL de la page
description: L’URL de la page.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 95%

---

# URL de la page

La [dimension](overview.md) « URL de la page » répertorie les URL de votre site.

>[!IMPORTANT]
>
>Cette dimension est uniquement disponible dans Data Warehouse. Si vous souhaitez utiliser une dimension URL dans dʼautres solutions Analytics, pensez à copier la valeur dans une [eVar](evar.md) pour chaque accès.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données des chaînes de requête [`g` et `-g`](/help/implement/validate/query-parameters.md) dans les [appels de visualisation de la page (`t()`)](/help/implement/vars/functions/t-method.md). Les [appels de suivi des liens (`tl()`)](/help/implement/vars/functions/tl-method.md) éliminent toujours cette dimension, même si la chaîne de requête `g` existe.

Les URL dépassent parfois 255 octets. AppMeasurement utilise le paramètre de chaîne de requête `g` pour les 255 premiers octets de l’URL dans les demandes d’image. Si une URL dépasse 255 octets, le reste de l’URL est stocké dans le paramètre de chaîne de requête `-g`. Les chaînes de protocole et de requête de l’URL sont incluses dans cette variable.

AppMeasurement collecte automatiquement ces données en fonction de lʼURL de la page. Vous pouvez remplacer la valeur collectée à lʼaide de la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Renseignement d’une eVar avec une URL

Adobe recommande de définir une eVar sur la chaîne concaténée `window.location.hostname + window.location.pathname`. Cette chaîne fonctionne généralement mieux que `window.location.href` parce qu’elle omet le protocole, les chaînes de requête et les balises d’ancrage.

Si vous souhaitez que l’eVar corresponde exactement à la dimension « URL de la page » dans Data Warehouse, vous pouvez utiliser des [variables dynamiques](/help/implement/vars/page-vars/dynamic-variables.md) et définir l’eVar sur `D=g` pour chaque accès.

## Éléments de dimension

Les éléments de dimension comprennent les adresses URL des pages de votre site.
