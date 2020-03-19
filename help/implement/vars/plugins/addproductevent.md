---
title: addProductEvent
description: Ajoute un personnalisé à la variable products and .
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Module externe Adobe : addProductEvent

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `addProductEvent` module externe ajoute un numérique ou monétaire à la [`products`](../page-vars/products.md) variable. Adobe recommande d’utiliser ce module externe si vous souhaitez ajouter un numérique ou monétaire à la `products` variable sans vous soucier du format de chaîne du produit. Ce module externe n’est pas nécessaire si vous n’utilisez pas de  numérique ou monétaire dans la `products` variable.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe   une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l&#39; [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Catalog] bouton
1. Installation et publication de l’ [!UICONTROL Common Analytics Plugins] extension
1. Si vous ne l’avez pas déjà fait, créez une règle intitulée &quot;Initialiser les modules externes&quot; avec la configuration suivante :
   * Condition : Aucun
   *  : Core - Bibliothèque chargée (Haut de la page)
1. Ajouter une action à la règle ci-dessus avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialize addProductEvent
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du module externe à l’aide de l’éditeur de code personnalisé Lancer

Si vous ne souhaitez pas utiliser l’extension du module externe, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété souhaitée.
1. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous l’extension Adobe Analytics.
1. Développez l’ [!UICONTROL Configure tracking using custom code] accordéon, ce qui révèle le [!UICONTROL Open Editor] bouton.
1. Ouvrez l’éditeur de code personnalisé et collez le code du module externe fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du module externe à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre implémentation permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires apl v3.1 and inList v2.0+ plug-ins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `addProductEvent` méthode utilise les arguments suivants :

* **`en`** (obligatoire, chaîne) : Le à ajouter à la dernière entrée de la `products` variable. Si la `products` variable est vide, une entrée de produit &quot;vide&quot; est créée avec le  (et sa valeur) associé.
* **`ev`** (obligatoire, chaîne) : Valeur affectée au numérique ou monétaire dans l’ `en` argument.  La valeur par défaut est `1` définie lorsqu’elle n’est pas définie.
* **`ap`** (facultatif, booléen) : Si la variable products contient actuellement plusieurs entrées de produit, une valeur de `true` (ou `1`) ajoute le  à toutes les entrées de produit.  La valeur par défaut est `false` définie lorsqu’elle n’est pas définie.

Le `addProductEvent` rapport ne renvoie rien. Au lieu de cela, il ajoute le  et sa valeur à la `products` variable. Le plug-in ajoute également automatiquement le  de à la [`events`](../page-vars/events/events-overview.md) variable, puisqu’il y est également obligatoire.

## Cookies

Le module complémentaire addProductEvent ne crée ni n’utilise de cookies

## Exemples d’appels

### Exemple n° 1

Le code suivant définit la `s.products` variable sur `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`.

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

Le code ci-dessus définit également la `s.events` variable sur `"purchase,event35"`

### Exemple n° 2

Le code suivant définit la `s.products` variable sur `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

Lorsque le troisième argument de l&#39; `addProductEvent` appel est `true` (ou `1`), chaque entrée de produit a le  spécifié dans l&#39;appel ajouté à sa valeur.

### Exemple n° 3

Le code suivant définit la `s.products` variable sur `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

Le code ci-dessus définit également la `s.events` variable sur `"purchase,event2,event33,event34,event35"`

### Exemple n° 4

Le code suivant définit la `s.products` variable sur `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

Le code ci-dessus définit également la `s.events` variable sur `"purchase,event2,event33,event34,event35"`.

> [!NOTE] Le deuxième argument de l’appel peut être un entier **ou** une chaîne représentant un nombre entier.

### Exemple n° 5

Si `s.products` n’est pas déjà défini, le code suivant le définit sur `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

Le code ci-dessus s’ajoute également `"event35"` à la fin de `s.events` ou, si **ce n’est pas déjà fait, le code ci-dessus se définit**`s.events` `s.events` sur `"event35"`

## Historique des versions

### 1.0 (7 octobre 2019)

* Version initiale.
