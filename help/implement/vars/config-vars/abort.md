---
title: abort
description: La variable abort est une valeur booléenne qui empêche l’envoi d’un accès aux serveurs de collecte de données Adobe.
feature: Appmeasurement Implementation
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
autotag-review: '2026-05-22T07:53:09.657Z'
TQID: 'https://experienceleague.adobe.com/3RASISgJtY29aSGrGzO7070ZyH-B5cl3Cgv3aN7xjEU'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 343
ht-degree: 39%

---

# abort

La variable `abort` est une valeur booléenne qui peut empêcher l’envoi de l’appel de suivi suivant à Adobe. Il existe une fonctionnalité similaire dans le Web SDK qui vous permet de renvoyer des `false` avant l’envoi d’un événement XDM.

## Annuler l’envoi d’un événement à l’aide de l’extension Web SDK

Utilisez l’éditeur de code [!UICONTROL Activé avant le rappel d’envoi d’événement] et renvoyez le `false`.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous [!UICONTROL Adobe Experience Platform Web SDK].
1. Sous [!UICONTROL Collecte de données], cliquez sur le bouton **[!UICONTROL Modifier le avant le code de rappel d’envoi d’événement]**.
1. Dans l’éditeur de code, placez le code suivant dans toutes les conditions où vous souhaitez abandonner l’envoi de données à Edge :

```js
return false;
```

## Annuler l’envoi d’un événement implémentant manuellement le Web SDK

Utilisez le rappel `onBeforeEventSend` et renvoyez `false`. Voir [Modifier globalement les événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) dans la documentation de Web SDK pour plus d’informations.

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Utilisation de la variable abort dans l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.abort dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.abort` est une valeur booléenne. Sa valeur par défaut est `false`.

* Si celle-ci est définie sur `true`, l’appel de suivi suivant ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)) n’envoie aucune donnée à Adobe.
* Si celle-ci est définie sur `false` ou non définie, cette variable ne fait rien.

```js
s.abort = true;
```

>[!NOTE]
>
>La variable `abort` est réinitialisée à `false` après chaque appel de suivi. Si vous souhaitez abandonner les appels de suivi suivants sur la même page, définissez `abort` sur `true`.

La variable `abort` peut être définie dans la fonction [`doPlugins()`](../functions/doplugins.md) , qui est la dernière fonction à s’exécuter avant l’envoi d’une demande d’image à Adobe. Cet exemple fonctionne de la même manière que le rappel `onBeforeEventSend` à l’aide de Web SDK.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Vous pouvez centraliser la logique à utiliser pour identifier l’activité que vous ne souhaitez pas suivre, comme certains liens personnalisés ou liens externes dans les annonces affichées.
