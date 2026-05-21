---
title: ActivityMap.regionIDAtattribute
description: Modifiez l’attribut recherché par Activity Map pour déterminer la région.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
TQID: https://experienceleague.adobe.com/4J2esEPxvV-weoNQM9X-ScFa6fIUERWVLCUme9GZygM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 237
ht-degree: 15%

---

# ActivityMap.regionIDAtattribute

La variable `ActivityMap.regionIDAttribute` vous permet de modifier l’attribut recherché par Activity Map lors de la détermination de la dimension [Région Activity Map](/help/components/dimensions/activity-map-region.md). Si votre site est structuré de manière à rendre l’attribut `id` moins utile pour la région Activity Map, vous pouvez définir cette variable pour examiner un autre attribut.

## Attribut ID de région dans l’extension Web SDK

Lorsque l’option **[!UICONTROL Activer la collecte de données de clic]** est activée, utilisez le bloc de code de rappel **[!UICONTROL Filtrer les propriétés du clic]**. Dans ce bloc de code, vous pouvez vérifier la valeur de `content.clickedElement` et modifier la valeur ou abandonner la collecte de données de suivi des liens.

## Attribut ID de région dans la bibliothèque JavaScript de Web SDK

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
