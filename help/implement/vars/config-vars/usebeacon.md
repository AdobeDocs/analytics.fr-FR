---
title: useBeacon
description: useBeacon vous permet de forcer AppMeasurement à utiliser l’API sendBeacon des navigateurs
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 62%

---

# useBeacon

La plupart des navigateurs modernes incluent la méthode native `navigator.sendBeacon()`. Elle envoie de manière asynchrone une petite quantité de données via HTTP à un serveur web. AppMeasurement peut utiliser la méthode `navigator.sendBeacon()` si la variable `useBeacon` est activée. Il est utile pour les liens de sortie et les autres situations où vous souhaitez envoyer des informations avant le déchargement de la page.

Si `useBeacon` est activé, l’accès suivant envoyé à Adobe utilise la méthode `navigator.sendBeacon()` du navigateur au lieu d’une demande d’image `GET` standard. Cette variable s’applique aux demandes d’image [`s.t()`](../functions/t-method.md) et aux demandes d’image [`s.tl()`](../functions/tl-method.md). Elle nécessite AppMeasurement 2.17.0 ou une version ultérieure.

>[!TIP]
>
> AppMeasurement active automatiquement les demandes d’image de lien de sortie `useBeacon`.

La variable `useBeacon` est ignorée lorsque le visiteur utilise un navigateur qui ne prend pas en charge `navigator.sendBeacon()`. L’utilisation de cette variable nécessite AppMeasurement 2.16.0 ou une version ultérieure.

## Utilisation de l’API sendBeacon à l’aide de l’extension SDK Web

La case à cocher **[!UICONTROL Le document se décharge]** dans une configuration d’action détermine si les données envoyées à Adobe utilisent l’API sendBeacon.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Rules] , puis cliquez sur la règle de votre choix.
1. Sous [!UICONTROL Actions], cliquez sur l’action souhaitée ou cliquez sur l’icône **&#39;+&#39;** pour ajouter une nouvelle action.
1. Définissez la liste déroulante [!UICONTROL Extension] sur **[!UICONTROL SDK Web Adobe Experience Platform]** et le [!UICONTROL Type d’action] sur **[!UICONTROL Envoyer l’événement]**
1. Cochez la case **[!UICONTROL Le document se décharge]** à droite.

Si cette case est cochée, les données sont envoyées à l’Adobe à l’aide de l’API sendBeacon. Cette case est désactivée par défaut.

## Utilisation de l’API sendBeacon pour implémenter manuellement le SDK Web

Définissez `documentUnloading` sur `true` lors de l’envoi d’un événement. Si elle n’est pas définie, sa valeur par défaut est `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Pour plus d’informations, voir [Utilisation de l’API sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=fr#using-the-sendbeacon-api) dans la documentation du SDK Web.

## Utilisation de la balise à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.useBeacon dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.useBeacon` est une valeur booléenne qui détermine si AppMeasurement utilise la méthode `navigator.sendBeacon()` du navigateur. Sa valeur par défaut est `false`. Définissez cette variable sur `true` avant d’appeler une fonction de suivi si vous souhaitez utiliser la nature asynchrone de `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Après l’exécution d’un appel de suivi, cette variable est réinitialisée sur `false`. Si votre mise en œuvre envoie plusieurs demandes d’image au même chargement de page (comme les applications d’une seule page), définissez cette variable sur `true` avant chaque appel de suivi.
