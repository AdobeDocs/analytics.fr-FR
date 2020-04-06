---
title: manageVars
description: Permet de modifier les valeurs de plusieurs variables Analytics à la fois.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : manageVars

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `manageVars` vous permet de manipuler simultanément les valeurs de plusieurs variables Analytics. Vous pouvez également définir des valeurs en minuscules ou supprimer les caractères superflus de plusieurs valeurs de variables en même temps. Adobe recommande d’utiliser ce plug-in si vous souhaitez effacer la valeur de plusieurs variables à la fois.

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
   * Type d’action : initialisation de manageVars
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
/* Adobe Consulting Plugin: manageVars v2.1 (Requires pt plug-in and other necessary callback plug-ins) */
s.manageVars=function(cb,l,il){var s=this;if(!s[cb])return!1;l=l||"";il=il||!0;var a,d="pageName,purchaseID,channel,server, pageType,campaign,state,zip,events,products,transactionID";for(a=1;76>a;a++)d+=",prop"+a;for(a=1;251>a;a++)d+=",eVar"+a;for(a=1;6>a;a++)d+=",hier"+a;for(a=1;4>a;a++)d+=",list"+a;for(a in s.contextData)d+=",contextData."+a;if(l){if(1==il)d=l.replace("['", ".").replace("']","");else if(0==il){l=l.split(",");il=d.split(",");d="";for(x in l)for(y in-1<l[x].indexOf("contextData")&& (l[x]="contextData."+l[x].split("'")[1]),il)l[x]===il[y]&&(il[y]="");for(y in il)d+=il[y]?","+il[y]:""}s.pt(d,",",cb,0);return!0} return""===l&&il?(s.pt(d,",",cb,0),!0):!1};

/* Adobe Consulting Plugin: lowerCaseVars for manageVars (Requires manageVars plug-in) */
s.lowerCaseVars=function(v){var s=this;s[v]&&("events"!==v&&-1===v.indexOf("contextData")?(s[v]=s[v].toString(),0!== s[v].indexOf("D=")&&(s[v]=s[v].toLowerCase())):-1<v.indexOf("contextData")&&(v=v.substring(v.indexOf(".")+1),s.contextData[v]&& (s.contextData[v]=s.contextData[v].toString().toLowerCase())))};

/* Adobe Consulting Plugin: cleanStr for manageVars (Requires manageVars and cleanStr plug-ins) */
s.cleanStr=function(v){var s=this;s[v]&&"function"!==typeof cleanStr&&(0>v.indexOf("contextData")?s[v]=cleanStr(s[v]): (v=v.substring(v.indexOf(".")+1),s.contextData[v]&&(s.contextData[v]=cleanStr(s.contextData[v].toString()))))};

/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g, "'").replace(/\t+/g,"").replace(/[\n\r]/g," ");for(;-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};

/* Adobe Consulting Plugin: pt v2.01 */
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `manageVars` utilise les arguments suivants :

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

L’appel de cette méthode ne renvoie rien. En revanche, il modifie les valeurs des variables Analytics selon la fonction de rappel souhaitée.

## Exemples d’appels

### Exemple 1

Le code suivant…

```js
s.manageVars("lowerCaseVars");
```

…modifie les valeurs de toutes les variables décrites ci-dessus en versions minuscules.  La seule exception à cette règle est la variable events, car certains événements (par exemple scAdd, scCheckout, etc.) sont sensibles à la casse et ne doivent pas être mis en minuscules.

### Exemple 2

Le code suivant…

```js
s.manageVars("lowerCaseVars", "events", false);
```

…produit pratiquement le même résultat que le premier exemple, car la variable events n’est pas mise en minuscule par défaut.

### Exemple 3

Le code suivant…

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

…ne modifie (en minuscules, par exemple) que les valeurs des variables eVar1, eVar2, eVar3 et list2.

### Exemple 4

Le code suivant…

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

…modifie (en minuscules, par exemple) les valeurs de toutes les variables décrites ci-dessus SAUF pour eVar1, eVar2, eVar3 et list2.

### Exemple 5

Le code suivant…

```js
s.manageVars("cleanStr");
```

…modifie les valeurs de toutes les variables décrites ci-dessus, y compris les variables events.  Plus précisément, la fonction de rappel cleanStr effectue les actions suivantes sur la valeur de chaque variable :

* Supprime le codage HTML.
* Supprime les espaces trouvés au début et à la fin de la valeur.
* Remplace les guillemets simples gauche/droite (par exemple ’) par un guillemet simple droit (&#39;).
* Remplace les caractères de tabulation, les renvois à la ligne et les retours chariot par des espaces.
* Remplace tous les espaces doubles (ou triples, etc.) par des espaces simples.

## Historique des versions

### 2.1 (14 janvier 2019)

* Correction de bogues pour les navigateurs Internet Explorer 11.
* Modifications pour `s.cleanStr`, qui utilise désormais la fonction `cleanStr` régulière.

### 2.0 (7 mai 2018)

* Nouvelle version (y compris la réanalyse/réécriture complète du plug-in)
* Ajout de la fonction de rappel `cleanStr`.
