---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.linkType

Contient le type de lien déterminé automatiquement, le cas échéant. Peut être définie sur l’un des paramètres suivants :

    * `d` (téléchargement)
    * `e` (sortie)
    * `o` (personnalisé/autre)

Il s’agit du paramètre `pe` dans la demande d’image. Si elle est définies avec `linkURL` ou `linkName`, un appel au serveur est envoyé en tant que lien de téléchargement, de sortie ou personnalisé.

*Remarque : La variable[`pageName`](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.html)ne peut pas être définie pour un téléchargement de fichier, un lien de sortie ou un lien personnalisé, car chaque type de lien n’est pas une page vue et n’est associé à aucun nom de page.*


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
