---
title: cookieLifetime
description: Permet de remplacer l’expiration des cookies créés par AppMeasurement.
translation-type: ht
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# cookieLifetime

Les cookies définis par AppMeasurement ont généralement une expiration de 2 ans. Utilisez la variable `cookieLifetime` pour remplacer la date d’expiration des cookies définis par AppMeasurement.

> [!NOTE] Cette variable a un impact sur le nombre et l’attribution des visiteurs uniques. Soyez prudent lorsque vous définissez cette variable.

## Durée de vie des cookies dans Adobe Experience Platform Launch

La durée de vie des cookies est une liste déroulante sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies], qui affiche la liste déroulante [!UICONTROL Durée de vie du cookie].

Cette liste déroulante contient les valeurs suivantes :

* **Valeur par défaut** : le cookie expire au bout de 2 ans.
* **Aucun** : AppMeasurement ne définit pas les cookies.
* **Session** : le cookie expire à la fin de la session du visiteur.
* **Secondes** : le cookie expire après l’expiration du nombre de secondes spécifié. Par exemple, si vous définissez cette liste déroulante sur [!UICONTROL Secondes] et placez `86400` dans le champ personnalisé, les cookies expirent exactement après 24 heures.

## s.cookieLifetime dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.cookieLifetime` est une chaîne qui détermine la date d’expiration des cookies définis par AppMeasurement.

* Si celle-ci est définie sur `SESSION`, les cookies définis par AppMeasurement expirent une fois la session du navigateur terminée.
* Si celle-ci est définie sur `NONE`, AppMeasurement ne tente pas de définir des cookies.
* Si celle-ci est définie sur une chaîne entière, les cookies définis par AppMeasurement expirent après l’expiration du nombre de secondes spécifié.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";

