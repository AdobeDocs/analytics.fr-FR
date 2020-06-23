---
title: linkType
description: Utilisez la variable linkType pour déterminer à quelle dimension de suivi de lien appartient l’accès.
translation-type: ht
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
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur Envoyer la balise.
6. Cochez la case `s.tl()` qui affiche la liste déroulante [!UICONTROL Type de lien].

Vous pouvez définir cette liste déroulante sur [!UICONTROL Lien personnalisé], [!UICONTROL Lien de téléchargement] ou [!UICONTROL Lien de sortie].

## s.linkType dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.linkType` est une chaîne qui accepte l’une des trois valeurs à caractère unique suivantes : `o`, `d` ou `e`. Si une méthode `tl()` est appelée sans type de lien, le lien personnalisé est défini par défaut.

* `o` - Liens personnalisés
* `d` - Liens de téléchargement
* `e` - Liens de sortie

>[!TIP] Cette variable correspond au deuxième paramètre de la méthode `tl()` et n’a généralement pas besoin d’être définie en tant que variable autonome. Cependant, vous pouvez utiliser la variable `linkType` si vous ne souhaitez pas définir de valeurs comme arguments dans la méthode `tl()`.

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
