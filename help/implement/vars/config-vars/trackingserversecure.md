---
title: trackingServerSecure
description: Permet de déterminer l’emplacement où les demandes d’image sont envoyées sur les pages HTTPS.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 66%

---

# trackingServerSecure

Adobe collecte des données sur votre site en recevant une demande d’image générée par le visiteur. La variable `trackingServerSecure` détermine l’emplacement où une demande d’image est envoyée via HTTPS. Celle-ci détermine également l’emplacement où les cookies des visiteurs sont stockés. Si cette variable n’est pas correctement définie, votre mise en œuvre peut entraîner une perte de données.

>[!WARNING]
>
>Si vous modifiez cette valeur, AppMeasurement recherche les cookies à un autre emplacement. Le nombre de visiteurs uniques peut augmenter temporairement la création de rapports lorsque les cookies de visiteurs sont définis au nouvel emplacement.

## Domaine Edge utilisant l’extension Web SDK

Web SDK utilise le domaine [!UICONTROL Edge] pour gérer le serveur de suivi et le serveur de suivi sécurisé. Vous pouvez définir la valeur du domaine [!UICONTROL Edge souhaité] lors de la configuration de l’extension Web SDK.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous [!UICONTROL Adobe Experience Platform Web SDK].
1. Définissez le champ de texte **[!UICONTROL domaine Edge]** souhaité.

Voir [Configurer l’extension Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=fr) dans la documentation de Web SDK pour plus d’informations.

>[!TIP]
>
>Si votre organisation passe à Web SDK à partir d’une implémentation d’extension AppMeasurement ou Analytics, ce champ peut utiliser la même valeur contenue dans `trackingServerSecure` (ou `trackingServer`).

## Domaine Edge implémentant manuellement le SDK Web

Configurez le SDK à l’aide de [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr). Le champ est une chaîne qui détermine le domaine vers lequel envoyer des données.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Serveur de suivi SSL utilisant l’extension Adobe Analytics

[!UICONTROL Le serveur de suivi SSL] est un champ sous l’accordéon [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Général], qui affiche le champ [!UICONTROL Serveur de suivi SSL].

Si ce champ n’est pas renseigné, la valeur de la variable [`trackingServer`](trackingserver.md) est utilisée par défaut.

## s.trackingServerSecure dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.trackingServerSecure` est une chaîne qui contient l’emplacement d’envoi des demandes d’image. Il s’agit presque toujours d’un sous-domaine de votre site. Les pratiques modernes de confidentialité dans les navigateurs rendent généralement les cookies tiers peu fiables. Si cette variable est vide, elle utilise la valeur de la variable `s.trackingServer`.

La valeur de cette variable est presque toujours un domaine propriétaire, tel que `data.example.com`. Pour plus d’informations sur le processus des cookies propriétaires, voir [Cookies propriétaires dans Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=fr) dans le guide d’utilisation des services principaux.

La personne qui configure initialement la mise en œuvre des cookies propriétaires définit également le domaine et le sous-domaine utilisés. Par exemple :

```js
s.trackingServerSecure = "data.example.com";
```

Les enregistrements CNAME renvoient généralement vers un sous-domaine sur `data.adobedc.net`, `sc.adobedc.net` ou `2o7.net`.
