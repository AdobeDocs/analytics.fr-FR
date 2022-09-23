---
title: getValOnce
description: Permet d’empêcher la définition d’une variable Analytics sur la même valeur deux fois de suite.
feature: Variables
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
source-git-commit: 02b7e45bb4141d92cd37ef7ccbbbb9bdbc70bc2a
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 96%

---

# Plug-in Adobe : getValOnce

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getValOnce` empêche qu’une variable soit définie plusieurs fois sur la même valeur. Adobe recommande d’utiliser ce plug-in lorsque vous souhaitez dédupliquer les occurrences dans lesquelles un visiteur actualise une page ou consulte une page donnée à plusieurs reprises. Ce plug-in n’est pas nécessaire si la mesure « Occurrences » dans Analysis Workspace ne vous intéresse pas.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getValOnce
1. Save and publish the changes to the rule.-->

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [Collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getValOnce v3.1 */
function getValOnce(vtc,cn,et,ep){var e=vtc,i=cn,t=et,n=ep;  if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.1"};var o=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();if(void 0!==o&&(o.contextData.getValOnce="3.1"),window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){var n=window.location.hostname,o=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){o=2<o?o:2;var r=n.lastIndexOf(".");if(0<=r){for(;0<=r&&1<o;)r=n.lastIndexOf(".",r-1),o--;r=0<r?n.substring(r):n}}if(g=r,i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var f=new Date;f.setTime(f.getTime()+6e4*t)}else f=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!=typeof cookieRead)&&cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),n=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>n?i.length:n)))?e:""},e){var i=i||"s_gvo",t=t||0,n="m"===n?6e4:864e5;if(e!==cookieRead(i)){var r=new Date;return r.setTime(r.getTime()+t*n),cookieWrite(i,e,0===t?0:r),e}}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `getValOnce` utilise les arguments suivants :

* **`vtc`** (obligatoire, chaîne) : variable à vérifier et à examiner pour savoir si elle vient d’être définie sur une valeur identique.
* **`cn`** (facultatif, chaîne) : nom du cookie qui contient la valeur à vérifier. La valeur par défaut est `"s_gvo"`.
* **`et`** (facultatif, entier) : expiration du cookie en jours (ou en minutes, selon l’argument `ep`). La valeur par défaut est `0`, qui expire à la fin de la session du navigateur.
* **`ep`** (facultatif, chaîne) : ne définissez cet argument que si `et` est également défini. Définissez cet argument sur `"m"` si vous souhaitez que le délai d’expiration de l’argument `et` soit exprimé en minutes plutôt qu’en jours. La valeur par défaut est `"d"`, qui définit l’argument `et` en jours.

Si lʼargument `vtc` et la valeur du cookie correspondent, cette fonction renvoie une chaîne vide. Si lʼargument `vtc` et la valeur du cookie ne correspondent pas, la fonction renvoie lʼargument `vtc` sous forme de chaîne.

## Exemples

```js
// Prevent the same value from being passed in to the campaign variable more than once in a row for next 30 days
s.campaign = getValOnce(s.campaign,"s_campaign",30);

// Prevent the same value from being passed in to eVar2 more than once in a row for the browser session
s.eVar2 = getValOnce(s.eVar2,"s_ev2");

// Prevent the same value from being passed in to eVar8 more than once in a row for 10 minutes
s.eVar8 = getValOnce(s.eVar8,"s_ev8",10,"m");
```

## Historique des versions

### 3.1 (22 septembre 2022)

* Correction d’un bogue relatif à l’expiration

### 3.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 2,01

* Correction d’un problème lié à l’écriture de cookies.

### 2,0

* Nouvelle version (recompilé, taille de code réduite).

### 1,1

* Ajout de la possibilité de choisir des minutes ou des jours pour l’expiration via le paramètre `t`.
* Correction de la portée de la variable `k` utilisée pour la limiter au plug-in uniquement. Cette modification permet d’éviter d’éventuelles interférences avec d’autres codes sur la page.
