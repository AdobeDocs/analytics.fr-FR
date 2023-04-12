---
title: manageVars
description: Permet de modifier les valeurs de plusieurs variables Analytics à la fois.
feature: Variables
exl-id: b80d1c43-7e79-443e-84fb-1f1edffca461
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 88%

---

# Plug-in Adobe : manageVars

{{plug-in}}

Le plug-in `manageVars` vous permet de manipuler simultanément les valeurs de plusieurs variables Analytics. Vous pouvez également définir des valeurs en minuscules ou supprimer les caractères superflus de plusieurs valeurs de variables en même temps. Adobe recommande d’utiliser ce plug-in si vous souhaitez effacer la valeur de plusieurs variables à la fois.

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
   * Type d’action : initialisation de manageVars
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
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `manageVars` utilise les arguments suivants :

* **`cb`** (obligatoire, chaîne) : nom d’une fonction de rappel utilisée par le plug-in pour manipuler les variables Analytics. Vous pouvez utiliser une fonction Adobe comme `cleanStr` ou votre propre fonction personnalisée.
* **`l`** (facultatif, chaîne) : liste, délimitée par des virgules, de variables Analytics que vous souhaitez manipuler. La valeur par défaut est TOUTES les variables Adobe Analytics lorsqu’elle n’est pas définie, ce qui inclut :
   * `pageName`
   * `purchaseID`
   * `channel`
   * `server`
   * `pageType`
   * `campaign`
   * `state`
   * `zip`
   * `events`
   * `products`
   * `transactionID`
   * Toutes les props
   * Toutes les eVars
   * Toutes les variables de hiérarchie
   * Toutes les variables de liste
   * Toutes les variables de données contextuelles
* **`Il`** (facultatif, booléen) : définissez cet argument sur `false` si vous souhaitez *exclure* la liste des variables déclarées dans l’argument `l` au lieu de l’inclure. La valeur par défaut est `true`.

Lʼappel de cette fonction ne renvoie rien. En revanche, il modifie les valeurs des variables Analytics selon la fonction de rappel souhaitée.

## Exemples d’appels

### Exemple 1

Le code suivant…

```js
manageVars("lowerCaseVars");
```

…modifie les valeurs de toutes les variables décrites ci-dessus en versions minuscules.  La seule exception à cette règle est la variable events, car certains événements (par exemple scAdd, scCheckout, etc.) sont sensibles à la casse et ne doivent pas être mis en minuscules.

### Exemple 2

Le code suivant…

```js
manageVars("lowerCaseVars", "events", false);
```

…produit pratiquement le même résultat que le premier exemple, car la variable events n’est pas mise en minuscule par défaut.

### Exemple 3

Le code suivant…

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

…ne modifie (en minuscules, par exemple) que les valeurs des variables eVar1, eVar2, eVar3 et list2.

### Exemple 4

Le code suivant…

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

…modifie (en minuscules, par exemple) les valeurs de toutes les variables décrites ci-dessus SAUF pour eVar1, eVar2, eVar3 et list2.

### Exemple 5

Le code suivant…

```js
manageVars("cleanStr");
```

…modifie les valeurs de toutes les variables décrites ci-dessus, y compris les variables events.  Plus précisément, la fonction de rappel cleanStr effectue les actions suivantes sur la valeur de chaque variable :

* Supprime le codage HTML.
* Supprime les espaces trouvés au début et à la fin de la valeur.
* Remplace les guillemets simples gauche/droite par un guillemet simple droit (`'`)
* Remplace les caractères de tabulation, les renvois à la ligne et les retours chariot par des espaces.
* Remplace tous les espaces doubles (ou triples, etc.) par des espaces simples.

## Historique des versions

### 3.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 2.1 (14 janvier 2019)

* Correction de bogues pour les navigateurs Internet Explorer 11.
* Modifications pour `s.cleanStr`, qui utilise désormais la fonction `cleanStr` régulière.

### 2.0 (7 mai 2018)

* Nouvelle version (y compris la réanalyse/réécriture complète du plug-in)
* Ajout de la fonction de rappel `cleanStr`.
