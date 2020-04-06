---
title: addProductEvent
description: Permet d’ajouter des événements personnalisés aux variables products et events.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : addProductEvent

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `addProductEvent` ajoute un événement numérique ou monétaire à la variable [`products`](../page-vars/products.md). Adobe recommande d’utiliser ce plug-in si vous souhaitez ajouter un événement numérique ou monétaire à la variable `products` sans vous soucier du format de la chaîne de produit. Ce plug-in n’est pas nécessaire si vous n’utilisez pas d’événements numériques ou monétaires dans la variable `products`.

## Installation du plug-in à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Installation et publication de l’ [!UICONTROL Common Analytics Plugins] extension
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation d’addProductEvent
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé de Launch

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Développez l’ [!UICONTROL Configure tracking using custom code] accordéon, ce qui révèle le [!UICONTROL Open Editor] bouton.
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

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

## Utilisation du plug-in

La méthode `addProductEvent` utilise les arguments suivants :

* **`en`** (obligatoire, chaîne) : événement à ajouter à la dernière entrée de la variable `products`. Si la variable `products` est vide, alors une entrée de produit « vide » est créée avec l’événement associé (ainsi que sa valeur).
* **`ev`** (obligatoire, chaîne) : valeur attribuée à l’événement numérique ou monétaire dans l’argument `en`.  La valeur par défaut est `1` lorsqu’elle n’est pas définie.
* **`ap`** (facultatif, booléen) : si la variable products contient actuellement plusieurs entrées de produit, une valeur de `true` (ou `1`) ajoute l’événement à toutes les entrées de produit.  La valeur par défaut est `false` lorsqu’elle n’est pas définie.

Le plug-in `addProductEvent` ne renvoie rien. Il ajoute plutôt l’événement et sa valeur à la variable `products`. De même, le plug-in ajoute automatiquement l’événement à la variable [`events`](../page-vars/events/events-overview.md), puisqu’il y est également obligatoire.

## Cookies

Le plug-in addProductEvent ne crée ni n’utilise de cookies.

## Exemples d’appels

### Exemple 1

Le code suivant définit la `s.products` variable sur `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`.

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

Le code ci-dessus définit également la `s.events` variable sur `"purchase,event35"`

### Exemple 2

Le code suivant définit la `s.products` variable sur `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

Lorsque le troisième argument de l&#39; `addProductEvent` appel est `true` (ou `1`), chaque entrée de produit a le  spécifié dans l&#39;appel ajouté à sa valeur.

### Exemple 3

Le code suivant définit la `s.products` variable sur `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

Le code ci-dessus définit également la `s.events` variable sur `"purchase,event2,event33,event34,event35"`

### Exemple 4

Le code suivant définit la `s.products` variable sur `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

Le code ci-dessus définit également la `s.events` variable sur `"purchase,event2,event33,event34,event35"`.

>[!NOTE] Le deuxième argument de l’appel peut être un entier **ou** une chaîne représentant un nombre entier.

### Exemple 5

Si `s.products` n’est pas déjà défini, le code suivant le définit sur `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

Le code ci-dessus s’ajoute également `"event35"` à la fin de `s.events` ou, si **ce n’est pas déjà fait, le code ci-dessus se définit**`s.events` `s.events` sur `"event35"`

## Historique des versions

### 1.0 (7 octobre 2019)

* Version initiale.
