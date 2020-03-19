---
title: linkType
description: Utilisez la variable linkType pour déterminer à quelle dimension de suivi de lien appartient l’accès.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkType

Les accès de suivi de liens peuvent remplir l’une des trois dimensions suivantes :

* Liens personnalisés
* Liens de sortie
* Liens de téléchargement

Utilisez la `linkType` variable pour déterminer la dimension à renseigner lors de l’exécution de la [`tl()`](../functions/tl-method.md) fonction suivante.

## Type de lien dans Adobe Experience Platform Launch

Définissez le type de lien lors de la configuration d’une règle pour envoyer une balise.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône &quot;+&quot;
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et [!UICONTROL Action Type] sur Envoyer la balise.
6. Cliquez sur le `s.tl()` bouton radio qui affiche la [!UICONTROL Link Type] liste déroulante.

Vous pouvez définir cette liste déroulante sur [!UICONTROL Custom Link], [!UICONTROL Download Link]ou [!UICONTROL Exit Link].

## s.linkType dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.linkType` variable est une chaîne qui accepte l’une des trois valeurs à caractère unique suivantes : `o`, `d`ou `e`. Si une `tl()` méthode est appelée sans type de lien, le lien personnalisé est défini par défaut.

* `o` - Liens personnalisés
* `d` - Liens de téléchargement
* `e` - Liens de sortie

> [!TIP] Cette variable est le deuxième paramètre de la `tl()` méthode et n’a généralement pas besoin d’être définie en tant que variable autonome. Cependant, vous pouvez utiliser la `linkType` variable si vous ne souhaitez pas définir de valeurs comme arguments dans la `tl()` méthode.

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
