---
title: getValOnce
description: Permet d’empêcher la définition d’une variable Analytics sur la même valeur deux fois de suite.
feature: Variables
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 74%

---

# Plug-in Adobe : getValOnce

{{plug-in}}

Le plug-in `getValOnce` empêche qu’une variable soit définie plusieurs fois sur la même valeur. Adobe recommande d’utiliser ce plug-in lorsque vous souhaitez dédupliquer les occurrences dans lesquelles un visiteur actualise une page ou consulte une page donnée à plusieurs reprises. Ce plug-in n’est pas nécessaire si la mesure « Occurrences » dans Analysis Workspace ne vous intéresse pas.

## Installation du module externe à l’aide de l’extension SDK Web

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec le SDK Web.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Balises]** à gauche, puis sur la propriété de balise de votre choix.
1. Cliquez sur **[!UICONTROL Extensions]** à gauche, puis sur l’onglet **[!UICONTROL Catalogue]**
1. Recherchez et installez l’extension **[!UICONTROL Common Web SDK Plugins]** .
1. Cliquez sur **[!UICONTROL Éléments de données]** à gauche, puis sur l’élément de données de votre choix.
1. Définissez le nom de l’élément de données souhaité avec la configuration suivante :
   * Extension : modules externes SDK Web courants
   * Élément de données : `getValOnce`
1. Définissez les paramètres de votre choix à droite.
1. Enregistrez et publiez les modifications sur l’élément de données.

## Installation manuelle du plug-in implémentant le SDK Web

Ce module externe n’est pas encore pris en charge pour une utilisation dans une mise en oeuvre manuelle du SDK Web.

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
   * Type d’action : initialisation de getValOnce
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

* Correction d’un bogue d’expiration

### 3.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 2,01

* Correction d’un problème lié à l’écriture de cookies.

### 2,0

* Nouvelle version (recompilé, taille de code réduite).

### 1,1

* Ajout de la possibilité de choisir des minutes ou des jours pour l’expiration via le paramètre `t`.
* Correction de la portée de la variable `k` utilisée pour la limiter au plug-in uniquement. Cette modification permet d’éviter d’éventuelles interférences avec d’autres codes sur la page.
