---
title: trackingServer
description: Permet de déterminer l’emplacement où les demandes d’image sont envoyées.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 52%

---

# trackingServer

Adobe collecte des données sur votre site en recevant une demande d’image générée par le visiteur. La variable `trackingServer` détermine l’emplacement d’envoi d’une demande d’image. Si cette variable n’est pas correctement définie, votre mise en œuvre peut entraîner une perte de données.

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

## Serveur de suivi utilisant l’extension Adobe Analytics

Le serveur de suivi est un champ sous l’accordéon [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Général], qui affiche le champ [!UICONTROL Serveur de suivi].

Si ce champ n’est pas renseigné, il est défini par défaut sur `[rsid].data.adobedc.net`.

## s.trackingServer dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.trackingServer` est une chaîne qui contient l’emplacement d’envoi des données.

## Considérations relatives à la détermination de la valeur de `trackingServer`

Vous pouvez choisir d’utiliser les domaines du serveur de suivi Adobe (par exemple, `adobedc.net`) ou vous pouvez suivre un processus spécial pour configurer un serveur de suivi correspondant à votre domaine de sites (par exemple, `data.mydomain.com`), également appelé implémentation CNAME. Disposer d’un serveur de suivi correspondant à votre domaine de site peut présenter certains avantages en fonction d’autres aspects de votre implémentation. Lorsque le serveur de suivi ne correspond pas au domaine de la page en cours, les cookies définis par AppMeasurement doivent être définis comme tiers. Si le navigateur ne prend pas en charge les cookies tiers, cette incohérence peut interférer avec certaines fonctionnalités d’Analytics :

- Définition des identifiants : si vous utilisez Experience Cloud Identity Service, le serveur de suivi n’a aucune incidence sur la définition des cookies. Cependant, si vous utilisez des identifiants Analytics hérités (ou le cookie `s_vi`) et que le serveur de collecte ne correspond pas au domaine actuel, les cookies doivent être définis comme tiers. Dans ce cas, si les cookies tiers sont bloqués par le navigateur, Analytics définit un identifiant de secours propriétaire (`s_fid`) au lieu du cookie `s_vi` standard.
- Le suivi des liens ne fonctionne pas pour les liens internes.
- Activity Map ne fonctionne pas pour les liens internes.
- Vérification des cookies.

### Cookies propriétaires

Si vous utilisez une mise en œuvre de cookies propriétaires, il est probable qu’une personne de votre entreprise ait déjà terminé le processus de cookies propriétaires. Pour plus d’informations sur le processus des cookies propriétaires, voir [Cookies propriétaires dans Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=fr) dans le guide d’utilisation des services principaux.

La personne qui configure initialement la mise en œuvre des cookies propriétaires définit également le domaine et le sous-domaine utilisés. Par exemple :

```js
s.trackingServer = "data.example.com";
```

### Serveur de suivi tiers

>[!TIP]
>
>L’augmentation des pratiques de confidentialité dans les navigateurs modernes rend les cookies tiers moins fiables. Adobe recommande de suivre le processus des cookies propriétaires.

Si vous utilisez une mise en œuvre de cookies tiers, la valeur de `trackingServer` est un sous-domaine de `data.adobedc.net`. Par exemple :

```js
s.trackingServer = "example.data.adobedc.net";
```

Sélectionnez un sous-domaine unique à votre organisation, qui ne sera probablement pas choisi par une autre organisation qui utilise Adobe Analytics.  Il est recommandé d’utiliser l’espace de noms du visiteur attribué à votre organisation.  Assurez-vous que toutes les mises en œuvre de votre entreprise utilisent le même serveur de suivi. Il peut s’avérer utile de conserver ces informations dans un [document de conception de solution](../../prepare/solution-design.md).

Votre organisation utilise peut-être déjà un serveur de suivi tiers dans les domaines `sc.omtrdc.net` ou `2o7.net`.  Ceux-ci étaient principalement utilisés dans les versions précédentes d’Adobe Analytics et sont toujours valides.

>[!NOTE]
>
>N’utilisez aucun sous-domaine plus profond que `example.data.adobedc.net`. Par exemple, `custom.example.data.adobedc.net` n’est pas un serveur de suivi valide.
