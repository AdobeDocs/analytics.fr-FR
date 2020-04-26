---
title: linkName
description: Permet de définir le nom de l’accès au lien personnalisé.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkName

Use the `linkName` variable to determine the dimension value of custom links, download links, or exit links when running the next [`tl()`](../functions/tl-method.md) method.

Si cette variable est vide, AppMeasurement revient à la variable [`linkURL`](linkurl.md).

## Nom du lien dans Adobe Experience Platform Launch

Vous pouvez définir le champ du nom du lien lors de la configuration d’une règle pour envoyer une balise.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur Envoyer la balise.
6. Cochez la case `s.tl()` qui affiche le champ [!UICONTROL Nom du lien].

## s.linkName dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.linkName` est une chaîne qui détermine la valeur de dimension pour les liens personnalisés, les liens de téléchargement ou les liens de sortie (selon ce à quoi [`s.linkType`](linktype.md) correspond). Celle-ci peut contenir jusqu’à 100 octets.

>[!TIP] Cette variable est le troisième paramètre de la `tl()` méthode et n’a généralement pas besoin d’être définie en tant que variable autonome. However, you can use the `linkName` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkName = "Example custom link";
```

## Exemple

Les deux exemples d’appels de suivi de liens suivants sont fonctionnellement identiques. Il s’agit de méthodes différentes pour accomplir le même suivi des liens avec les accès.

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
