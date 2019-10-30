---
description: L’indicateur abort peut être défini dans doPlugins afin que l’appel de suivi actuel ne soit pas envoyé.
keywords: Mise en œuvre d’Analytics
seo-description: L’indicateur abort peut être défini dans doPlugins afin que l’appel de suivi actuel ne soit pas envoyé.
seo-title: Indicateur s.abort
solution: Analytics
title: Indicateur s.abort
topic: Développeur et mise en œuvre
uuid: 0c6ec8c7-d136-4851-8cb6-6cb1b7f6f0dc
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Indicateur s.abort

L’indicateur abort peut être défini dans doPlugins afin que l’appel de suivi actuel ne soit pas envoyé.

L’indicateur abort est réinitialisé à chaque appel de suivi, de sorte que si un appel de suivi consécutif doit également être abandonné, l’indicateur devra être redéfini dans doPlugins.

```js
s.doPlugins = function(s) { 
     s.campaign = s.getQueryParam("cid"); 
     if ((!s.campaign) && (!s.events)) { 
          s.abort = true; 
     } 
};
```

Ceci vous permet de centraliser la logique à utiliser pour identifier l’activité que vous ne souhaitez pas suivre, comme certains liens personnalisés ou liens externes dans les annonces affichées.
