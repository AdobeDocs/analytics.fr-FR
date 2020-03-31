---
title: trackingServer
description: Permet de déterminer l’emplacement où les demandes d’image sont envoyées.
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# trackingServer

Adobe collecte des données sur votre site en recevant une demande d’image générée par le visiteur. La variable `trackingServer` détermine l’emplacement d’envoi d’une demande d’image. Si cette variable n’est pas correctement définie, votre mise en œuvre peut entraîner une perte de données.

> [!IMPORTANT] Si vous modifiez cette valeur, AppMeasurement recherche les cookies à un autre emplacement. Le nombre de visiteurs uniques peut augmenter temporairement la création de rapports lorsque les cookies de visiteurs sont définis au nouvel emplacement.

## Serveur de suivi dans Adobe Experience Platform Launch

Tracking Server is a field under the [!UICONTROL General] accordion when configuring the Adobe Analytics extension.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Développez l’ [!UICONTROL General] accordéon, ce qui révèle le [!UICONTROL Tracking Server] champ.

Si ce champ n’est pas renseigné, il est défini par défaut sur `[rsid].112.2o7.net`.

## s.trackingServer dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.trackingServer` est une chaîne qui contient l’emplacement d’envoi des données.

> [!TIP] Certaines mises en œuvre renvoient les données vers `2o7.net`. Bien qu’il s’agisse d’un domaine de collecte de données valide, celui-ci n’utilise pas la collecte de données régionale. Les mises en œuvre qui utilisent `2o7.net` affichent des temps de réponse de demande d’image légèrement supérieurs.

## Déterminer la valeur de trackingServer

La valeur de cette variable dépend de l’utilisation de cookies propriétaires ou tiers. Adobe recommande vivement d’utiliser des cookies propriétaires dans votre mise en œuvre.

### Cookies propriétaires

Si vous utilisez une mise en œuvre de cookies propriétaires, il est probable qu’une personne de votre entreprise ait déjà terminé le processus de cookies propriétaires. Pour plus d’informations sur le processus des cookies propriétaires, voir [Cookies propriétaires dans Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) dans le guide d’utilisation des services principaux.

La personne qui configure initialement la mise en œuvre des cookies propriétaires définit également le domaine et le sous-domaine utilisés. Par exemple :

```js
s.trackingServer = "data.example.com";
```

En règle générale, les enregistrements CNAME sont déjà configurés et renvoient vers `sc.omtrdc.net`. Le domaine `2o7.net` est également une destination CNAME valide, principalement utilisée dans les versions précédentes d’Adobe Analytics.

### Cookies tiers

> [!TIP] L’augmentation des pratiques de confidentialité dans les navigateurs modernes rend les cookies tiers moins fiables. Adobe recommande de suivre le processus des cookies propriétaires.

Si vous utilisez une mise en œuvre de cookies tiers, la valeur de `trackingServer` est un sous-domaine de `sc.omtrdc.net`. Par exemple :

```js
s.trackingServer = "example.sc.omtrdc.net";
```

Sélectionnez un sous-domaine unique à votre organisation, qui ne sera probablement pas choisi par une autre organisation qui utilise Adobe Analytics. Assurez-vous que toutes les mises en œuvre de votre entreprise utilisent le même serveur de suivi. Il peut s’avérer utile de conserver ces informations dans un [document de conception de solution](../../prepare/solution-design.md).

> [!NOTE] N’utilisez aucun sous-domaine plus profond que `example.sc.omtrdc.net`. Par exemple, `custom.example.sc.omtrdc.net` il ne s’agit pas d’un serveur de suivi valide.
