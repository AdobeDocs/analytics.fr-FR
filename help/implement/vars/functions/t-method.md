---
title: t
description: Permet d’envoyer un appel de suivi des pages vues à Adobe.
feature: Appmeasurement Implementation
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 56%

---

# t()

La méthode `t()` est un composant principal important d’Adobe Analytics. Elle prend toutes les variables Analytics définies sur la page, les compile dans une demande d’image et envoie ces données aux serveurs de collecte de données Adobe.

Prenons l’exemple du code JavaScript suivant :

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

L’exécution de la méthode `t()` prend toutes les variables Analytics définies et formule une URL basée sur ces variables. Certaines variables Analytics déterminent l’URL de l’image, tandis que d’autres déterminent les valeurs des paramètres de chaîne de requête.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20item
```

Adobe reçoit la demande d’image, puis analyse l’en-tête de la demande, l’URL et les paramètres de chaîne de requête. Les serveurs de collecte de données renvoient ensuite une image transparente de 1x1 pixel, affichée de manière invisible sur votre site.

## Envoi d’un événement à l’aide de l’extension Web SDK

Utilisez une action pour configurer l’envoi de données d’événement XDM à Adobe. Le flux de données reçoit ces données, applique les mappages configurés et transfère ces données à Adobe Analytics s’il s’agit d’un service ajouté à ce flux de données.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
1. Sous [!UICONTROL Actions], cliquez sur l’action souhaitée ou cliquez sur l’icône **’+’** pour ajouter une action.
1. Définissez la liste déroulante [!UICONTROL Extension] sur **[!UICONTROL Adobe Experience Platform Web SDK]** et le [!UICONTROL Type d’action] sur **[!UICONTROL Envoyer l’événement]**.

## Envoi d’un événement implémentant manuellement le SDK Web

Utilisez la commande `sendEvent` pour envoyer des données à Adobe. Le flux de données reçoit ces données, applique les mappages configurés et transfère ces données à Adobe Analytics s’il s’agit d’un service ajouté à ce flux de données.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Voir [`sendEvent`](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/sendevent/overview) dans la documentation de Web SDK pour plus d’informations.

## Appel de suivi des pages vues à l’aide de l’extension Adobe Analytics

L’extension Adobe Analytics dans la collecte de données Adobe Experience Platform dispose d’un emplacement dédié permettant de définir un appel de suivi des pages vues.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
1. Sous [!UICONTROL Actions], cliquez sur l’action souhaitée ou cliquez sur l’icône **’+’** pour ajouter une action.
1. Définissez la liste déroulante [!UICONTROL Extension] sur **[!UICONTROL Adobe Analytics]**, et le [!UICONTROL Type d’action] sur **[!UICONTROL Envoyer la balise]**.
1. Cochez la case `s.t()`.

## s.t() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Appelez la méthode `s.t()` lorsque vous souhaitez envoyer un appel de suivi à Adobe.

```js
s.t();
```

Vous pouvez éventuellement utiliser un objet comme argument pour remplacer des valeurs de variable. Pour plus d’informations, voir [Remplacements de variable](../../js/overrides.md).

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>Les versions précédentes d’AppMeasurement utilisaient plusieurs lignes de code pour appeler cette fonction. Le code supplémentaire prenait auparavant en charge les solutions pour différents navigateurs. La normalisation et les bonnes pratiques des navigateurs modernes ne nécessitent plus ce bloc de code. Seul l’appel de méthode `s.t()` est désormais nécessaire.
