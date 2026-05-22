---
title: ActivityMap.region
description: Personnalisez la manière dont Activity Map collecte la zone géographique sur laquelle l’utilisateur a cliqué.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
TQID: 'https://experienceleague.adobe.com/EVVto7LRuTewu9y9AHLAPGn7sbqhJU3QSjlNtjKE5bQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 15%

---

# ActivityMap.region

La variable `ActivityMap.region` vous permet de remplacer la logique utilisée par Activity Map pour définir les valeurs de région. Cette variable est utile dans les zones où vous souhaitez avoir plus de contrôle que ce que [`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md) fournit.

>[!CAUTION]
>Cette variable remplace complètement la logique Activity Map. La définition d’une fonction de remplacement ici qui renvoie des valeurs incorrectes peut entraîner des problèmes de collecte de données avec les dimensions Activity Map et la superposition Activity Map.

## Remplacement des valeurs de zone géographique à l’aide de Web SDK

Vous pouvez utiliser [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) rappel pour modifier la payload de Web SDK ou abandonner l’envoi de données.

## Remplacement de zone géographique à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## ActivityMap.region dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Affectez à cette variable une fonction qui :

* reçoit l’élément HTML sur lequel l’utilisateur a cliqué ; et
* Renvoie une valeur de chaîne. Cette valeur de chaîne est la valeur finale utilisée pour la dimension [Région &#x200B;](/help/components/dimensions/activity-map-region.md).

Si la valeur renvoyée est [false](https://developer.mozilla.org/fr-FR/docs/Glossaire/Falsy), toutes les variables de données contextuelles Activity Map sont effacées et aucune donnée de lien n’est suivie.

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
