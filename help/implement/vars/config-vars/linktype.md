---
title: linkType
description: Utilisez la variable linkType pour déterminer à quelle dimension de suivi de lien appartient l’accès.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkType

Les accès de suivi de liens peuvent remplir l’une des trois dimensions suivantes :

* Liens personnalisés
* Liens de sortie
* Liens de téléchargement

Utilisez la variable `linkType` pour déterminer la dimension à renseigner lors de l’exécution de la fonction suivante [`tl()`](../functions/tl-method.md).

## Type de lien dans Adobe Experience Platform Launch

Définissez le type de lien lors de la configuration d’une règle pour envoyer une balise.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the &#39;+&#39; icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Type] dropdown.

Vous pouvez définir cette liste déroulante sur [!UICONTROL Custom Link], [!UICONTROL Download Link]ou [!UICONTROL Exit Link].

## s.linkType dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.linkType` est une chaîne qui accepte l’une des trois valeurs à caractère unique suivantes : `o`, `d` ou `e`. If a `tl()` method is called without a link type, it defaults to Custom link.

* `o` - Liens personnalisés
* `d` - Liens de téléchargement
* `e` - Liens de sortie

>[!TIP] Cette variable est le deuxième paramètre de la `tl()` méthode et n’a généralement pas besoin d’être définie en tant que variable autonome. However, you can use the `linkType` variable if you do not want to set values as arguments in the `tl()` method.

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
