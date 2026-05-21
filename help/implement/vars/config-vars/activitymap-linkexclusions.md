---
title: ActivityMap.linkExclusions
description: Filtrer les données d’Activity Map par nom de lien.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
TQID: https://experienceleague.adobe.com/y8RH2nGcIHYvrTwotHAbtFxu7hIXoh48FuU2OBsAuuM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 206
ht-degree: 17%

---

# ActivityMap.linkExclusions

La variable `ActivityMap.linkExclusions` vous permet de filtrer ou d’exclure de manière sélective des données Activity Map en fonction du texte de la dimension [Lien Activity Map](/help/components/dimensions/activity-map-link.md).

## Exclusions de liens dans l’extension Web SDK

Lorsque l’option **[!UICONTROL Activer la collecte de données de clic]** est activée, utilisez le bloc de code de rappel **[!UICONTROL Filtrer les propriétés du clic]**. Dans ce bloc de code, vous pouvez vérifier la valeur de `content.linkName` et modifier la valeur ou abandonner la collecte de données de suivi des liens.

## Exclusions de liens dans la bibliothèque JavaScript de Web SDK

Lorsque [`clickCollectionEnabled`](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) est activé, utilisez le rappel `filterClickDetails` dans l’objet `clickCollection`. Dans ce rappel, vous pouvez vérifier la valeur de `linkName` et modifier la valeur ou abandonner la collecte de données de suivi des liens.

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

## Exclusions de liens à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.ActivityMap.linkExclusions avec AppMeasurement

La variable `s.ActivityMap.linkExclusions` est une chaîne contenant des valeurs d’expressions délimitées par des virgules à exclure du suivi Activity Map. Si l’une des expressions correspond à la valeur collectée dans la dimension [Lien &#x200B;](/help/components/dimensions/activity-map-link.md), toutes les données Activity Map sont supprimées de l’accès. Notez que cette variable examine les `linkName`, et non les `linkUrl`.

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
