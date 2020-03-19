---
title: t
description: Permet d’envoyer un appel de suivi des pages vues à Adobe.
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# t

La méthode `t` est un composant principal important d’Adobe Analytics. Elle prend toutes les variables Analytics définies sur la page, les compile dans une demande d’image et envoie ces données aux serveurs de collecte de données Adobe.

Prenons l’exemple du code JavaScript suivant :

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension value";

// Compile the variables on the page into an image request to Adobe
s.t();
```

L’exécution de la méthode `t` prend toutes les variables Analytics définies et formule une URL basée sur ces variables. Certaines variables Analytics déterminent l’URL de l’image, tandis que d’autres déterminent les valeurs des paramètres de chaîne de requête.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe reçoit la demande d’image, puis analyse l’en-tête de la demande, l’URL et les paramètres de chaîne de requête. Les serveurs de collecte de données renvoient ensuite une image transparente de 1x1 pixel, affichée de manière invisible sur votre site.

## Appel de suivi des pages vues dans Adobe Experience Platform Launch

Launch a un emplacement dédié défini un appel de suivi des pages vues.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur Envoyer la balise.
6. Cochez la case `s.t()`.

## s.t() dans AppMeasurement et l’éditeur de code personnalisé de Launch

Appelez la méthode `s.t()` lorsque vous souhaitez envoyer un appel de suivi à Adobe.

```js
s.t();
```

Vous pouvez éventuellement utiliser un objet comme argument pour remplacer des valeurs de variable. Pour plus d’informations, voir [Remplacements de variable](../../js/overrides.md).

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

> [!NOTE] Les versions précédentes d’AppMeasurement utilisaient plusieurs lignes de code pour appeler cette fonction. Le code supplémentaire prenait auparavant en charge les solutions pour différents navigateurs. La normalisation et les bonnes pratiques des navigateurs modernes ne nécessitent plus ce bloc de code. Seul l’appel de méthode `s.t()` est désormais nécessaire.
