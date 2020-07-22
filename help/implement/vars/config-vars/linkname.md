---
title: linkName
description: Permet de définir le nom de l’accès au lien personnalisé.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 80%

---


# linkName

Use the `linkName` variable to determine the dimension item of custom links, download links, or exit links when running the next [`tl()`](../functions/tl-method.md) method.

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

The `s.linkName` variable is a string that determines the dimension item for custom links, download links, or exit links (depending on what [`s.linkType`](linktype.md) is). Celle-ci peut contenir jusqu’à 100 octets.

>[!TIP]
>
>Cette variable correspond au troisième paramètre de la méthode `tl()` et n’a généralement pas besoin d’être définie en tant que variable autonome. Cependant, vous pouvez utiliser la variable `linkName` si vous ne souhaitez pas définir de valeurs comme arguments dans la méthode `tl()`.

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
