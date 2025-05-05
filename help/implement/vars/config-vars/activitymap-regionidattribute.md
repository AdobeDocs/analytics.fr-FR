---
title: ActivityMap.regionIDAttribute
description: Modifiez l’attribut que l’Activity Map recherche pour déterminer la région.
feature: Variables
role: Admin, Developer
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 10%

---

# ActivityMap.regionIDAttribute

La variable `ActivityMap.regionIDAttribute` vous permet de modifier l’attribut que l’Activity Map recherche lors de la détermination de la dimension [Région Activity Map](/help/components/dimensions/activity-map-region.md). Si votre site est structuré d’une manière qui rend l’attribut `id` moins utile pour la région Activity Map, vous pouvez définir cette variable pour qu’elle examine un autre attribut.

## Attribut Identifiant de région dans l’extension SDK Web

Lorsque l’option **[!UICONTROL Activer la collecte de données de clic]** est activée, utilisez le bloc de code de rappel **[!UICONTROL Filtrer les propriétés de clic]** . Dans ce bloc de code, vous pouvez vérifier la valeur de `content.clickedElement` et modifier la valeur ou abandonner la collecte de données de suivi des liens.

## Attribut Identifiant de région dans la bibliothèque JavaScript du SDK Web

Lorsque [`clickCollectionEnabled`](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) est activé, utilisez le rappel `filterClickDetails` dans l’objet `clickCollection`. Dans ce rappel, vous pouvez vérifier la valeur de `clickedElement` et personnaliser la logique de la région collectée.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked element was in a table, set the region to the contents of the data-custom attribute
      // If the clicked element was not in a table, or if the data-custom attribute doesn't exist, leave region as-is
      content.region = content.clickedElement.closest('table')?.getAttribute('data-custom') || content.region;
    }
  }
});
```

## Attribut Identifiant de région utilisant l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.ActivityMap.regionIDAtattribute à l’aide d’AppMeasurement

La variable `s.ActivityMap.regionIDAttribute` est une chaîne qui représente l’attribut permettant de déterminer la dimension [Région Activity Map](/help/components/dimensions/activity-map-region.md). Cette variable est définie sur `id` par défaut. Si vous modifiez cette variable, Activity Map ne recherche plus l’attribut `id`, mais recherche toujours d’autres critères pour déterminer la région (comme les éléments sémantiques).

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionIDAttribute = "data-custom";
</script>

<!-- Clicking any of these links populates the region dimension with 'left-nav' -->
<div id="676967617A656C6C65" data-custom="left-nav">
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</div>
```
