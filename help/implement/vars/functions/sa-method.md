---
title: sa
description: Permet de modifier la suite de rapports à tout moment de votre mise en œuvre.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---

# sa

La méthode `sa()` vous permet de modifier dynamiquement une suite de rapports à tout moment de la page. Si vous souhaitez envoyer des données à différentes suites de rapports sans rechargement de page, vous pouvez utiliser cette méthode.

## Utilisation de la méthode sa à l’aide de balises dans Adobe Experience Platform

Il n’existe pas de méthode souple pour modifier la suite de rapports dans l’interface. Vous pouvez définir la suite de rapports sous l’accordéon [!UICONTROL Gestion des bibliothèques] lors de la configuration de l’extension Adobe Analytics. Toutefois, vous ne pouvez pas modifier ni mettre à jour la suite de rapports à l’aide de règles. Si vous souhaitez mettre à jour les valeurs d’une suite de rapports après leur définition, utilisez l’éditeur de code personnalisé suivant la syntaxe AppMeasurement.

## s.sa() dans AppMeasurement et l’éditeur de code personnalisé

Appelez la méthode `s.sa()` pour modifier la suite de rapports de destination. Son seul argument est une chaîne contenant un identifiant de suite de rapports ou plusieurs identifiants de suite de rapports délimités par une virgule. L’argument d’identifiant de suite de rapports est obligatoire. N’utilisez pas d’espaces dans l’argument de chaîne.

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
