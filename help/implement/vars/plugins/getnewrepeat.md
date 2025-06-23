---
title: getNewRepeat
description: Permet de suivre l’activité des nouveaux visiteurs par rapport aux visiteurs réguliers.
feature: Appmeasurement Implementation
exl-id: 8f64e176-1926-4cb1-bfae-09d7e2c015ae
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 74%

---

# Plug-in Adobe : getNewRepeat

{{plug-in}}

Le plug-in `getNewRepeat` vous permet de déterminer si un visiteur sur le site est un nouveau visiteur ou un visiteur régulier pendant une période donnée. Adobe recommande d’utiliser ce plug-in si vous souhaitez identifier les visiteurs comme « nouveaux » sur la base d’un nombre de jours personnalisé. Ce plug-in n’est pas nécessaire si le traitement des visiteurs nouveaux/réguliers dans Analysis Workspace répond aux besoins de votre entreprise.

## Installation du plug-in à l’aide de l’extension Web SDK

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec Web SDK.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Balises]** à gauche, puis sur la propriété de balise de votre choix.
1. Cliquez sur **[!UICONTROL Extensions]** à gauche, puis sur l’onglet **[!UICONTROL Catalogue]**
1. Recherchez et installez l’extension **[!UICONTROL Plug-ins Web SDK courants]**.
1. Cliquez sur **[!UICONTROL Éléments de données]** à gauche, puis sur l’élément de données de votre choix.
1. Définissez le nom de l’élément de données de votre choix avec la configuration suivante :
   * Extension : plug-ins Web SDK courants
   * Élément de données : `getNewRepeat`
1. Définissez le paramètre `daysBeforeReset` sur la droite.
1. Enregistrez et publiez les modifications apportées à l’élément de données.

## Installation du plug-in implémentant manuellement le SDK Web

Ce plug-in n’est pas encore pris en charge pour une utilisation dans le cadre d’une implémentation manuelle de Web SDK.

## Installation du plug-in à l’aide de l’extension Adobe Analytics

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
   * Type d’action : initialisation de getNewRepeat
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension du plug-in des modules externes courants Analytics, vous pouvez utiliser l’éditeur de code personnalisé.

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
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `getNewRepeat` utilise les arguments suivants :

* **`d`** (entier, facultatif) : nombre minimum de jours requis entre les visites qui réinitialise le statut des visiteurs à `"New"`. Si cet argument n’est pas défini, la période par défaut est de 30 jours.

Cette fonction renvoie la valeur de `"New"` si le cookie défini par le plug-in nʼexiste pas ou a expiré. Elle renvoie la valeur de `"Repeat"` si le cookie défini par le plug-in existe et si le temps écoulé depuis l’accès actif et celui défini dans le cookie sont supérieurs à 30 minutes. Cette fonction renvoie la même valeur pour une visite complète.

Ce plug-in utilise un cookie nommé `"s_nr[LENGTH]"` où `[LENGTH]` est égal à l’argument `d`. Le cookie contient un horodatage Unix représentant l’heure actuelle et le statut actuel du visiteur (`"New"` ou `"Repeat"`).

## Exemples

```js
// Sets eVar1 to "New" if it is the visitor's first visit to the site, or they have not visited in at least 30 days. Otherwise, sets eVar1 to "Repeat".
s.eVar1 = getNewRepeat();

// Sets eVar2 to "New" if it is the visitor's first visit to the site, or they have not visited in at least a year (365 days). Otherwise, sets eVar2 to "Repeat".
s.eVar2 = getNewRepeat(365);
```

## Historique des versions

### 3.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 2.1 (30 septembre 2019)

* Réorganisation de la logique JavaScript pour réduire la taille du plug-in.

### 2.0 (16 avril 2018)

* Recompilation avec une taille de code réduite.
* Suppression de la possibilité de nommer le cookie pour stocker les informations relatives à la visite. Le plug-in nomme désormais dynamiquement le cookie en fonction de la valeur transmise à l’argument `d`.
