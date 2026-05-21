---
title: useBeacon
description: useBeacon vous permet de forcer AppMeasurement à utiliser l’API sendBeacon des navigateurs
feature: Appmeasurement Implementation
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
role: Admin, Developer
TQID: https://experienceleague.adobe.com/-drQZhKcoWzWfwcbFKms2xV2eunuNYIjkm4AWTmD-Pg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 406
ht-degree: 63%

---

# useBeacon

La plupart des navigateurs modernes incluent la méthode native `navigator.sendBeacon()`. Elle envoie de manière asynchrone une petite quantité de données via HTTP à un serveur web. AppMeasurement peut utiliser la méthode `navigator.sendBeacon()` si la variable `useBeacon` est activée. Il est utile pour les liens de sortie et les autres situations où vous souhaitez envoyer des informations avant le déchargement de la page.

Si `useBeacon` est activé, l’accès suivant envoyé à Adobe utilise la méthode `navigator.sendBeacon()` du navigateur au lieu d’une demande d’image `GET` standard. Cette variable s’applique aux demandes d’image [`s.t()`](../functions/t-method.md) et aux demandes d’image [`s.tl()`](../functions/tl-method.md). Elle nécessite AppMeasurement 2.17.0 ou une version ultérieure.

>[!TIP]
>
>AppMeasurement active automatiquement les demandes d’image de lien de sortie `useBeacon`.

La variable `useBeacon` est ignorée lorsque le visiteur utilise un navigateur qui ne prend pas en charge `navigator.sendBeacon()`. L’utilisation de cette variable nécessite AppMeasurement 2.16.0 ou une version ultérieure.

## Utiliser l’API sendBeacon à l’aide de l’extension Web SDK

La case à cocher **[!UICONTROL Le document sera déchargé]** dans une configuration d’action détermine si les données envoyées à Adobe utilisent l’API sendBeacon.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur la règle de votre choix.
1. Sous [!UICONTROL Actions], cliquez sur l’action souhaitée ou cliquez sur l’icône **’+’** pour ajouter une nouvelle action.
1. Définissez la liste déroulante [!UICONTROL Extension] sur **[!UICONTROL Adobe Experience Platform Web SDK]** et le [!UICONTROL Type d’action] sur **[!UICONTROL Envoyer l’événement]**
1. Cochez la case **[!UICONTROL Le document sera déchargé]** à droite.

Si cette case est cochée, les données sont envoyées à Adobe à l’aide de l’API sendBeacon. Cette case est désactivée par défaut.

## Utiliser l’API sendBeacon pour implémenter manuellement le SDK Web

Définissez la `documentUnloading` sur `true` lors de l’envoi d’un événement. Si elle n’est pas définie, sa valeur par défaut est `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Voir [Utilisation de l’API sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=fr#using-the-sendbeacon-api) dans la documentation de Web SDK pour plus d’informations.

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
