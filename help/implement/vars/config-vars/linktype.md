---
title: linkType
description: Utilisez la variable linkType pour déterminer à quelle dimension de suivi de lien appartient l’accès.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkType

Les accès de suivi de liens peuvent remplir l’une des trois dimensions suivantes :

* Liens personnalisés
* Liens de sortie
* Liens de téléchargement

Utilisez la `linkType` variable pour déterminer la dimension à renseigner lors de l’exécution de la `tl()` fonction suivante.

## Type de lien dans Adobe Experience Platform Launch

Définissez le type de lien lors de la configuration d’une règle pour envoyer une balise.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône &quot;+&quot;
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur Envoyer la balise.
6. Cliquez sur le `s.tl()` bouton radio qui affiche la liste déroulante Type [!UICONTROL de] lien.

Vous pouvez définir cette liste déroulante sur Lien personnalisé, Lien [!UICONTROL de]téléchargement ou Lien [!UICONTROL de]sortie.

## s.linkType dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.linkType` variable est une chaîne qui accepte l’une des trois valeurs à caractère unique suivantes : `o`, `d`ou `e`. Si une `tl()` fonction est appelée sans type de lien, le lien personnalisé est défini par défaut.

* `o` - Liens personnalisés
* `d` - Liens de téléchargement
* `e` - Liens de sortie

> [!TIP] Cette variable est le deuxième paramètre de la `tl()` fonction et n’a généralement pas besoin d’être définie en tant que variable autonome. Cependant, vous pouvez utiliser la `linkType` variable si vous ne souhaitez pas définir de valeurs comme arguments dans la `tl()` fonction.

```js
s.linkType = "e";
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
