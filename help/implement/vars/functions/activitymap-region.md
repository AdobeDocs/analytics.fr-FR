---
title: ActivityMap.region
description: Personnalisez la manière dont l’Activity Map collecte les clics sur la région.
feature: Variables
role: Admin, Developer
source-git-commit: 1fb57590714ad2412323416289dee967eef07fad
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 12%

---

# ActivityMap.region

La variable `ActivityMap.region` vous permet de remplacer la logique utilisée par l’Activity Map pour définir les valeurs de région. Cette variable est utile dans les zones où vous souhaitez avoir plus de contrôle que ce que [`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md) fournit.

>[!CAUTION]
>Cette variable remplace complètement la logique Activity Map. La définition d’une fonction de remplacement qui renvoie des valeurs incorrectes peut entraîner des problèmes de collecte de données avec les dimensions Activity Map et la superposition Activity Map.

## Remplacement des valeurs de région à l’aide du SDK Web

Vous pouvez utiliser le rappel [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) pour modifier la charge utile du SDK Web ou interrompre l’envoi de données.

## Remplacement de région à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## ActivityMap.region dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Attribuez à cette variable une fonction qui :

* reçoit l’élément d’HTML sur lequel l’utilisateur a cliqué ; et
* Renvoie une valeur string . Cette valeur string est la valeur finale utilisée pour la dimension [Région Activity Map](/help/components/dimensions/activity-map-region.md).

Si la valeur renvoyée est [falsy](https://developer.mozilla.org/fr-FR/docs/Glossaire/Falsy), toutes les variables de données contextuelles Activity Map sont effacées et aucune donnée de lien n’est suivie.

## Exemples

Utilisez un nom de balise en minuscules comme région :

```js
s.ActivityMap.region = function(clickedElement) {
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    var regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

Utilisez des noms de classe spécifiques comme région :

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  };
  while ((ele && (ele = ele.parentNode))) {
    if ((className = ele.className)) {
      let classes = className.split(' ');
      for (let i = 0; i < classes.length; i++) {
        if (classNames[classes[i]]) {
          return classes[i];
        }
      }
    }
  }
  return "BODY";
}
```
