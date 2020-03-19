---
title: linkName
description: Définissez le nom de l’accès au lien personnalisé.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkName

Utilisez la `linkName` variable pour déterminer la valeur de dimension des liens personnalisés, des liens de téléchargement ou des liens de sortie lors de l’exécution de la [`tl()`](../functions/tl-method.md) méthode suivante.

Si cette variable est vide, AppMeasurement revient à la [`linkURL`](linkurl.md) variable.

## Nom du lien dans Adobe Experience Platform Launch

Vous pouvez définir le champ du nom du lien lors de la configuration d’une règle pour envoyer une balise.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône &quot;+&quot;
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et [!UICONTROL Action Type] sur Envoyer la balise.
6. Cliquez sur le `s.tl()` bouton radio qui affiche le [!UICONTROL Link Name] champ.

## s.linkName dans l’éditeur de code personnalisé AppMeasurement et Lancement

La `s.linkName` variable est une chaîne qui détermine la valeur de dimension pour les liens personnalisés, les liens de téléchargement ou les liens de sortie (selon ce qui [`s.linkType`](linktype.md) est). Il peut contenir jusqu&#39;à 100 octets.

> [!TIP] Cette variable est le troisième paramètre de la `tl()` méthode et n’a généralement pas besoin d’être définie en tant que variable autonome. Cependant, vous pouvez utiliser la `linkName` variable si vous ne souhaitez pas définir de valeurs comme arguments dans la `tl()` méthode.

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
