---
title: linkURL
description: Permet de remplacer l’URL de lien générée automatiquement utilisée par AppMeasurement dans les appels de suivi des liens.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 75%

---

# linkURL

Chaque fois qu’un appel de suivi des liens est envoyé à Adobe, les serveurs de collecte de données détectent automatiquement l’URL. Utilisez la variable `linkURL` pour remplacer l’URL détectée.

## URL du lien à l’aide du SDK Web

L’URL du lien est [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=fr) sous le champ XDM `web.webInteraction.URL`.

## URL du lien à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.linkURL dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.linkURL` est une chaîne contenant l’URL du navigateur lorsque l’utilisateur a cliqué sur le lien. Cette variable ne renseigne aucune dimension disponible dans les rapports.

```js
s.linkURL = "https://example.com";
```

Si le troisième argument de la méthode [tl()](../functions/tl-method.md) n’est pas défini, la variable `linkURL` est utilisée à la place.
