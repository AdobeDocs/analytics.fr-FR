---
title: ActivityMap.link
description: Personnalisez la manière dont Activity Map collecte le lien sur lequel l’utilisateur a cliqué.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 3a31f80b-dbee-4a45-ac3c-0b8ca198c95a
TQID: 'https://experienceleague.adobe.com/5NCARDGth07l5vixudVzLrE7FVrh82PS4xNrJ61gnow'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 308
ht-degree: 10%

---

# ActivityMap.link

La variable `ActivityMap.link` vous permet de remplacer la logique utilisée par Activity Map pour définir les valeurs de lien. Cette variable est utile dans les zones où vous souhaitez avoir plus de contrôle que ce que [`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md) fournit.

>[!CAUTION]
>Cette variable remplace complètement la logique Activity Map. La définition d’une fonction de remplacement ici qui renvoie des valeurs incorrectes peut entraîner des problèmes de collecte de données avec les dimensions Activity Map et la superposition Activity Map.

## Remplacement des valeurs de lien à l’aide de Web SDK

Vous pouvez utiliser [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) rappel pour modifier la payload de Web SDK ou abandonner l’envoi de données.

## Remplacement de lien à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## ActivityMap.link dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Affectez à cette variable une fonction qui :

* reçoit l’élément HTML sur lequel l’utilisateur a cliqué ; et
* Renvoie une valeur de chaîne. Cette valeur de chaîne est la valeur finale utilisée pour la dimension [Lien ](/help/components/dimensions/activity-map-link.md).

Si la valeur renvoyée est [false](https://developer.mozilla.org/fr-FR/docs/Glossaire/Falsy), toutes les variables de données contextuelles Activity Map sont effacées et aucune donnée de lien n’est suivie.

## Exemples

N’utilisez que l’attribut de titre des balises `<a>`. Si l’attribut de titre n’est pas présent, aucun lien n’est suivi.

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

Renvoyer le nom du lien défini manuellement dans `s.tl` s’il existe, sinon renvoyer l’URL du lien.

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

1. Si `linkName` est transmis, la méthode a été appelée par `tl()`. Renvoyez ce qui `tl()` transmis en tant que `linkName`.
2. Lorsqu’un `linkName` est appelé par Activity Map, il n’est jamais transmis. Appelez donc `customFunction()` avec l’élément de lien. Vous pouvez utiliser n’importe quelle fonction personnalisée que vous souhaitez pour renvoyer une valeur.
3. Si aucune des valeurs ci-dessus ne renvoie de valeur, utilisez le nom du lien normalement collecté comme solution de secours.
