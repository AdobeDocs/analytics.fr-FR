---
title: addProductEvent
description: Permet d’ajouter des événements personnalisés aux variables products et events.
translation-type: ht
source-git-commit: 3359ed8e7ef7979be57ca5ec9ca1803fc52afe88
workflow-type: ht
source-wordcount: '632'
ht-degree: 100%

---


# Plug-in Adobe : addProductEvent

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `addProductEvent` ajoute un événement numérique ou monétaire à la variable [`products`](../page-vars/products.md). Adobe recommande d’utiliser ce plug-in si vous souhaitez ajouter un événement numérique ou monétaire à la variable `products` sans vous soucier du format de la chaîne de produit. Ce plug-in n’est pas nécessaire si vous n’utilisez pas d’événements numériques ou monétaires dans la variable `products`.

## Installation du plug-in à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
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
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvent v2.0 */
function addProductEvent(en,ev,ap){var f=en,g=ev,c=ap;if("-v"===f)return{plugin:"addProductEvent",version:"2.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,e;b<window.s_c_il.length;b++)if(e=window.s_c_il[b],e._c&&"s_c"===e._c)return e}();if("undefined"!==typeof d&&(d.contextData.addProductEvent="2.0",window.apl=window.apl||function(b,e,c,d,f){function g(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!b||"string"===typeof b){if("string"!==typeof e||""===e)return b;c=c||",";d=d||c;1==d&&(d=c,f||(f=1));2==d&&1!=f&&(d=c);e=e.split(",");k=e.length;for(var h=0;h<k;h++)g(b,e[h],c,f)||(b=b?b+d+e[h]:e[h])}return b},"string"===typeof f))if(g=isNaN(g)?"1":String(g),c=c||!1,d.events=window.apl(d.events,f),d.products){var l=d.products.split(","),m=l.length;c=c?0:m-1;for(var b;c<m;c++)b=l[c].split(";"),b[4]&&-1<b[4].indexOf("event")?b[4]=b[4]+"|"+f+"="+g:b[5]?b[4]=f+"="+g:b[4]||(b[3]||(b[3]=""),b[2]||(b[2]=""),b[1]||(b[1]=""),b[4]=f+"="+g),l[c]=b.join(";");d.products=l.join(",")}else d.products=";;;;"+f+"="+g};
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

Le code suivant définit la variable `s.products` sur `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`.

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

Le code ci-dessus définit également la variable `s.events` sur `"purchase,event35"`

### Exemple 2

Le code suivant définit la variable `s.products` sur `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

Lorsque le troisième argument de l’appel `addProductEvent`est `true` (ou `1`), l’événement spécifié dans l’appel est ajouté à la valeur de chaque entrée de produit.

### Exemple 3

Le code suivant définit la variable `s.products` sur `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

Le code ci-dessus définit également la variable `s.events` sur `"purchase,event2,event33,event34,event35"`

### Exemple 4

Le code suivant définit la variable `s.products` sur `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

Le code ci-dessus définit également la variable `s.events` sur `"purchase,event2,event33,event34,event35"`.

>[!NOTE]
>
>Le second argument de l’appel peut être un entier **ou** une chaîne représentant un nombre entier

### Exemple 5

Si `s.products` n’est pas déjà défini, le code suivant le définit sur `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

Le code ci-dessus ajoute également `"event35"` à la fin de `s.events` **ou**, si `s.events` n’est pas déjà défini, le code ci-dessus définit `s.events` sur `"event35"`

## Historique des versions

### 2.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 1.0 (7 octobre 2019)

* Version initiale.
