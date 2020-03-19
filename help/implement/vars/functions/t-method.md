---
title: t
description: Envoyez un appel de suivi de de page à Adobe.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# t()

La `t()` méthode est un composant principal important d’Adobe Analytics. Elle prend toutes les variables Analytics définies sur la page, les compile dans une demande d’image et envoie ces données aux serveurs de collecte de données Adobe.

Prenons l’exemple du code JavaScript suivant :

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension value";

// Compile the variables on the page into an image request to Adobe
s.t();
```

L’exécution de la `t()` méthode prend toutes les variables Analytics définies et formule une URL basée sur ces variables. Certaines variables Analytics déterminent l’URL de l’image, tandis que d’autres déterminent les valeurs des paramètres de chaîne de.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe reçoit la demande d’image, puis analyse l’en-tête de la demande, l’URL et les paramètres de chaîne de. Les serveurs de collecte de données renvoient ensuite une image transparente de 1x1 pixel, affichée de manière invisible sur votre site.

## Appel de suivi de  de page dans Adobe Experience Platform Launch

Le lancement a un emplacement dédié défini un appel de suivi  page.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur l’icône &quot;+&quot;
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et [!UICONTROL Action Type] sur Envoyer la balise.
6. Click the `s.t()` radio button.

## s.t() dans l’éditeur de code personnalisé AppMeasurement et Launch

Appelez la `s.t()` méthode lorsque vous souhaitez envoyer un appel de suivi à Adobe.

```js
s.t();
```

Vous pouvez éventuellement utiliser un objet comme argument pour remplacer des valeurs de variable. Pour plus d’informations, voir Remplacements [de](../../js/overrides.md) variable.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

> [!NOTE] Les versions précédentes d’AppMeasurement utilisaient plusieurs lignes de code pour appeler cette fonction. Le code supplémentaire a historiquement pris en charge les solutions pour les différents navigateurs. La normalisation et les bonnes pratiques des navigateurs modernes ne nécessitent plus ce bloc de code. Seul l’appel de méthode `s.t()` est nécessaire maintenant.
