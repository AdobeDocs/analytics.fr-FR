---
title: linkURL
description: Permet de remplacer l’URL de lien générée automatiquement utilisée par AppMeasurement dans les appels de suivi des liens.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 100%

---

# linkURL

Chaque fois qu’un appel de suivi des liens est envoyé à Adobe, les serveurs de collecte de données détectent automatiquement l’URL. Utilisez la variable `linkURL` pour remplacer l’URL détectée.

## URL du lien à l’aide de balises dans Adobe Experience Platform

Il n’existe pas de champ dédié dans l’interface utilisateur de la collecte de données pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.linkURL dans AppMeasurement et l’éditeur de code personnalisé

La variable `s.linkURL` est une chaîne contenant l’URL du navigateur lorsque l’utilisateur a cliqué sur le lien. Cette variable ne renseigne aucune dimension disponible dans les rapports.

```js
s.linkURL = "https://example.com";
```

Si le troisième argument de la méthode [tl()](../functions/tl-method.md) n’est pas défini, la variable `linkURL` est utilisée à la place.
