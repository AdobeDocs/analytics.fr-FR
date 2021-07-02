---
title: trackingServer
description: Permet de déterminer l’emplacement où les demandes d’image sont envoyées.
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '396'
ht-degree: 100%

---

# trackingServer

Adobe collecte des données sur votre site en recevant une demande d’image générée par le visiteur. La variable `trackingServer` détermine l’emplacement d’envoi d’une demande d’image. Si cette variable n’est pas correctement définie, votre mise en œuvre peut entraîner une perte de données.

>[!IMPORTANT]
>
>Si vous modifiez cette valeur, AppMeasurement recherche les cookies à un autre emplacement. Le nombre de visiteurs uniques peut augmenter temporairement la création de rapports lorsque les cookies de visiteurs sont définis au nouvel emplacement.

## Serveur de suivi dans Adobe Experience Platform Launch

Le serveur de suivi est un champ sous l’accordéon [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Général], qui affiche le champ [!UICONTROL Serveur de suivi].

Si ce champ n’est pas renseigné, il est défini par défaut sur `[rsid].data.adobedc.net`.

## s.trackingServer dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.trackingServer` est une chaîne qui contient l’emplacement d’envoi des données.

## Déterminer la valeur de trackingServer

La valeur de cette variable dépend de l’utilisation de cookies propriétaires ou tiers. Adobe recommande vivement d’utiliser des cookies propriétaires dans votre mise en œuvre.

### Cookies propriétaires

Si vous utilisez une mise en œuvre de cookies propriétaires, il est probable qu’une personne de votre entreprise ait déjà terminé le processus de cookies propriétaires. Pour plus d’informations sur le processus des cookies propriétaires, voir [Cookies propriétaires dans Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=fr) dans le guide d’utilisation des services principaux.

La personne qui configure initialement la mise en œuvre des cookies propriétaires définit également le domaine et le sous-domaine utilisés. Par exemple :

```js
s.trackingServer = "data.example.com";
```

### Cookies tiers

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
