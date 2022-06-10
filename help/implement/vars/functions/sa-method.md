---
title: sa
description: Permet de modifier la suite de rapports à tout moment de votre mise en œuvre.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 38%

---

# sa

La méthode `sa()` vous permet de modifier dynamiquement une suite de rapports à tout moment de la page. Si vous souhaitez envoyer des données à différentes suites de rapports sans rechargement de page, vous pouvez utiliser cette méthode.

## Gestion des suites de rapports à l’aide du SDK Web

Le SDK Web fonctionne en envoyant des données à un flux de données spécifique, qui transfère des données vers les suites de rapports Analytics souhaitées. Un seul flux de données peut transférer des données vers plusieurs suites de rapports. Cette section s’applique à la fois à l’extension SDK Web et à la mise en oeuvre manuelle du SDK Web.

1. Connectez-vous à [Collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Datastreams]** sur la gauche.
1. Cliquez sur le flux de données de votre choix ou cliquez sur **[!UICONTROL Nouvelle structure de données]**.
1. Cliquez sur **[!UICONTROL Ajouter un service]**, puis sélectionnez **[!UICONTROL Adobe Analytics]**.
1. Saisissez l’identifiant de suite de rapports souhaité. Si vous souhaitez envoyer les mêmes données à plusieurs suites de rapports, cliquez sur **[!UICONTROL Ajouter une suite de rapports]**.
1. Une fois toutes les suites de rapports souhaitées saisies, cliquez sur **[!UICONTROL Enregistrer]**.

## Définissez la flux de données souhaitée à l’aide de l’extension SDK Web.

L’extension SDK Web fournit une liste déroulante de flux de données pour chaque environnement. Vous pouvez également saisir manuellement l’identifiant de la banque de données.

1. Connectez-vous à [Collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez au [!UICONTROL Extensions] , puis cliquez sur le bouton **[!UICONTROL Configurer]** sous [!UICONTROL SDK Web Adobe Experience Platform].
1. Sous [!UICONTROL Datastreams], sélectionnez la matrice de données de votre choix dans la liste déroulante pour chaque environnement.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Définissez la flux de données souhaitée en implémentant manuellement le SDK Web.

Définissez la variable `edgeConfigId` à l’identifiant de la banque de données. L’identifiant de la banque de données se trouve à droite lors de l’affichage d’un flux de données dans la collecte de données Adobe Experience Platform.

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

Voir [Configuration du SDK Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) pour plus d’informations, voir la documentation du SDK Web .

## Modification de la suite de rapports à l’aide de l’extension Adobe Analytics

Il n’existe pas de méthode souple pour modifier la suite de rapports dans l’interface. Vous pouvez définir la suite de rapports sous l’accordéon [!UICONTROL Gestion des bibliothèques] lors de la configuration de l’extension Adobe Analytics. Toutefois, vous ne pouvez pas modifier ni mettre à jour la suite de rapports à l’aide de règles. Si vous souhaitez mettre à jour les valeurs d’une suite de rapports après leur définition, utilisez l’éditeur de code personnalisé suivant la syntaxe AppMeasurement.

## s.sa() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Appelez la méthode `s.sa()` pour modifier la suite de rapports de destination. Son seul argument est une chaîne contenant un identifiant de suite de rapports ou plusieurs identifiants de suite de rapports délimités par une virgule. L’argument d’identifiant de suite de rapports est obligatoire. N’utilisez pas d’espaces dans l’argument de chaîne.

```js
s.sa("examplersid");
```

Vous pouvez, par exemple, modifier la suite de rapports si l’utilisateur effectue une action spécifique sur votre site.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
