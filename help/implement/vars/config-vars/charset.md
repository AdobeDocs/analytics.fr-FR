---
title: charSet
description: La variable charSet détermine le codage utilisé par Adobe pour analyser votre demande d’image.
translation-type: tm+mt
source-git-commit: 70410af433f540764b71bd29a81ff9d8210cb95c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 60%

---


# charSet

La variable charSet est utilisée par Adobe pour convertir les données entrantes au format UTF-8 en vue d’une conservation et d’une création de rapports par Analytics. La plupart des sites n’ont pas besoin de définir cette variable.

Définissez cette variable uniquement si vous voyez des valeurs altérées ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) dans les rapports. Vous pouvez définir cette variable page par page si votre site utilise différents codages sur différentes pages.

## Jeu de caractères dans Adobe Experience Platform Launch

Le jeu de caractères désigne un champ sous l’accordéon [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Général], qui affiche le champ [!UICONTROL Jeu de caractères].

Vous pouvez utiliser un jeu de caractères prédéfini ou un jeu de caractères personnalisé. Evitez de modifier la valeur à `UTF-8` moins que les valeurs ne soient altérées dans les rapports.

## s.charSet dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `charSet` est une chaîne. Si vous avez des valeurs altérées dans Adobe Analytics, définissez cette variable sur la même valeur que la balise `<meta charset="">` HTML de votre site.

```js
s.charSet = "UTF-8";
```
