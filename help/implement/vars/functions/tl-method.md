---
title: tl
description: Envoyez un appel de suivi de lien à Adobe.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# tl

La `tl()` méthode est un composant principal important d’Adobe Analytics. Elle prend toutes les variables Analytics définies sur la page, les compile dans une demande d’image et envoie ces données aux serveurs de collecte de données Adobe. Il fonctionne de la même manière que la [`t()`](t-method.md) méthode, mais cette méthode n’incrémente pas les  de page. Il est utile pour le suivi des liens et d’autres éléments qui ne seraient pas considérés comme un chargement de page complet.

Si [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) ou [`trackExternalLinks`](../config-vars/trackexternallinks.md) sont activés, AppMeasurement appelle automatiquement la `tl()` méthode pour envoyer les données de suivi des liens de téléchargement et de sortie. Si votre organisation préfère avoir plus de contrôle sur les liens à suivre et sur leur comportement, vous pouvez appeler la `tl()` méthode manuellement. Les liens personnalisés ne peuvent être suivis que manuellement.

## Appel de suivi des liens dans Adobe Experience Platform Launch

Le lancement a un emplacement dédié défini un appel de suivi des liens.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
1. Sous [!UICONTROL Actions], cliquez sur l’icône &quot;+&quot;
1. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et [!UICONTROL Action Type] sur Envoyer la balise.
1. Click the `s.tl()` radio button.

Vous ne pouvez pas définir d’arguments facultatifs dans Lancement.

## s.tl(), méthode dans l’éditeur de code personnalisé AppMeasurement et Launch

Appelez la `s.tl()` méthode lorsque vous souhaitez envoyer un appel de suivi à Adobe.

```js
s.tl();
```

Cette méthode accepte éventuellement plusieurs arguments :

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Objet Link

L’argument de l’objet link détermine si le navigateur attend jusqu’à 500 ms avant de quitter la page. Si une demande d’image est envoyée avant 500 ms, la page accède immédiatement au lien sur lequel l’utilisateur a cliqué.

> [!NOTE] AppMeasurement active automatiquement la [`useBeacon`](../config-vars/usebeacon.md) variable pour les liens de sortie, ce qui rend cet argument inutile dans les navigateurs modernes. Cet argument a été utilisé plus couramment dans les versions précédentes d’AppMeasurement.

* `this` : attendre jusqu’à 500 ms afin de laisser à AppMeasurement le temps d’envoyer une demande d’image. Valeur par défaut.
* `true` : ne pas attendre. 

```JavaScript
// Include a 500ms delay
s.tl(this);

// Do not include a 500ms delay
s.tl(true);
```

### Type de lien

L&#39;argument de type de lien est une chaîne d&#39;une seule lettre qui détermine le type d&#39;appel de suivi de lien. C’est la même chose que de définir la [`linkType`](../config-vars/linktype.md) variable.

```js
// Send a custom link
s.tl(true,"o");

// Send a download link
s.tl(true,"d");

// Send an exit link
s.tl(true,"e");
```

### Nom du lien

L’argument du nom du lien est une chaîne qui détermine la valeur de la dimension de suivi des liens. C’est la même chose que de définir la [`linkName`](../config-vars/linkname.md) variable.

```js
s.tl(true,"d","Example download link");
```

### Remplacements de variables

Permet de modifier les valeurs de variable pour un appel unique. Pour plus d’informations, voir Remplacements [de](../../js/overrides.md) variable.

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## Exemples et cas d’utilisation

Envoyez un appel de suivi de lien de base directement dans un lien HTML :

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

Utilisez JavaScript pour effectuer un appel de suivi de lien de base à l’aide d’arguments de méthode :

```JavaScript
s.tl(true,"o","Example link");
```

Utilisez JavaScript pour effectuer le même appel de suivi des liens de base à l’aide de variables distinctes :

```js
s.linkType = "o";
s.linkName = "Example link";
s.tl();
```

### Effectuer des appels de suivi de lien dans une fonction personnalisée

Vous pouvez regrouper le code de suivi des liens dans une fonction JavaScript autonome définie sur la page ou dans un fichier JavaScript lié. Vous pouvez alors effectuer des appels dans la fonction onClick de chaque lien. Définissez les éléments suivants dans un fichier JavaScript :

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

Vous pouvez ensuite appeler la fonction chaque fois que vous souhaitez effectuer le suivi d’un lien donné :

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

### Evitez d’effectuer le suivi des liens 

Si `trackDownloadLinks` ou `trackExternalLinks` sont activés, AppMeasurement effectue automatiquement un appel de suivi des liens si le correct  correspond. Si vous appelez également manuellement `s.tl()` pour ces clics sur les liens, vous pouvez envoyer des données  à Adobe. Les données  gonflent le nombre de rapports et les rendent moins précis.

Par exemple, la fonction suivante envoie deux appels de suivi de liens pour le même clic de lien (liens de téléchargement manuels et automatiques) :

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

Vous pouvez aider à empêcher les appels de suivi des liens  en utilisant la fonction modifiée suivante. Il vérifie tout d&#39;abord s&#39;il existe un objet de lien et envoie un appel de suivi manuel des liens uniquement si l&#39;objet de lien est une chaîne vide.

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
