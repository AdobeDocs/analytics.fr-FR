---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.registerPreTrackCallback et s.registerPostTrackCallback

Ces fonctions acceptent comme paramètres : rappel (fonction) et les paramètres de cette fonction. Par exemple :

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

Le rappel est appelé avec `requestUrl` et les paramètres transmis lorsque le rappel est enregistré. Cela se produit avant ou après l’appel de suivi, selon la méthode utilisée pour enregistrer le rappel.

L’ordre dans lequel ces rappels sont appelés n’est pas garanti. Les rappels enregistrés dans la préfonction sont appelés après la création de l’URL de suivi finale. Les post-rappels sont appelés lors d’un appel de suivi réussi (si l’appel de suivi échoue, ces fonctions ne sont pas appelées). Les rappels enregistrés avec `registerPreTrackCallback` n’ont aucun impact sur l’appel de suivi. De plus, l’appel de ces méthodes de suivi dans un rappel enregistré n’est pas recommandé et peut entraîner une boucle sans fin.
