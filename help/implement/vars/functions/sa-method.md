---
title: sa
description: Modifiez la suite de rapports à tout moment de votre implémentation.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# sa

La `sa()` méthode vous permet de modifier dynamiquement une suite de rapports à tout moment de la page. Si vous souhaitez envoyer des données à différentes suites de rapports sans rechargement de page, vous pouvez utiliser cette méthode.

## Utilisation de la méthode sa dans Adobe Experience Platform Launch

Il n’existe pas de méthode souple pour modifier la suite de rapports dans l’interface. Vous pouvez définir la suite de rapports sous l’ [!UICONTROL Library Management] accordéon lors de la configuration de l’extension Adobe Analytics. Toutefois, vous ne pouvez pas modifier ni mettre à jour la suite de rapports à l’aide de règles. Si vous souhaitez mettre à jour les valeurs d’une suite de rapports après leur définition, utilisez l’éditeur de code personnalisé suivant la syntaxe AppMeasurement.

## s.sa() dans AppMeasurement et Lancement de l’éditeur de code personnalisé

Appelez la `s.sa()` méthode pour modifier la suite de rapports de destination. Son seul argument est une chaîne contenant un identifiant de suite de rapports ou plusieurs identifiants de suite de rapports délimités par une virgule. L&#39;argument ID de suite de rapports est obligatoire. N’utilisez pas d’espaces dans l’argument de chaîne.

```js
s.sa("examplersid");
```

## Exemple

Vous pouvez modifier la suite de rapports si l’utilisateur effectue une action spécifique sur votre site.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
