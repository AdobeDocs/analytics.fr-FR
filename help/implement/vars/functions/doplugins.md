---
title: doPlugins
description: Permet de configurer la logique juste avant qu’un accès ne soit compilé et envoyé à Adobe.
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 63%

---

# doPlugins

La variable `doPlugins` agit comme un « dernier appel » pour définir des valeurs dans votre mise en œuvre. C&#39;est l&#39;endroit idéal pour passer des appels à [Méthodes de plug-in](../plugins/impl-plugins.md) et définissez les variables souhaitées avant l’envoi d’une demande d’image. Si l’option [`usePlugins`](../config-vars/useplugins.md) est activée, celle-ci s’exécute automatiquement juste avant que n’importe quel type de demande d’image ne soit compilé et envoyé à Adobe, notamment :

* Tous les appels de page vue ([`t()`](t-method.md))
* Tous les appels de suivi de liens ([`tl()`](tl-method.md)), y compris les liens de téléchargement et de sortie automatiques

Utilisez la variable `doPlugins` pour appeler le code du plug-in et définir les valeurs des variables finales juste avant la compilation et l’envoi d’une demande d’image à Adobe.

## Utiliser le code de rappel On Before Event Send à l’aide de l’extension SDK Web

Au lieu de `doPlugins`, le SDK Web utilise `onBeforeEventSend` avec des fonctionnalités similaires.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez au [!UICONTROL Extensions] , puis cliquez sur le bouton **[!UICONTROL Configurer]** bouton sous [!UICONTROL SDK Web Adobe Experience Platform].
1. Sous [!UICONTROL Collecte de données], cliquez sur le **[!UICONTROL Modifier avant le code de rappel d’envoi d’événement]** bouton .
1. Placez le code de votre choix dans l’éditeur.

## Utilisation `onBeforeEventSend` implémentation manuelle du SDK Web

Au lieu de `doPlugins`, le SDK Web utilise `onBeforeEventSend` avec des fonctionnalités similaires. Voir [Modification globale des événements](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) pour plus d’informations, voir la documentation du SDK Web .

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Modules externes à l’aide de l’extension Adobe Analytics

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
