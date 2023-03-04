---
title: getGeoCoordinates
description: Permet d’assurer le suivi de la géolocalisation d’un visiteur.
feature: Variables
exl-id: 8620d083-7fa6-432b-891c-e24907e7c466
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 100%

---

# Plug-in Adobe : getGeoCoordinates

{{plug-in}}

Le plug-in `getGeoCoordinates` vous permet de relever la latitude et la longitude des appareils des visiteurs. Adobe recommande d’utiliser ce plug-in si vous souhaitez collecter des données de géolocalisation dans des variables Analytics.

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
    * Action Type: Initialize getGeoCoordinates
1. Save and publish the changes to the rule.-->

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

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
/* Adobe Consulting Plugin: getGeoCoordinates v2.0  */
function getGeoCoordinates(){if(arguments&&"-v"===arguments[0])return{plugin:"getGeoCoordinates",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getGeoCoordinates="2.0");window.cookieWrite=window.cookieWrite||function(a,c,f){if("string"===typeof a){var h=window.location.hostname,b=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){b=2<b?b:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<b;)e=h.lastIndexOf(".",e-1),b--;e=0<e?h.substring(e):h}}g=e;c="undefined"!==typeof c?""+c:"";if(f||""===c)if(""===c&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(c)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===c:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var c=" "+document.cookie,b=c.indexOf(" "+a+"="),d=0>b?b:c.indexOf(";",b);return(a=0>b?"":decodeURIComponent(c.substring(b+2+a.length,0>d?c.length:d)))?a:""};var d="";b=cookieRead("s_ggc").split("|");var k={timeout:5E3,maximumAge:0},l=function(a){a=a.coords;cookieWrite("s_ggc",parseFloat(a.latitude.toFixed(4))+"|"+parseFloat(a.longitude.toFixed(4)),30);d="latitude="+parseFloat(a.latitude.toFixed(4))+" | longitude="+parseFloat(a.longitude.toFixed(4))},m=function(a){d="error retrieving geo coordinates"};1<b.length&&(d="latitude="+b[0]+" | longitude="+b[1]);navigator.geolocation&&navigator.geolocation.getCurrentPosition(l,m,k);""===d&&(d="geo coordinates not available");return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `getGeoCoordinates` nʼutilise aucun argument. Elle renvoie l’une des valeurs suivantes :

* `"geo coordinates not available"` : pour les appareils qui ne disposent pas de données de géolocalisation au moment de l’exécution du plug-in. Cette valeur est courante lors du premier accès de la visite, en particulier lorsque les visiteurs doivent d’abord donner leur consentement pour le suivi de leur emplacement.
* `"error retrieving geo coordinates"` : lorsque le plug-in rencontre des erreurs lors de la tentative de récupération de l’emplacement de l’appareil.
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"` : où [LATITUDE]/[LONGITUDE] sont respectivement la latitude et la longitude.

>[!NOTE]
>
>Les valeurs des coordonnées sont arrondies à la quatrième décimale la plus proche. Par exemple, la valeur de `"40.438635333"` est arrondie à `"40.4386"` pour limiter le nombre de valeurs uniques à saisir. Les valeurs sont suffisamment proches pour déterminer l’emplacement exact de l’appareil dans un rayon d’environ 6 mètres.

Ce plug-in utilise un cookie nommé `"s_ggc"` pour stocker les coordonnées entre les accès si nécessaire.

## Exemples

```js
// Sets eVar1 to one of the above return values depending on the visitor's device status.
s.eVar1 = getGeoCoordinates();

// Extracts latitude and longitude into their own variables called finalLatitude and finalLongitude for use in other code/applications.
var coordinates = getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}

// From there, you can determine whether a visitor is at, for example, the Statue of Liberty:
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongitude >= -74.0446 && finalLongitude <= -74.0444)
{
  var visitorAtStatueOfLiberty = true;
}
else
{
  var visitorAtStatueOfLiberty = false;
}
```

## Historique des versions

### 2.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 1.0 (25 mai 2015)

* Version initiale.
