---
title: tl
description: Permet d’envoyer un appel de suivi de lien à Adobe.
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 76%

---

# tl

La méthode `tl()` est un composant principal important d’Adobe Analytics. Elle prend toutes les variables Analytics définies sur la page, les compile dans une demande d’image et envoie ces données aux serveurs de collecte de données Adobe. Elle fonctionne de la même manière que la méthode [`t()`](t-method.md), mais cette méthode n’incrémente pas les pages vues. Elle est utile pour le suivi des liens et d’autres éléments qui ne seraient pas considérés comme un chargement de page complet.

Si [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) ou [`trackExternalLinks`](../config-vars/trackexternallinks.md) sont activés, AppMeasurement appelle automatiquement la méthode `tl()` pour envoyer les données de suivi des liens de téléchargement et de sortie. Si votre organisation préfère avoir plus de contrôle sur les liens à suivre et sur leur comportement, vous pouvez appeler la méthode `tl()` manuellement. Les liens personnalisés ne peuvent être suivis que manuellement.

## Suivi des liens à l’aide du SDK Web

Le SDK Web ne fait pas la distinction entre les appels de pages vues et les appels de suivi de liens ; tous deux utilisent la variable `sendEvent` .

Si vous utilisez un objet XDM et souhaitez qu’Adobe Analytics comptabilise un événement donné comme un appel de suivi des liens, assurez-vous que vos données XDM comprennent :

* Nom du lien : mappé sur `xdm.web.webInteraction.name`.
* URL du lien : mappée sur `xdm.web.webInteraction.URL`.
* Type de lien : mappé sur `xdm.web.webInteraction.type`. Les valeurs valides sont les suivantes : `other` (Liens personnalisés), `download` (Liens de téléchargement) et `exit` (Liens de sortie).

```js
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webInteraction": {
        "name": "My Custom Link",
        "URL": "https://example.com",
        "type": "other"
      }
    }
  }
});
```

Si vous utilisez un objet de données et souhaitez qu’Adobe Analytics comptabilise un événement donné comme un appel de suivi des liens, assurez-vous que votre objet de données comprend :

* Nom du lien : mappé sur `data.__adobe.analytics.linkName`.
* URL du lien : mappée sur `data.__adobe.analytics.linkURL`.
* Type de lien : mappé sur `data.__adobe.analytics.linkType`. Les valeurs valides sont les suivantes : `o` (Liens personnalisés), `d` (Liens de téléchargement) et `e` (Liens de sortie).

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "linkName": "My custom link",
        "linkURL": "https://example.com",
        "linkType": "o"
      }
    }
  }
});
```

## Suivi des liens à l’aide de l’extension Adobe Analytics

L’extension Adobe Analytics dispose d’un emplacement dédié pour définir un appel de suivi des liens.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
1. Sous [!UICONTROL Actions], cliquez sur l’action souhaitée ou cliquez sur le bouton **&#39;+&#39;** pour ajouter une action.
1. Définissez la variable [!UICONTROL Extension] Liste déroulante à **[!UICONTROL Adobe Analytics]**, et la variable [!UICONTROL Type d’action] to **[!UICONTROL Envoyer la balise]**.
1. Cochez la case `s.tl()`.

Vous ne pouvez pas définir d’arguments facultatifs dans l’extension Analytics.

## s.tl() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Appelez la méthode `s.tl()` lorsque vous souhaitez envoyer un appel de suivi à Adobe.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Objet du lien (obligatoire)

L’argument d’objet du lien détermine si le navigateur attend jusqu’à 500 ms avant de quitter la page. Si une demande d’image est envoyée avant 500 ms, la page accède immédiatement au lien sur lequel l’utilisateur a cliqué.

>[!NOTE]
>
>AppMeasurement active automatiquement la variable [`useBeacon`](../config-vars/usebeacon.md) pour les liens de sortie, ce qui rend cet argument inutile dans les navigateurs modernes. Cet argument a été utilisé plus couramment dans les versions précédentes d’AppMeasurement.

* `this` : attendre jusqu’à 500 ms afin de laisser à AppMeasurement le temps d’envoyer une demande d’image. Valeur par défaut.
* `true` : ne pas attendre.

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### Type de lien (obligatoire)

L’argument de type de lien est une chaîne d’un seul caractère qui détermine le type d’appel de suivi des liens. Il existe trois valeurs valides.

* `o` : le lien est un [lien personnalisé](/help/components/dimensions/custom-link.md).
* `d` : le lien est un [lien de téléchargement](/help/components/dimensions/download-link.md).
* `e` : le lien est un [lien de sortie](/help/components/dimensions/exit-link.md).

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### Nom du lien (recommandé)

L’argument du nom du lien est une chaîne qui détermine l’élément de dimension de suivi des liens. Cette chaîne contient l’élément de dimension lorsque vous utilisez les dimensions [Lien personnalisé](/help/components/dimensions/custom-link.md), [Lien de téléchargement](/help/components/dimensions/download-link.md) ou [Lien de sortie](/help/components/dimensions/exit-link.md) dans le compte rendu des performances. Si cet argument n’est pas défini, la variable [linkURL](../config-vars/linkurl.md) est utilisée.

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### Remplacements de variables (facultatif)

Permet de modifier les valeurs de variable pour un appel unique. Pour plus d’informations, voir [Remplacements de variable](../../js/overrides.md).

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## Exemples et cas d’utilisation

Envoyez un appel de suivi de lien de base directement dans un lien HTML :

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

Utilisez JavaScript pour effectuer un appel de suivi de lien de base à l’aide d’arguments de méthode :

```JavaScript
s.tl(true,"o","Example link");
```

### Effectuez des appels de suivi de lien dans une fonction personnalisée

Vous pouvez regrouper le code de suivi des liens dans une fonction JavaScript autonome définie sur la page ou dans un fichier JavaScript lié. Vous pouvez alors effectuer des appels dans la fonction onClick de chaque lien. Définissez les éléments suivants dans un fichier JavaScript :

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

Vous pouvez ensuite appeler la fonction lorsque vous souhaitez effectuer le suivi d’un lien donné :

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

### Éviter le suivi des liens en double

Si `trackDownloadLinks` ou `trackExternalLinks` sont activés, AppMeasurement effectue automatiquement un appel de suivi des liens si les filtres corrects correspondent. Si vous appelez également manuellement `s.tl()` pour ces clics sur les liens, vous pouvez envoyer des données en double à Adobe. Les données en double gonflent le nombre de rapports et les rendent moins précis.

Par exemple, la fonction suivante envoie deux appels de suivi de liens pour le même clic de lien (liens de téléchargement manuels et automatiques) :

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

Vous pouvez contribuer à empêcher les appels de suivi de liens en double en utilisant la fonction modifiée suivante. Il vérifie tout d’abord s’il existe un objet de lien et envoie un appel de suivi manuel des liens uniquement si l’objet de lien est une chaîne vide.

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
