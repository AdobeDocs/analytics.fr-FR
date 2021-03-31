---
title: Utiliser la méthode tl() avec le Activity Map
description: Vous pouvez utiliser la méthode tl() pour effectuer le suivi des éléments personnalisés et configurer le rendu des incrustations pour le contenu dynamique.
feature: Activity Map
role: Professionnel, Administrateur
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 43%

---


# Utiliser la méthode `tl()` avec le Activity Map

Vous pouvez utiliser la méthode `tl()` pour suivre des éléments personnalisés et configurer le rendu des superpositions pour le contenu dynamique.

## Suivi d’éléments personnalisés

L’utilisation de la [`tl()` méthode](/help/implement/vars/functions/tl-method.md) au sein du module Activity Map d’AppMeasurement vous permet de suivre les objets sur lesquels l’utilisateur clique, notamment ceux qui ne sont pas des balises d’ancrage ou des éléments d’image. `tl()` permet d’effectuer le suivi de tout élément personnalisé qui n’entraîne pas le chargement d’une page.

Dans la méthode `tl()`, le paramètre `linkName` actuellement utilisé pour identifier les liens de sortie, les liens personnalisés, etc. est désormais utilisé pour identifier l’ID de lien pour la variable d’Activity Map.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

En d’autres termes, si vous utilisez `tl()` pour suivre vos éléments personnalisés, l’ID de lien est extrait de la valeur transmise en tant que troisième paramètre (nom du lien) dans la méthode `tl()`. Il n’est pas extrait de l’algorithme de suivi des liens standard utilisé pour le [suivi par défaut](activitymap-link-tracking-methodology.md) dans Activity Map.

## Rendu des superpositions pour le contenu dynamique

Lorsque la méthode `tl()` est appelée directement à partir du événement de clic de l’élément HTML, le Activity Map peut afficher une superposition pour cet élément lorsque la page Web est chargée. Exemple :

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

À chaque fois que le contenu d’une page web est ajouté à la page après le chargement initial de celle-ci, la méthode `tl()` est appelée indirectement et nous ne pouvons pas afficher de superpositions pour ce nouveau contenu, à moins qu’il ne soit expressément activé/visité. Un nouveau processus de collecte des liens est ensuite déclenché depuis Activity Map.

Lorsque la méthode `tl()` n’est pas appelée directement à partir de l’événement « onclick » de l’élément HTML, Activity Map peut uniquement afficher une superposition après que l’utilisateur a cliqué sur l’élément. Voici un exemple dans lequel la méthode `tl()` est appelée indirectement :

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Le meilleur moyen pour le Activity Map d’incruster des liens de contenu dynamique consiste à configurer une fonction `ActivityMap.link` personnalisée pour appeler la même fonction dont la valeur renvoyée est transmise à `tl()`. Par exemple :

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName)
{
    // if this is a s.tl call, just return string passed
    return linkName ||      
    // this is ActivityMap reporting time
    makeLinkName(element) ||
    // our custom function didn't return anything, so just return the default ActivityMap Link
    originalLinkFunction(element,linkName);
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Ici, nous avons remplacé la fonction `ActivityMap.link` pour effectuer l&#39;une des trois opérations lorsqu&#39;elle est appelée :

1. Si `linkName` est transmis, il a été appelé par `tl()`, donc renvoyez simplement ce que `tl()` a transmis en tant que `linkName`.
2. Lorsqu&#39;il est appelé par le Activity Map au moment du rapports, un `linkName` n&#39;est jamais transmis et, par conséquent, appelez `makeLinkName()` avec l&#39;élément de lien. Il s&#39;agit de l&#39;étape cruciale ici - l&#39;appel `makeLinkName(element)` doit être identique au troisième argument de l&#39;appel `tl()` dans la balise `<button>`. Cela signifie que lorsque `tl()` est appelé, nous suivons la chaîne renvoyée par `makeLinkName()`. Lorsque le Activity Map signale les liens de la page, il utilise le même appel pour créer un lien.
3. La dernière solution consiste simplement à renvoyer la valeur originale renvoyée par la fonction de lien Activity Map par défaut. Si vous conservez cette référence pour appeler dans le cas par défaut, vous n’avez qu’à remplacer ou à écrire du code personnalisé pour `makeLinkName()` et à ne pas avoir à fournir une valeur de retour de lien pour tous les liens de la page.
