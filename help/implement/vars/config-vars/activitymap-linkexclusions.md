---
title: ActivityMap.linkExclusions
description: Filtrez les données Activity Map par nom de lien.
role: Admin, Developer
feature: Variables
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 11%

---

# ActivityMap.linkExclusions

La variable `ActivityMap.linkExclusions` vous permet de filtrer ou d’exclure des données Activity Map de manière sélective en fonction du texte de la dimension [Lien Activity Map](/help/components/dimensions/activity-map-link.md).

## Exclusions de liens dans l’extension SDK Web

Lorsque l’option **[!UICONTROL Activer la collecte de données de clic]** est activée, utilisez le bloc de code de rappel **[!UICONTROL Filtrer les propriétés de clic]** . Dans ce bloc de code, vous pouvez vérifier la valeur de `content.linkName` et modifier la valeur ou abandonner la collecte de données de suivi des liens.

## Exclusions de liens dans la bibliothèque JavaScript du SDK Web

Lorsque [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) est activé, utilisez le rappel `filterClickDetails` dans l’objet `clickCollection`. Dans ce rappel, vous pouvez vérifier la valeur de `linkName` et modifier la valeur ou abandonner la collecte de données de suivi des liens.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the link is a clickable telephone number, anonymize it
      if(content.linkUrl.includes("tel:")) {
        content.linkName = content.linkUrl = "Phone number";
      }
      // If the link is an email address, anonymize it
      if(content.linkUrl.includes("mailto:")) {
        content.linkName = content.linkUrl = "Email address";
      }
    }
  }
});
```

## Lier les exclusions à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.ActivityMap.linkExclusions à l’aide de AppMeasurement

La variable `s.ActivityMap.linkExclusions` est une chaîne contenant des valeurs délimitées par des virgules d’expressions à exclure du suivi Activity Map. Si l’une des expressions correspond à la valeur collectée dans la dimension [Lien Activity Map](/help/components/dimensions/activity-map-link.md), toutes les données Activity Map sont supprimées de l’accès. Notez que cette variable ne regarde pas `linkUrl`, mais `linkName`.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.linkExclusions = "Contact";
</script>

<!-- Clicking this link tracks normally -->
<a href="products.html">View our products</a>

<!-- Activity Map data is not tracked for this link -->
<a href="mailto:user@example.com">Contact this user</a>
```
