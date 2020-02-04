---
title: getGeoCoordinates
description: Assurez le suivi de la géolocalisation d’un visiteur.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Module externe Adobe :getGeoCoordinates

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getGeoCoordinates` module externe vous permet de capturer la latitude et la longitude des périphériques des visiteurs. Adobe recommande d’utiliser ce module externe si vous souhaitez capturer des données de géolocalisation dans des variables Analytics.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur une propriété.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Catalogue] .
1. Installation et publication de l’extension Plugins [!UICONTROL Analytics] communs
1. Pour toute règle de lancement dans laquelle vous souhaitez utiliser le module externe, ajoutez une action avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser addProductEvar
1. Enregistrer et publier les modifications apportées à la règle

## Installation du module externe à l’aide de l’éditeur de code personnalisé Lancer

Si vous ne souhaitez pas utiliser l’extension du module externe, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété souhaitée.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez la section [!UICONTROL Configurer le suivi à l’aide de l’accordéon de code] personnalisé, qui affiche le bouton [!UICONTROL Ouvrir l’éditeur] .
1. Ouvrez l’éditeur de code personnalisé et collez le code du module externe fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du module externe à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide `s_gi`). La conservation des commentaires et des numéros de version du code dans votre implémentation permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getGeoCoordinates` méthode n’utilise aucun argument. Elle renvoie l’une des valeurs suivantes :

* `"geo coordinates not available"`: Pour les périphériques qui ne disposent pas de données de géolocalisation disponibles au moment de l’exécution du module. Cette valeur est courante lors du premier accès de la visite, en particulier lorsque les visiteurs doivent d’abord donner leur consentement au suivi de leur emplacement.
* `"error retrieving geo coordinates"`: Lorsque le module externe rencontre des erreurs lors de la tentative de récupération de l’emplacement du périphérique
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`: Où [LATITUDE]/[LONGITUDE] sont respectivement la latitude et la longitude

> [!NOTE] Les valeurs de coordonnées sont arrondies à la quatrième décimale la plus proche. Par exemple, la valeur de `"40.438635333"` est arrondie `"40.4386"` pour limiter le nombre de valeurs uniques à capturer. Les valeurs sont suffisamment proches pour indiquer l’emplacement exact de l’appareil dans un rayon d’environ 6 mètres.

Ce module externe utilise un cookie nommé `"s_ggc"` pour stocker les coordonnées entre les accès, le cas échéant.

## Exemples d’appels

### Exemple n° 1

Le code suivant...

```js
s.eVar1 = s.getGeoCoordinates();
```

...définit eVar1 sur l’une des valeurs renvoyées ci-dessus, selon l’état du périphérique du visiteur.

### Exemple n° 2

Le code suivant extrait la latitude et la longitude dans leurs propres variables appelées finalLatitude et finalLongitude pour les utiliser dans d&#39;autres codes/applications

```js
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```

A partir de là, vous pouvez déterminer si un visiteur se trouve, par exemple, dans la Statue de la Liberté :

```js
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
  var visitorAtStatueOfLiberty = true;
else
  var visitorAtStatueOfLiberty = false;
```

## Historique des versions

### 1.0 (25 mai 2015)

* Version initiale.
