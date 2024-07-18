---
title: abort
description: La variable abort est une valeur booléenne qui empêche l’envoi d’un accès aux serveurs de collecte de données Adobe.
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 5ef8ba686a13f8b4ab592c0b48a9c074b0477fcf
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 39%

---

# abort

La variable `abort` est une valeur booléenne qui peut empêcher l’envoi de l’appel de suivi suivant à Adobe. Il existe une fonctionnalité similaire dans le SDK Web qui vous permet de renvoyer `false` avant l’envoi d’un événement XDM.

## Annuler l’envoi d’un événement à l’aide de l’extension SDK Web

Utilisez l’éditeur de code [!UICONTROL Activé avant le rappel d’envoi d’événement] et renvoyez `false`.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton **[!UICONTROL Configurer]** sous [!UICONTROL SDK Web Adobe Experience Platform].
1. Sous [!UICONTROL Collecte de données], cliquez sur le bouton **[!UICONTROL Modifier avant l’envoi du code de rappel d’événement]** .
1. Dans l’éditeur de code, placez le code suivant sous toutes les conditions que vous souhaitez éviter d’envoyer des données à Edge :

```js
return false;
```

## Annuler l’envoi manuel d’un événement mettant en oeuvre le SDK Web

Utilisez le rappel `onBeforeEventSend` et renvoyez `false`. Pour plus d’informations, voir [Modification des événements globalement](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) dans la documentation du SDK Web.

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
>La variable `abort` est réinitialisée à `false` après chaque appel de suivi. Si vous souhaitez abandonner les appels de suivi suivants sur la même page, définissez à nouveau `abort` sur `true`.

La variable `abort` peut être définie dans la fonction [`doPlugins()`](../functions/doplugins.md), qui est la dernière fonction à exécuter avant l’envoi d’une demande d’image à Adobe. Cet exemple fonctionne de la même manière que le rappel `onBeforeEventSend` à l’aide du SDK Web.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Vous pouvez centraliser la logique à utiliser pour identifier l’activité que vous ne souhaitez pas suivre, comme certains liens personnalisés ou liens externes dans les annonces affichées.
