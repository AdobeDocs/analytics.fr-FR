---
title: charSet
description: La variable charSet détermine le codage utilisé par Adobe pour analyser votre demande d’image.
translation-type: ht
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

La variable charSet est utilisée par Adobe pour convertir les données entrantes au format UTF-8 en vue d’une conservation et d’une création de rapports par Analytics. Si votre site utilise un charSet autre que UTF-8, cette variable permet à vos données d’être correctement codées par Adobe. Cette variable peut être définie page par page si votre site utilise différents codages sur différentes pages.

## Jeu de caractères dans Adobe Experience Platform Launch

Le jeu de caractères désigne un champ sous l’accordéon [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Général], qui affiche le champ [!UICONTROL Jeu de caractères].

Vous pouvez utiliser un jeu de caractères prédéfini ou un jeu de caractères personnalisé. Cette valeur doit correspondre au codage des caractères sur votre site. La plupart des sites utilisent `UTF-8`.

## s.charSet dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `charSet` est une chaîne. Définissez cette variable sur la même valeur que la balise HTML `<meta charset="">` de votre site.

```js
s.charSet = "UTF-8";
```
