---
title: visitorID
description: Permet d’utiliser un identifiant visiteur personnalisé.
translation-type: ht
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorID

Adobe utilise plusieurs méthodes différentes pour identifier les visiteurs de votre site. La variable `visitorID` remplace toutes les autres méthodes d’identification des visiteurs.

> [!IMPORTANT] Adobe conseille d’utiliser cette variable. Utilisez plutôt [Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html).

## Identifiant visiteur dans Adobe Experience Platform Launch

[!UICONTROL L’identifiant visiteur] est un champ sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies], ce qui permet d’afficher le champ [!UICONTROL Identifiant visiteur].

Affectez ce champ à l’élément de données contenant votre identifiant visiteur personnalisé. Ne définissez pas ce champ sur une valeur statique.

## s.visitorID dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.visitorID` est une chaîne qui contient un identifiant unique personnalisé pour le visiteur. Les valeurs valides comprennent des caractères alphanumériques jusqu’à 100 octets. Évitez d’utiliser des tirets, des espaces, des traits de soulignement ou des symboles dans cette variable.

> [!WARNING] Si vous définissez la variable `visitorID` à mi-chemin au cours d’une visite, les données génèrent deux visiteurs uniques distincts.

```js
s.visitorID = "abc123";
```
