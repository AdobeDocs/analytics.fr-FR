---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 1773e84809e04b3be25c77bf1fb8ad8317b7f8c0

---


# s-linkURL

The URL of the link, which acts as the name if a `linkName` does not exist. Peut être définie sur n’importe quelle chaîne d’URL. Il s’agit du paramètre `pev1` dans la demande d’image.


If set with [`linkType`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html), an image request will be sent as a download, custom or exit link.


**Exemple**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```
