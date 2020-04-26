---
title: trackingServerSecure
description: Permet de déterminer l’emplacement où les demandes d’image sont envoyées sur les pages HTTPS.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# trackingServerSecure

Adobe collecte des données sur votre site en recevant une demande d’image générée par le visiteur. La variable `trackingServerSecure` détermine l’emplacement où une demande d’image est envoyée via HTTPS. Celle-ci détermine également l’emplacement où les cookies des visiteurs sont stockés. Si cette variable n’est pas correctement définie, votre mise en œuvre peut entraîner une perte de données.

>[!IMPORTANT] Si vous modifiez cette valeur, AppMeasurement recherche les cookies à un autre emplacement. Le nombre de visiteurs uniques peut augmenter temporairement la création de rapports lorsque les cookies de visiteurs sont définis au nouvel emplacement.

## Serveur de suivi SSL dans Adobe Experience Platform Launch

[!UICONTROL Le serveur de suivi SSL] est un champ sous l’accordéon [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Général], qui affiche le champ [!UICONTROL Serveur de suivi SSL].

Si ce champ n’est pas renseigné, la valeur de la variable [`trackingServer`](trackingserver.md) est utilisée par défaut.

## s.trackingServerSecure dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.trackingServerSecure` est une chaîne qui contient l’emplacement d’envoi des demandes d’image. Il s’agit presque toujours d’un sous-domaine de votre site. Les pratiques modernes de confidentialité dans les navigateurs rendent généralement les cookies tiers peu fiables. Si cette variable est vide, elle utilise la valeur de la variable `s.trackingServer`.

La valeur de cette variable est presque toujours un domaine propriétaire, tel que `data.example.com`. Pour plus d’informations sur le processus des cookies propriétaires, voir [Cookies propriétaires dans Experience Cloud](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-first-party.html) dans le guide d’utilisation des services principaux.

La personne qui configure initialement la mise en œuvre des cookies propriétaires définit également le domaine et le sous-domaine utilisés. Par exemple :

```js
s.trackingServerSecure = "data.example.com";
```

Les enregistrements CNAME renvoient généralement vers un sous-domaine sur `ssl.d1.sc.omtrdc.net`.
