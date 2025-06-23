---
title: ActivityMap.regionExclusions
description: Filtrez les données d’Activity Map par région.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 353282aa-860c-45dc-a6b0-8d9f1fa09f13
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 13%

---

# ActivityMap.regionExclusions

La variable `ActivityMap.regionExclusions` vous permet de filtrer ou d’exclure de manière sélective des données Activity Map en fonction des éléments de dimension collectés dans la dimension [Région Activity Map](/help/components/dimensions/activity-map-region.md).

## Exclusions de zones géographiques dans l’extension Web SDK

Lorsque l’option **[!UICONTROL Activer la collecte de données de clic]** est activée, utilisez le bloc de code de rappel **[!UICONTROL Filtrer les propriétés du clic]**. Dans ce bloc de code, vous pouvez vérifier la valeur de `content.linkRegion` et modifier la valeur ou abandonner la collecte de données de suivi des liens.

## Exclusions de zones géographiques dans la bibliothèque JavaScript Web SDK

Lorsque [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) est activé, utilisez le rappel `filterClickDetails` dans l’objet `clickCollection`. Dans ce rappel, vous pouvez vérifier la valeur de `linkRegion` et modifier la valeur ou abandonner la collecte de données de suivi des liens.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked region has personal links in it, don't send click data
      if(content.linkRegion.includes("personal")) {
        return false;
      }
    }
  }
});
```

## Exclusions de régions à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.ActivityMap.regionExclusions avec AppMeasurement

La variable `s.ActivityMap.regionExclusions` est une chaîne contenant des expressions délimitées par des virgules à exclure du suivi Activity Map. Si l’une des expressions correspond à la valeur collectée dans la dimension [Région Activity Map](/help/components/dimensions/activity-map-region.md), toutes les données Activity Map sont supprimées de l’accès.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionExclusions = "contact";
</script>

<!-- Clicking any of these links tracks normally. -->
<!-- While "contact" is present, it is not tracked in region. The region is "nav" -->
<nav>
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</nav>

<!-- Activity Map data is not tracked for any of these links. -->
<!-- All these links belong to the region "Personal contact information" -->
<div id="personal-contact-information">
 <a href="mailto:user@example.com">Example user</a>
 <a href="mailto:user2@example.com">Example user 2</a>
 <a href="mailto:user3@example.com">Example user 3</a>
</div>
```
