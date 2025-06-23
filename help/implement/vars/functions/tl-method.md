---
title: tl
description: Permet d’envoyer un appel de suivi de lien à Adobe.
feature: Appmeasurement Implementation
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 62%

---

# tl

La méthode `tl()` est un composant principal important d’Adobe Analytics. Elle prend toutes les variables Analytics définies sur la page, les compile dans une demande d’image et envoie ces données aux serveurs de collecte de données Adobe. Elle fonctionne de la même manière que la méthode [`t()`](t-method.md), mais cette méthode n’incrémente pas les pages vues. Elle est utile pour le suivi des liens et d’autres éléments qui ne seraient pas considérés comme un chargement de page complet.

Si [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) ou [`trackExternalLinks`](../config-vars/trackexternallinks.md) sont activés, AppMeasurement appelle automatiquement la méthode `tl()` pour envoyer les données de suivi des liens de téléchargement et de sortie. Si votre organisation préfère avoir plus de contrôle sur les liens à suivre et sur leur comportement, vous pouvez appeler la méthode `tl()` manuellement. Les liens personnalisés ne peuvent être suivis que manuellement.

## Suivi des liens à l’aide de Web SDK

Le SDK Web ne fait pas de distinction entre les appels de page vue et les appels de suivi des liens ; tous deux utilisent la commande `sendEvent`.

Si vous utilisez un objet XDM et souhaitez qu’Adobe Analytics comptabilise un événement donné comme un appel de suivi des liens, assurez-vous que vos données XDM incluent :

* Nom du lien : mappé à `xdm.web.webInteraction.name`.
* URL du lien : mappé à `xdm.web.webInteraction.URL`.
* Type de lien : mappé à `xdm.web.webInteraction.type`. Les valeurs valides sont les suivantes : `other` (Liens personnalisés), `download` (Liens de téléchargement) et `exit` (Liens de sortie).

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

Si vous utilisez un objet de données et souhaitez qu’Adobe Analytics comptabilise un événement donné comme un appel de suivi des liens, assurez-vous que votre objet de données inclut :

* Nom du lien : mappé à `data.__adobe.analytics.linkName`.
* URL du lien : mappé à `data.__adobe.analytics.linkURL`.
* Type de lien : mappé à `data.__adobe.analytics.linkType`. Les valeurs valides sont les suivantes : `o` (Liens personnalisés), `d` (Liens de téléchargement) et `e` (Liens de sortie).

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
1. Sous [!UICONTROL Actions], cliquez sur l’action souhaitée ou cliquez sur l’icône **’+’** pour ajouter une action.
1. Définissez la liste déroulante [!UICONTROL Extension] sur **[!UICONTROL Adobe Analytics]**, et le [!UICONTROL Type d’action] sur **[!UICONTROL Envoyer la balise]**.
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

Vous pouvez consolider le code de suivi des liens en une fonction JavaScript autonome. Des appels peuvent alors être effectués dans la fonction `onClick` de chaque lien. Définissez les éléments suivants dans un fichier JavaScript :

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

>[!NOTE]
>L’appel indirect de la méthode `tl()` peut rendre les rapports de recouvrement Activity Map moins pratiques. Vous devez cliquer sur chaque lien pour enregistrer la fonction avec l’élément de lien. Toutefois, les dimensions Activity Map dans Workspace sont suivies de la même manière.

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

### Utilisation de la méthode `tl()` avec Activity Map

Vous pouvez utiliser la méthode `tl()` pour effectuer le suivi des éléments personnalisés et configurer le rendu de recouvrement pour le contenu dynamique. Le paramètre `linkName` est également utilisé pour définir la dimension [Lien Activity Map](/help/components/dimensions/activity-map-link.md).

Lorsque la méthode `tl()` est appelée directement à partir de l’événement on-click de l’élément HTML, Activity Map peut afficher un recouvrement pour cet élément lors du chargement de la page web. Par exemple :

```html
<a href="index.html" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

Lorsque la méthode `tl()` n’est pas appelée directement à partir de l’événement on-click de l’élément HTML, Activity Map ne peut afficher un recouvrement qu’une fois que l’utilisateur a cliqué sur cet élément. Par exemple :

```html
<a href="index.html" onclick="someFn(event);">Example link text</a>
<script>
  function someFn (event) {
    s.tl(event.srcElement,'o','Example custom link');
  }
</script>
```
