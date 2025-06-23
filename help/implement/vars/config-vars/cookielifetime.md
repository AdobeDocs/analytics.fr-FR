---
title: cookieLifetime
description: Permet de remplacer l’expiration des cookies créés par AppMeasurement.
feature: Appmeasurement Implementation
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 64%

---

# cookieLifetime

Les cookies définis par AppMeasurement ont généralement une expiration de 2 ans. Utilisez la variable `cookieLifetime` pour remplacer la date d’expiration des cookies définis par AppMeasurement.

>[!NOTE]
>
>Cette variable a un impact sur le nombre et l’attribution des visiteurs uniques. Soyez prudent lorsque vous définissez cette variable.

## Durée de vie des cookies à l’aide de Web SDK

Web SDK n’offre pas encore de personnalisation de la durée de vie des cookies qu’il définit.

## Durée de vie des cookies à l’aide de l’extension Adobe Analytics

La durée de vie des cookies est une liste déroulante sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Cookies] pour afficher la liste déroulante [!UICONTROL Durée de vie des cookies].

Cette liste déroulante contient les valeurs suivantes :

* **Valeur par défaut** : le cookie expire au bout de 2 ans.
* **Aucun** : AppMeasurement ne définit pas les cookies.
* **Session** : le cookie expire à la fin de la session du visiteur.
* **Secondes** : le cookie expire après l’expiration du nombre de secondes spécifié. Par exemple, définir cette liste déroulante sur [!UICONTROL Secondes] et placer des `86400` dans le champ personnalisé force l’expiration des cookies au bout de 24 heures exactement.

## s.cookieLifetime dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.cookieLifetime` est une chaîne qui détermine la date d’expiration des cookies définis par AppMeasurement.

* Si celle-ci est définie sur `SESSION`, les cookies définis par AppMeasurement expirent une fois la session du navigateur terminée.
* Si celle-ci est définie sur `NONE`, AppMeasurement ne tente pas de définir des cookies.
* Si celle-ci est définie sur une chaîne entière, les cookies définis par AppMeasurement expirent après l’expiration du nombre de secondes spécifié.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
