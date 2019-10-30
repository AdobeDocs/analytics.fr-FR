---
description: Vous pouvez utiliser la fonction s.tl() pour suivre des éléments personnalisés et configurer le rendu des superpositions pour le contenu dynamique.
seo-description: Vous pouvez utiliser la fonction s.tl() pour suivre des éléments personnalisés et configurer le rendu des superpositions pour le contenu dynamique.
seo-title: Utilisation de la fonction s.tl()
solution: Analytics
title: Utilisation de la fonction s.tl()
topic: Activity Map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# Utilisation de la fonction s.tl()

Vous pouvez utiliser la fonction s.tl() pour suivre des éléments personnalisés et configurer le rendu des superpositions pour le contenu dynamique.

## Tracking custom elements {#section_5D6688DFFFC241718249A9A0C632E465}

L’utilisation de la [fonction s.tl()](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html) au sein du module d’AppMeasurement vous permet de suivre les objets sur lesquels l’utilisateur clique, notamment ceux qui ne sont pas des balises d’ancrage ou des éléments d’image. [!DNL Activity Map] La fonction s.tl vous permet de suivre les éléments personnalisés qui ne conduisent pas à un chargement de page.

Dans la fonction s.tl, le paramètre linkName actuellement utilisé pour identifier les liens de sortie, les liens personnalisés, etc. is now also used to identify the Link ID for the [!DNL Activity Map] variable.

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

En d’autres termes, si vous utilisez cette fonction pour suivre vos éléments personnalisés, l’ID de lien est extrait de la valeur correspondant au troisième paramètre (linkName) dans la fonction s.tl. Il n’est pas extrait de l’algorithme de suivi des liens standard utilisé pour [le suivi par défaut](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) dans [!DNL Activity Map].

## Overlay rendering for dynamic content {#section_FD24B61A732149C7B58BA957DD84A5E7}

When the s.tl() function is called directly from the HTML element’s on-click event, [!DNL Activity Map] can display an overlay for that element when the web page is loaded. Exemple:

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

À chaque fois que le contenu d’une page web est ajouté à la page après le chargement initial de celle-ci, la fonction s.tl est appelée indirectement et nous ne pouvons pas afficher de superpositions pour ce nouveau contenu, à moins qu’il ne soit expressément activé/visité. Un nouveau processus de collecte des liens est ensuite déclenché depuis [!DNL Activity Map].

When the s.tl() function is not called directly from the HTML element’s on-click event, [!DNL Activity Map] can only display overlay once that element has been clicked by the user. Voici un exemple dans lequel la fonction s.tl() est appelée indirectement :

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

The best way for [!DNL Activity Map] to overlay dynamic content links is to have a customized ActivityMap.link function set up to call the same function whose return value is passed to s.tl. Voici un exemple :

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type=”button” onclick=”s.tl(this,’o’,makeLinkName(this)”>Add To Cart</button>
```

Ici, nous avons modifié la fonction ActivityMap.link pour qu’elle effectue l’une des trois actions suivantes lorsqu’elle est appelée :

1. Si linkName est transmis, la fonction ActivityMap.link est appelée par s.tl(), il suffit donc de renvoyer ce que s.tl a transmis en tant que linkName.
1. This is called by [!DNL Activity Map] at reporting time, so a linkName is never passed, and so call makeLinkName() with the link element. This is the crucial step here - the “makeLinkName(element)” call should be the same at the s.tl call’s 3rd argument in the `<button>` tag. Cela signifie que lorsque la fonction s.tl est appelée, nous suivons la chaîne renvoyée par makeLinkName. When [!DNL Activity Map] reports on the links on the page, is uses the same call to make a link.
1. La dernière solution consiste simplement à renvoyer la valeur originale renvoyée par la fonction de lien Activity Map par défaut. Le fait de conserver cette référence pour appeler le cas par défaut vous permet de ne remplacer ou écrire du code personnalisé que pour makeLinkName au lieu de devoir fournir une valeur de retour de lien pour tous les liens de la page.
