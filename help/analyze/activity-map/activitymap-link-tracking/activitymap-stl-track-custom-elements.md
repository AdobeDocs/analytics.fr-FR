---
title: Utilisation de la méthode tl() avec Activity Map
description: Vous pouvez utiliser la méthode tl() pour effectuer le suivi des éléments personnalisés et configurer le rendu des superpositions pour le contenu dynamique.
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 43%

---

# Utilisez la variable `tl()` méthode avec Activity Map

Vous pouvez utiliser la méthode `tl()` pour suivre des éléments personnalisés et configurer le rendu des superpositions pour le contenu dynamique.

## Suivi d’éléments personnalisés

L’utilisation de la [`tl()` méthode](/help/implement/vars/functions/tl-method.md) au sein du module Activity Map d’AppMeasurement vous permet de suivre les objets sur lesquels l’utilisateur clique, notamment ceux qui ne sont pas des balises d’ancrage ou des éléments d’image. Utilisation `tl()`, vous pouvez effectuer le suivi des éléments personnalisés qui ne génèrent pas de chargement de page.

Dans la méthode `tl()`, le paramètre `linkName` actuellement utilisé pour identifier les liens de sortie, les liens personnalisés, etc. est désormais utilisé pour identifier l’ID de lien pour la variable d’Activity Map.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

En d’autres termes, si vous utilisez `tl()` pour effectuer le suivi de vos éléments personnalisés, l’ID de lien est extrait de la valeur transmise comme troisième paramètre (nom du lien) dans la variable `tl()` . Il n’est pas extrait de l’algorithme de suivi des liens standard utilisé pour le [suivi par défaut](activitymap-link-tracking-methodology.md) dans Activity Map.

## Rendu des superpositions pour le contenu dynamique

Lorsque la variable `tl()` est appelée directement à partir de l’événement &quot;onclick&quot; de l’élément de HTML, Activity Map peut afficher une superposition pour cet élément lorsque la page web est chargée. Exemple :

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

Le meilleur moyen pour un Activity Map de superposer des liens de contenu dynamique consiste à définir une `ActivityMap.link` configurée pour appeler la même fonction que celle dont la valeur renvoyée est transmise à `tl()`. Par exemple :

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

Ici, nous avons remplacé le `ActivityMap.link` pour effectuer l’une des trois opérations suivantes lorsqu’elle est appelée :

1. If `linkName` est transmis, puis il a été appelé par `tl()`, alors renvoyez simplement ce qui suit : `tl()` transmis en tant que `linkName`.
2. Lorsqu’elle est appelée par le Activity Map au moment de la création de rapports, une `linkName` n’est jamais transmis, et l’appel `makeLinkName()` avec l’élément link . C&#39;est là une étape cruciale : `makeLinkName(element)` doit être identique à l’appel `tl()` 3e argument de l’appel dans la variable `<button>` balise . Cela signifie que lorsque `tl()` est appelée, nous suivons la chaîne renvoyée par `makeLinkName()`. Lorsque Activity Map crée des rapports sur les liens de la page, il utilise le même appel pour créer un lien.
3. La dernière solution consiste simplement à renvoyer la valeur originale renvoyée par la fonction de lien Activity Map par défaut. Si vous conservez cette référence pour appeler dans le cas par défaut, vous n’avez plus qu’à remplacer ou à écrire du code personnalisé pour `makeLinkName()` et ne pas avoir à fournir une valeur de retour de lien pour tous les liens de la page.
