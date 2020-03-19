---
title: 'manageVars  '
description: Modifiez les valeurs de plusieurs variables Analytics à la fois.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Module externe Adobe : manageVars

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `manageVars` module externe vous permet de manipuler simultanément les valeurs de plusieurs variables Analytics. Vous pouvez également définir des valeurs en minuscules ou supprimer simultanément des caractères superflus de plusieurs valeurs de variable. Adobe recommande d’utiliser ce module externe si vous souhaitez nettoyer la valeur de plusieurs variables à la fois.

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
   * Type d&#39;action : Initialiser manageVars
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

## Utilisation du module externe

La `manageVars` méthode utilise les arguments suivants :

* **`cb`** (obligatoire, chaîne) : Nom d’une fonction de rappel utilisée par le module externe pour manipuler les variables Analytics. Vous pouvez utiliser une fonction Adobe comme `cleanStr` ou votre propre fonction personnalisée.
* **`l`** (facultatif, chaîne) : délimité par des virgules de variables Analytics que vous souhaitez manipuler. Par défaut, TOUTES les variables Adobe Analytics ne sont pas définies, ce qui inclut :
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
   * Toutes les variables 
   * Toutes les variables de données contextuelles
* **`Il`** (facultatif, booléen) : Définissez cette variable sur `false` si vous souhaitez *exclure* le des variables déclarées dans l’ `l` argument au lieu de les inclure. Par défaut, `true`.

L’appel de cette méthode ne renvoie rien. Il modifie plutôt les valeurs des variables Analytics en fonction de la fonction de rappel souhaitée.

## Exemples d’appels

### Exemple n° 1

Le code suivant...

```js
s.manageVars("lowerCaseVars");
```

...change les valeurs de toutes les variables décrites ci-dessus en versions lues.  La seule exception à cette règle est la variable de , comme certains des  (par exemple scAdd, scCheckout, etc.) sont sensibles à la casse et ne doivent pas être lus

### Exemple n° 2

Le code suivant...

```js
s.manageVars("lowerCaseVars", "events", false);
```

...produit essentiellement le même résultat que le premier exemple, car la variable  n’est pas lue par défaut.

### Exemple n° 3

Le code suivant...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...modifiera (en minuscules, par exemple) uniquement les valeurs d’eVar1, d’eVar2, d’eVar3 et de2.

### Exemple n° 4

Le code suivant...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...modifiera (en minuscules, par exemple) les valeurs de toutes les variables décrites ci-dessus SAUF pour eVar1, eVar2, eVar3 et2.

### Exemple n° 5

Le code suivant...

```js
s.manageVars("cleanStr");
```

...modifie les valeurs de toutes les variables décrites ci-dessus, y compris les variables de  du.  Plus précisément, la fonction de rappel cleanStr effectue les actions suivantes sur la valeur de chaque variable :

* Supprime le codage HTML
* Supprime les espaces trouvés au début et à la fin de la valeur
* Remplace les guillemets simples gauche/droite (ex. ’) avec un guillemet simple droit (&#39;)
* Remplace les caractères de tabulation, les caractères de nouvelle ligne et les caractères de retour chariot par des espaces
* Remplace tous les  de (ou triples, etc.) espaces avec des espaces uniques

## Historique des versions

### 2.1 (14 janvier 2019)

* Correction de bogues pour les navigateurs Internet Explorer 11.
* Modifications pour `s.cleanStr`, qui utilise désormais la `cleanStr` fonction régulière.

### 2.0 (7 mai 2018)

* Version ponctuelle (y compris la réanalyse complète/la réécriture du module externe)
* Fonction `cleanStr` de rappel ajoutée
