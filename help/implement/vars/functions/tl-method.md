---
title: tl
description: Permet d’envoyer un appel de suivi de lien à Adobe.
translation-type: tm+mt
source-git-commit: 5bdd07b147d1ea5ef80336a893c02057e7bf5785
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 87%

---


# tl

La méthode `tl()` est un composant principal important d’Adobe Analytics. Elle prend toutes les variables Analytics définies sur la page, les compile dans une demande d’image et envoie ces données aux serveurs de collecte de données Adobe. Elle fonctionne de la même manière que la méthode [`t()`](t-method.md), mais cette méthode n’incrémente pas les pages vues. Elle est utile pour le suivi des liens et d’autres éléments qui ne seraient pas considérés comme un chargement de page complet.

Si [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) ou [`trackExternalLinks`](../config-vars/trackexternallinks.md) sont activés, AppMeasurement appelle automatiquement la méthode `tl()` pour envoyer les données de suivi des liens de téléchargement et de sortie. Si votre organisation préfère avoir plus de contrôle sur les liens à suivre et sur leur comportement, vous pouvez appeler la méthode `tl()` manuellement. Les liens personnalisés ne peuvent être suivis que manuellement.

## Appel de suivi des liens dans Adobe Experience Platform Launch

Launch a un emplacement dédié défini un appel de suivi des liens.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
1. Sous [!UICONTROL Actions], cliquez sur l’icône « + ».
1. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur Envoyer la balise.
1. Cochez la case `s.tl()`.

Vous ne pouvez pas définir d’arguments facultatifs dans Launch.

## s.tl() dans AppMeasurement et l’éditeur de code personnalisé de Launch

Appelez la méthode `s.tl()` lorsque vous souhaitez envoyer un appel de suivi à Adobe.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Objet Link (obligatoire)

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

L&#39;argument type de lien est une chaîne à caractère unique qui détermine le type d&#39;appel de suivi de lien. Il existe trois valeurs valides.

* `o`: Le lien est un lien [ ](/help/components/dimensions/custom-link.md)personnalisé.
* `d`: Il s’agit d’un lien [ de ](/help/components/dimensions/download-link.md)téléchargement.
* `e`: Le lien est un lien [ de ](/help/components/dimensions/exit-link.md)sortie.

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### Nom du lien (recommandé)

L’argument du nom du lien est une chaîne qui détermine l’élément de dimension de suivi des liens. Lorsque vous utilisez les dimensions [Lien personnalisé](/help/components/dimensions/custom-link.md), [Lien de téléchargement](/help/components/dimensions/download-link.md) ou [Lien de sortie](/help/components/dimensions/exit-link.md) dans le rapports, cette chaîne contient l’élément de dimension. Si cet argument n&#39;est pas défini, la variable [linkURL](../config-vars/linkurl.md) est utilisée.

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
