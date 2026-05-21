---
title: doPlugins
description: Permet de configurer la logique juste avant qu’un accès ne soit compilé et envoyé à Adobe.
feature: Appmeasurement Implementation
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
role: Admin, Developer
TQID: https://experienceleague.adobe.com/T-AyesoP2IMk3J-ftdnR-o48HqTmoRsAYtaIgn9cc1Q
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
source-wordcount: 326
ht-degree: 61%

---

# doPlugins

La variable `doPlugins` agit comme un « dernier appel » pour définir des valeurs dans votre mise en œuvre. Il s’agit de l’endroit idéal pour effectuer des appels aux [méthodes de plug-in](../plugins/impl-plugins.md) et définir toutes les variables souhaitées avant l’envoi d’une demande d’image. Si l’option [`usePlugins`](../config-vars/useplugins.md) est activée, celle-ci s’exécute automatiquement juste avant que n’importe quel type de demande d’image ne soit compilé et envoyé à Adobe, notamment :

* Tous les appels de page vue ([`t()`](t-method.md))
* Tous les appels de suivi de liens ([`tl()`](tl-method.md)), y compris les liens de téléchargement et de sortie automatiques

Utilisez la variable `doPlugins` pour appeler le code du plug-in et définir les valeurs des variables finales juste avant la compilation et l’envoi d’une demande d’image à Adobe.

## Utiliser le code de rappel d’envoi d’événement On Before à l’aide de l’extension Web SDK

Au lieu de `doPlugins`, le SDK Web utilise des `onBeforeEventSend` avec des fonctionnalités similaires.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous [!UICONTROL Adobe Experience Platform Web SDK].
1. Sous [!UICONTROL Collecte de données], cliquez sur le bouton **[!UICONTROL Modifier le avant le code de rappel d’envoi d’événement]**.
1. Placez le code de votre choix dans l’éditeur.

## Utilisation `onBeforeEventSend` mise en œuvre manuelle de Web SDK

Au lieu de `doPlugins`, le SDK Web utilise des `onBeforeEventSend` avec des fonctionnalités similaires. Voir [Modifier globalement les événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=fr#modifying-events-globally) dans la documentation de Web SDK pour plus d’informations.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Plug-ins utilisant l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.doPlugins dans AppMeasurement et le code personnalisé de

Définissez la variable `s.doPlugins` sur une fonction contenant le code souhaité. La fonction s’exécute automatiquement lorsque vous effectuez un appel de suivi.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
>Définissez une fonction sur la variable `doPlugins` une seule fois dans votre mise en œuvre. Si vous définissez la variable `doPlugins` plusieurs fois, seul le code le plus récent est utilisé.

## Exemples

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
>Les versions précédentes d’AppMeasurement comportaient un code légèrement différent `doPlugins()`. Adobe recommande d’utiliser le format ci-dessus (bonne pratique).
