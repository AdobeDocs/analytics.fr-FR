---
title: ActivityMap.regionIDAtattribute
description: Modifiez l’attribut recherché par Activity Map pour déterminer la région.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 11%

---

# ActivityMap.regionIDAtattribute

La variable `ActivityMap.regionIDAttribute` vous permet de modifier l’attribut recherché par Activity Map lors de la détermination de la dimension [Région Activity Map](/help/components/dimensions/activity-map-region.md). Si votre site est structuré de manière à rendre l’attribut `id` moins utile pour la région Activity Map, vous pouvez définir cette variable pour examiner un autre attribut.

## Attribut ID de région dans l’extension Web SDK

Lorsque l’option **[!UICONTROL Activer la collecte de données de clic]** est activée, utilisez le bloc de code de rappel **[!UICONTROL Filtrer les propriétés du clic]**. Dans ce bloc de code, vous pouvez vérifier la valeur de `content.clickedElement` et modifier la valeur ou abandonner la collecte de données de suivi des liens.

## Attribut ID de région dans la bibliothèque JavaScript de Web SDK

Lorsque [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) est activé, utilisez le rappel `filterClickDetails` dans l’objet `clickCollection`. Dans ce rappel, vous pouvez vérifier la valeur de `clickedElement` et personnaliser la logique de la région collectée.

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

## Attribut ID de région utilisant l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.ActivityMap.regionIDAtattribute avec AppMeasurement

La variable `s.ActivityMap.regionIDAttribute` est une chaîne qui représente l’attribut pour déterminer la dimension [Région Activity Map](/help/components/dimensions/activity-map-region.md). Cette variable est définie sur `id` par défaut. Si vous modifiez cette variable, Activity Map ne recherche plus l’attribut `id`, mais toujours d’autres critères pour déterminer la région (comme les éléments sémantiques).

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
