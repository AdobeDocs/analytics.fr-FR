---
description: L’indicateur abort peut être défini dans doPlugins afin que l’appel de suivi actuel ne soit pas envoyé.
keywords: Mise en œuvre d’Analytics
seo-description: L’indicateur abort peut être défini dans doPlugins afin que l’appel de suivi actuel ne soit pas envoyé.
seo-title: Indicateur s.abort
solution: Analytics
title: Indicateur s.abort
topic: Développeur et mise en œuvre
uuid: 0 c 6 ec 8 c 7-d 136-4851-8 cb 6-6 cb 1 b 7 f 6 f 0 dc
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

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
