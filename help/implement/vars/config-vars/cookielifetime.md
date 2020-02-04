---
title: cookieLifetime
description: Remplacez l’expiration des cookies créés par AppMeasurement.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# cookieLifetime

Les cookies définis par AppMeasurement ont généralement une expiration de 2 ans. Utilisez la `cookieLifetime` variable pour remplacer la date d’expiration des cookies définis par AppMeasurement.

> [!NOTE] Cette variable a un impact sur le nombre et l’attribution des visiteurs uniques. Soyez prudent lorsque vous définissez cette variable.

## Durée de vie des cookies dans Adobe Experience Platform Launch

La durée de vie des cookies est une liste déroulante sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies] , qui affiche la liste déroulante Durée de vie [!UICONTROL des] cookies.

Cette liste déroulante contient les valeurs suivantes :

* **Valeur par défaut**: Le cookie expire après 2 ans.
* **Aucun**: AppMeasurement ne définit pas les cookies.
* **Session**: Le cookie expire à la fin de la session du visiteur.
* **Secondes**: Le cookie expire après l’expiration du nombre de secondes spécifié. Par exemple, si vous définissez cette liste déroulante sur [!UICONTROL Secondes] et placez `86400` les cookies dans le champ personnalisé, les cookies expirent exactement après 24 heures.

## s.cookieLifetime dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.cookieLifetime` variable est une chaîne qui détermine la date d’expiration des cookies définis par AppMeasurement.

* S’il est défini sur `SESSION`, les cookies définis par AppMeasurement expirent une fois la session du navigateur terminée.
* S’il est défini sur `NONE`, AppMeasurement ne tente pas de définir des cookies.
* S’il est défini sur une chaîne entière, les cookies définis par AppMeasurement expirent après l’expiration du nombre de secondes spécifié.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";

