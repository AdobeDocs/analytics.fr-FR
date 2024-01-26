---
title: t
description: Permet d’envoyer un appel de suivi des pages vues à Adobe.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '453'
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
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe reçoit la demande d’image, puis analyse l’en-tête de la demande, l’URL et les paramètres de chaîne de requête. Les serveurs de collecte de données renvoient ensuite une image transparente de 1x1 pixel, affichée de manière invisible sur votre site.

## Envoyer un événement à l’aide de l’extension SDK Web

Utilisez une action pour configurer l’envoi de données d’événement XDM à Adobe. Le flux de données reçoit ces données, applique les mappages configurés et transmet ces données à Adobe Analytics s’il s’agit d’un service ajouté à ce flux de données.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
1. Sous [!UICONTROL Actions], cliquez sur l’action souhaitée ou cliquez sur le bouton **&#39;+&#39;** pour ajouter une action.
1. Définissez la variable [!UICONTROL Extension] Liste déroulante à **[!UICONTROL SDK Web Adobe Experience Platform]** et la variable [!UICONTROL Type d’action] to **[!UICONTROL Envoyer un événement]**.

## Envoyer manuellement l’événement en implémentant le SDK Web

Utilisez la variable `sendEvent` pour envoyer des données à Adobe. Le flux de données reçoit ces données, applique les mappages configurés et transmet ces données à Adobe Analytics s’il s’agit d’un service ajouté à ce flux de données.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Voir [Suivi des événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=fr) pour plus d’informations, voir la documentation du SDK Web .

## Appel de suivi des pages vues à l’aide de l’extension Adobe Analytics

L’extension Adobe Analytics de la collecte de données Adobe Experience Platform dispose d’un emplacement dédié défini un appel de suivi des pages vues.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
1. Sous [!UICONTROL Actions], cliquez sur l’action souhaitée ou cliquez sur le bouton **&#39;+&#39;** pour ajouter une action.
1. Définissez la variable [!UICONTROL Extension] Liste déroulante à **[!UICONTROL Adobe Analytics]**, et la variable [!UICONTROL Type d’action] to **[!UICONTROL Envoyer la balise]**.
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
