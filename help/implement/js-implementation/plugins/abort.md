---
description: L’indicateur abort peut être défini dans doPlugins afin que l’appel de suivi actuel ne soit pas envoyé.
keywords: Analytics Implementation
solution: Analytics
title: Indicateur s.abort
topic: Developer and implementation
uuid: 0c6ec8c7-d136-4851-8cb6-6cb1b7f6f0dc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
