---
title: sa
description: Permet de modifier la suite de rapports à tout moment de votre mise en œuvre.
feature: Appmeasurement Implementation
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 42%

---

# sa

La méthode `sa()` vous permet de modifier dynamiquement une suite de rapports à tout moment de la page. Si vous souhaitez envoyer des données à différentes suites de rapports sans rechargement de page, vous pouvez utiliser cette méthode.

## Gestion des suites de rapports à l’aide de Web SDK

Le SDK web envoie les données à un flux de données spécifique qui les transfère vers la ou les suites de rapports Analytics souhaitées. Un seul flux de données peut transférer des données vers plusieurs suites de rapports. Cette section s’applique à la fois à l’extension Web SDK et à l’implémentation manuelle de Web SDK.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Flux de données]** sur la gauche.
1. Cliquez sur le flux de données de votre choix ou cliquez sur **[!UICONTROL Nouveau flux de données]**.
1. Cliquez sur **[!UICONTROL Ajouter un service]**, puis sélectionnez **[!UICONTROL Adobe Analytics]**.
1. Saisissez l’identifiant de suite de rapports souhaité. Si vous souhaitez envoyer les mêmes données à plusieurs suites de rapports, cliquez sur **[!UICONTROL Ajouter une suite de rapports]**.
1. Une fois toutes les suites de rapports saisies, cliquez sur **[!UICONTROL Enregistrer]**.

## Définir le flux de données souhaité à l’aide de l’extension Web SDK

L’extension Web SDK fournit une liste déroulante Flux de données pour chaque environnement. Vous pouvez également saisir manuellement l’identifiant du flux de données.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous [!UICONTROL Adobe Experience Platform Web SDK].
1. Sous [!UICONTROL Flux de données], choisissez le flux de données de votre choix dans la liste déroulante pour chaque environnement.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Définir le flux de données souhaité en implémentant manuellement le SDK Web

Définissez la variable de configuration `datastreamId` sur l’identifiant du flux de données. L’identifiant du flux de données se trouve à droite lors de l’affichage d’un flux de données dans la collecte de données Adobe Experience Platform.

```js
alloy("configure", {
  datastreamId: "example-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Voir [Configurer le SDK Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) dans la documentation de Web SDK pour plus d’informations.

## Modification d’une suite de rapports à l’aide de l’extension Adobe Analytics

Il n’existe pas de méthode souple pour modifier la suite de rapports dans l’interface. Vous pouvez définir la suite de rapports sous l’accordéon [!UICONTROL Gestion des bibliothèques] lors de la configuration de l’extension Adobe Analytics. Toutefois, vous ne pouvez pas modifier ni mettre à jour la suite de rapports à l’aide de règles. Si vous souhaitez mettre à jour les valeurs d’une suite de rapports après leur définition, utilisez l’éditeur de code personnalisé suivant la syntaxe AppMeasurement.

## s.sa() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Appelez la méthode `s.sa()` pour modifier la suite de rapports de destination. Son seul argument est une chaîne contenant un identifiant de suite de rapports ou plusieurs identifiants de suite de rapports délimités par une virgule. L’argument d’identifiant de suite de rapports est obligatoire. N’utilisez pas d’espaces dans l’argument de chaîne.

```js
s.sa("examplersid");
```

Par exemple, vous pouvez modifier la suite de rapports si l’utilisateur effectue une action spécifique sur votre site.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
