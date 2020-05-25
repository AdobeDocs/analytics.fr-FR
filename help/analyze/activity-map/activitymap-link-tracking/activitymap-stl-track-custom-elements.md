---
description: Vous pouvez utiliser la méthode s.tl() pour suivre des éléments personnalisés et configurer le rendu des superpositions pour le contenu dynamique.
title: Utilisation de la méthode s.tl()
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Utilisation de la méthode `tl()`

Vous pouvez utiliser la méthode `tl()` pour suivre des éléments personnalisés et configurer le rendu des superpositions pour le contenu dynamique.

## Suivi d’éléments personnalisés {#section_5D6688DFFFC241718249A9A0C632E465}

L’utilisation de la [`tl()` méthode](/help/implement/vars/functions/tl-method.md) au sein du module Activity Map d’AppMeasurement vous permet de suivre les objets sur lesquels l’utilisateur clique, notamment ceux qui ne sont pas des balises d’ancrage ou des éléments d’image. La fonction s.tl vous permet de suivre les éléments personnalisés qui ne conduisent pas à un chargement de page.

Dans la méthode `tl()`, le paramètre `linkName` actuellement utilisé pour identifier les liens de sortie, les liens personnalisés, etc. est désormais utilisé pour identifier l’ID de lien pour la variable d’Activity Map.

```js
s.tl(this,linkType,linkName,variableOverrides)
```

En d’autres termes, si vous utilisez `s.tl()` pour suivre vos éléments personnalisés, l’ID de lien est extrait de la valeur correspondant au troisième paramètre (linkName) dans la méthode `s.tl()`. Il n’est pas extrait de l’algorithme de suivi des liens standard utilisé pour le [suivi par défaut](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) dans Activity Map.

## Rendu des superpositions pour le contenu dynamique {#section_FD24B61A732149C7B58BA957DD84A5E7}

Lorsque la fonction s.tl() est appelée directement à partir de l’événement « onclick » de l’élément HTML, Activity Map peut afficher une superposition pour cet élément quand la page web est chargée. Exemple :

```html
<div onclick="s.tl(this,'o','Example custom link')">Example link text</a>
```

À chaque fois que le contenu d’une page web est ajouté à la page après le chargement initial de celle-ci, la méthode `tl()` est appelée indirectement et nous ne pouvons pas afficher de superpositions pour ce nouveau contenu, à moins qu’il ne soit expressément activé/visité. Un nouveau processus de collecte des liens est ensuite déclenché depuis Activity Map.

Lorsque la méthode `tl()` n’est pas appelée directement à partir de l’événement « onclick » de l’élément HTML, Activity Map peut uniquement afficher une superposition après que l’utilisateur a cliqué sur l’élément. Voici un exemple dans lequel la méthode `tl()` est appelée indirectement :

```html
<div onclick="someFn(event)"></div>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

La meilleure façon de superposer des liens de contenu dynamique dans Activity Map consiste à configurer une fonction ActivityMap.link personnalisée pour qu’elle appelle la même fonction que celle dont la valeur renvoyée est transmise à `s.tl`. Par exemple :

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName) {
    return linkName ||      // if this is a s.tl call, just return string passed
        makeLinkName(element) || // this is ActivityMap reporting time
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Ici, nous avons modifié la fonction ActivityMap.link pour qu’elle effectue l’une des trois actions suivantes lorsqu’elle est appelée :

1. Si linkName est transmis, la fonction ActivityMap.link est appelée par s.tl(), il suffit donc de renvoyer ce que s.tl a transmis en tant que linkName.
2. Cette fonction est appelée par Activity Map lors de la création de rapports, donc un paramètre linkName n’est jamais transmis. Il convient donc d’appeler makeLinkName() avec l’élément de lien. Cette étape est cruciale : l’appel de « makeLinkName(element) » doit être identique au 3e argument de l’appel de s.tl dans la balise `<button>`. Cela signifie que lorsque la fonction s.tl est appelée, nous suivons la chaîne renvoyée par makeLinkName. Lorsque Activity Map tient compte des liens de la page, il utilise le même appel pour créer un lien.
3. La dernière solution consiste simplement à renvoyer la valeur originale renvoyée par la fonction de lien Activity Map par défaut. Le fait de conserver cette référence pour appeler le cas par défaut vous permet de ne remplacer ou écrire du code personnalisé que pour makeLinkName au lieu de devoir fournir une valeur de retour de lien pour tous les liens de la page.
