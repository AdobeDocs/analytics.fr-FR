---
title: addProductEvent
description: Permet d’ajouter des événements personnalisés aux variables products et events.
feature: Variables
exl-id: 74f4cb93-714a-4d2b-88f3-408d032f6811
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 86%

---

# Plug-in Adobe : addProductEvent

{{plug-in}}

Le plug-in `addProductEvent` ajoute un événement numérique ou monétaire à la variable [`products`](../page-vars/products.md). Adobe recommande d’utiliser ce plug-in si vous souhaitez ajouter un événement numérique ou monétaire à la variable `products` sans vous soucier du format de la chaîne de produit. Ce plug-in n’est pas nécessaire si vous n’utilisez pas d’événements numériques ou monétaires dans la variable `products`.

## Installation du module externe à l’aide du SDK Web ou de l’extension SDK Web

Ce module externe n’est pas encore pris en charge pour une utilisation dans le SDK Web.

## Installation du module externe à l’aide de l’extension Adobe Analytics

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation d’addProductEvent
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension de plug-in Plugins Analytics communs, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à la [collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous l’extension Adobe Analytics.
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

La fonction `addProductEvent` utilise les arguments suivants :

* **`en`** (obligatoire, chaîne) : événement à ajouter à la dernière entrée de la variable `products`. Si la variable `products` est vide, alors une entrée de produit « vide » est créée avec l’événement associé (ainsi que sa valeur).
* **`ev`** (obligatoire, chaîne) : valeur attribuée à l’événement numérique ou monétaire dans l’argument `en`.  La valeur par défaut est `1` lorsqu’elle n’est pas définie. Les nombres non encadrés par des guillemets sont également valables.
* **`ap`** (facultatif, booléen) : si la variable products contient actuellement plusieurs entrées de produit, une valeur de `true` (ou `1`) ajoute l’événement à toutes les entrées de produit.  La valeur par défaut est `false` lorsqu’elle n’est pas définie.

Le plug-in `addProductEvent` ne renvoie rien. Il ajoute plutôt l’événement et sa valeur à la variable `products`. De même, le plug-in ajoute automatiquement l’événement à la variable [`events`](../page-vars/events/events-overview.md), puisqu’il y est également obligatoire.

## Cookies

La fonction `addProductEvent` ne crée ni nʼutilise de cookies.

## Exemples

```js
// Sets the products variable to ";product1;3;300,;product2;2;122,;product3;1;25;event35=25".
// Also sets the events variable to "purchase,event35".
s.products = ";product1;3;300,;product2;2;122,;product3;1;25";
s.events = "purchase";
addProductEvent("event35", "25");

// Sets the products variable to ";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25".
s.products = ";product1;3;300,;product2;2;122,;product3;1;25";
addProductEvent("event35", 25, true);

// Sets the products variable to ";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"
// Also sets the s.events variable to "purchase,event2,event33,event34,event35".
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
addProductEvent("event33", "12");
addProductEvent("event34", "10");
addProductEvent("event35", "15");

// Sets the products variable to ";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15".
// Also sets the events variable to "purchase,event2,event33,event34,event35".
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
addProductEvent("event33", "12", 1);
addProductEvent("event34", 10, 1);
addProductEvent("event35", "15", 1);

// If the products variable isn't already set, sets it to ";;;;event35=25".
// Also appends event35 to the events variable.
addProductEvent("event35", "25");
```

## Historique des versions

### 2.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 1.0 (7 octobre 2019)

* Version initiale.
