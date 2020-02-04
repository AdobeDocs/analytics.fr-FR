---
title: trackingServerSecure
description: Déterminez l’emplacement où les demandes d’image sont envoyées sur les pages HTTPS.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServerSecure

Adobe collecte des données sur votre site en recevant une demande d’image générée par le visiteur. La `trackingServerSecure` variable détermine l’emplacement où une demande d’image est envoyée via HTTPS. Il détermine également l’emplacement où les cookies des visiteurs sont stockés. Si cette variable n’est pas correctement définie, votre implémentation peut entraîner une perte de données.

> [!IMPORTANT] Si vous modifiez cette valeur, AppMeasurement recherche les cookies à un autre emplacement. Le nombre de visiteurs uniques peut augmenter temporairement la création de rapports lorsque les cookies de visiteurs sont définis au nouvel emplacement.

## Serveur de suivi SSL dans Adobe Experience Platform Launch

[!UICONTROL Le serveur] de suivi SSL est un champ sous l’accordéon [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Général] , qui affiche le champ Serveur [!UICONTROL de suivi] SSL.

Si ce champ n’est pas renseigné, la valeur de la `trackingServer` variable est utilisée par défaut.

## s.trackingServerSecure dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.trackingServerSecure` variable est une chaîne qui contient l’emplacement d’envoi des demandes d’image. Il s’agit presque toujours d’un sous-domaine de votre site. Les pratiques modernes de confidentialité dans les navigateurs rendent généralement les cookies tiers peu fiables. Si cette variable est vide, elle utilise la valeur de la `s.trackingServer` variable.

La valeur de cette variable est presque toujours un domaine propriétaire, tel que `data.example.com`. Pour plus d’informations sur le processus des cookies propriétaires, voir Cookies [propriétaires dans Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) dans le guide de l’utilisateur des services principaux.

La personne qui configure initialement l’implémentation des cookies propriétaires définit également le domaine et le sous-domaine utilisés. Par exemple :

```js
s.trackingServerSecure = "data.example.com";
```

Les enregistrements CNAME pointent généralement vers un sous-domaine sur `ssl.d1.sc.omtrdc.net`.
