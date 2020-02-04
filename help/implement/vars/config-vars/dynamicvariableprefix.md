---
title: dynamicVariablePrefix
description: Permet de personnaliser la chaîne qui identifie les variables dynamiques.
translation-type: tm+mt
source-git-commit: 03a4c0d5e080219a7fd96dff33ce122669351ac3

---


# dynamicVariablePrefix

Les variables dynamiques sont un concept abrégé qui vous permet de copier des valeurs d’une variable vers une autre. Elles s’avèrent utiles pour les longues valeurs de variable, car elles permettent de raccourcir la longueur de l’URL d’une demande d’image. Voir Variables [](../page-vars/dynamic-variables.md) dynamiques pour en savoir plus sur ce concept.

Par défaut, les variables dynamiques utilisent le préfixe `D=`. La `dynamicVariablePrefix` variable vous permet de personnaliser la chaîne qui identifie les variables dynamiques. Il est sensible à la casse.

## Préfixe de variable dynamique dans Adobe Experience Platform Launch

Le préfixe de variable dynamique est un champ situé sous l’accordéon Variables  globales lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon Variables  globales, qui affiche le champ Préfixe [!UICONTROL de variable] dynamique.

Ce champ contient `D=` par défaut. Vous pouvez modifier la valeur si vous souhaitez utiliser un préfixe de variable dynamique différent. Vous pouvez utiliser n’importe quelle valeur, à condition qu’elle corresponde au codage des caractères sur votre site.

## s.dynamicVariablePrefix dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.dynamicVariablePrefix` variable est une chaîne pouvant contenir n’importe quelle séquence de caractères. Si cette variable n’est pas définie, AppMeasurement utilise la chaîne `D=` par défaut.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
