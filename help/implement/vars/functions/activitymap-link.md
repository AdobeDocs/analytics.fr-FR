---
title: ActivityMap.link
description: Personnalisez la manière dont Activity Map collecte le lien sur lequel l’utilisateur a cliqué.
feature: Variables
role: Admin, Developer
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 8%

---

# ActivityMap.link

La variable `ActivityMap.link` vous permet de remplacer la logique utilisée par l’Activity Map pour définir les valeurs de lien. Cette variable est utile dans les zones où vous souhaitez avoir plus de contrôle que ce que [`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md) fournit.

>[!CAUTION]
>Cette variable remplace complètement la logique Activity Map. La définition d’une fonction de remplacement qui renvoie des valeurs incorrectes peut entraîner des problèmes de collecte de données avec les dimensions Activity Map et la superposition Activity Map.

## Remplacement des valeurs de lien à l’aide du SDK Web

Vous pouvez utiliser le rappel [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) pour modifier la charge utile du SDK Web ou interrompre l’envoi de données.

## Remplacement de lien à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## ActivityMap.link dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Attribuez à cette variable une fonction qui :

* reçoit l’élément d’HTML sur lequel l’utilisateur a cliqué ; et
* Renvoie une valeur string . Cette valeur string est la valeur finale utilisée pour la dimension [Lien Activity Map](/help/components/dimensions/activity-map-link.md).

Si la valeur renvoyée est [falsy](https://developer.mozilla.org/fr-FR/docs/Glossaire/Falsy), toutes les variables de données contextuelles Activity Map sont effacées et aucune donnée de lien n’est suivie.

## Exemples

N’utilisez que l’attribut title des balises `<a>`. Si l’attribut title n’est pas présent, aucun lien n’est suivi.

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

Renvoie le nom du lien défini manuellement dans `s.tl` s’il existe, sinon renvoie l’URL du lien.

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele && ele.tagName == 'A' && ele.href) {
    return ele.href;
  }
}
```

Au lieu de remplacer complètement la logique de lien par défaut, vous pouvez la modifier de manière conditionnelle.

```html
<script>
  // Copy the original link function
  var originalLinkFunction = s.ActivityMap.link;
  // Return the link name from s.tl, a modified activity map value, or the original activity map value
  s.ActivityMap.link = function(element,linkName)
  {
    return linkName || customFunction(element) || originalLinkFunction(element,linkName);
  };
</script>

<button type="button" onclick="s.tl(this,'o',customFunction(this)">Add To Cart</button>
```

1. Si `linkName` est transmis, la méthode a été appelée par `tl()`. Renvoie ce que `tl()` a transmis en tant que `linkName`.
2. Lorsqu&#39;il est appelé par un Activity Map, un `linkName` n&#39;est jamais transmis. Par conséquent, appelez `customFunction()` avec l&#39;élément de lien. Vous pouvez utiliser n’importe quelle fonction personnalisée dont vous souhaitez renvoyer une valeur.
3. Si aucune des valeurs renvoyées ci-dessus n’est utilisée, utilisez le nom du lien normalement collecté comme secours.
