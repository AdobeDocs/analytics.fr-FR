---
title: getVisitNum
description: Permet d’assurer le suivi du nombre de visites actuelles d’un visiteur.
feature: Variables
exl-id: 05b3f57c-7268-4585-a01e-583f462ff8df
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 78%

---

# Plug-in Adobe : getVisitNum

{{plug-in}}

Le plug-in `getVisitNum` renvoie le nombre de visites pour tous les visiteurs qui se rendent sur le site au cours du nombre de jours souhaité. Analysis Workspace propose une dimension « Nombre de visites » qui offre des fonctionnalités similaires. Adobe recommande d’utiliser ce plug-in si vous souhaitez avoir un meilleur contrôle sur la manière dont le nombre de visites est incrémenté. Ce plug-in n’est pas nécessaire si la dimension « Nombre de visites » intégrée dans Analysis Workspace est suffisante pour vos besoins en matière de rapports.

## Installation du module externe à l’aide de l’extension SDK Web

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec le SDK Web.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Balises]** sur la gauche, puis cliquez sur la propriété de balise de votre choix.
1. Cliquez sur **[!UICONTROL Extensions]** sur la gauche, puis cliquez sur le bouton **[!UICONTROL Catalogue]** tab
1. Recherchez et installez le **[!UICONTROL Plug-ins SDK Web courants]** extension .
1. Cliquez sur **[!UICONTROL Éléments de données]** sur la gauche, puis cliquez sur l’élément de données souhaité.
1. Définissez le nom de l’élément de données souhaité avec la configuration suivante :
   * Extension : Plug-ins SDK Web courants
   * Élément de données: `getVisitNum`
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
   * Type d’action : initialisation de getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.2 */
function getVisitNum(rp,erp){var a=rp,l=erp;function m(c){return isNaN(c)?!1:(parseFloat(c)|0)===parseFloat(c)}function n(c){var b=new Date,e=isNaN(c)?0:Math.floor(c);b.setHours(23);b.setMinutes(59);b.setSeconds(59);"w"===c&&(e=6-b.getDay());if("m"===c){e=b.getMonth()+1;var a=b.getFullYear();e=(new Date(a?a:1970,e?e:1,0)).getDate()-b.getDate()}b.setDate(b.getDate()+e);"y"===c&&(b.setMonth(11),b.setDate(31));return b}if("-v"===a)return{plugin:"getVisitNum",version:"4.2"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof f&&(f.contextData.getVisitNum="4.2");window.cookieWrite=window.cookieWrite||function(c,b,e){if("string"===typeof c){var a=window.location.hostname,d=window.location.hostname.split(".").length-1;if(a&&!/^[0-9.]+$/.test(a)){d=2<d?d:2;var h=a.lastIndexOf(".");if(0<=h){for(;0<=h&&1<d;)h=a.lastIndexOf(".",h-1),d--;h=0<h?a.substring(h):a}}g=h;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var f=new Date;f.setTime(f.getTime()+6E4*e)}else f=e;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:365;l="undefined"!==typeof l?!!l:m(a)?!0:!1;var p=(new Date).getTime();f=n(a);if(window.cookieRead("s_vnc"+a))var d=window.cookieRead("s_vnc"+a).split("&vn="),k=d[1];if(window.cookieRead("s_ivc"))return k?(window.cookieWrite("s_ivc",!0,30),k):"unknown visit number";if("undefined"!==typeof k)return k++,d=l&&m(a)?p+864E5*a:d[0],f.setTime(d),window.cookieWrite("s_vnc"+a,d+"&vn="+k,f),window.cookieWrite("s_ivc",!0,30),k;d=m(a)?p+864E5*a:n(a).getTime();window.cookieWrite("s_vnc"+a,d+"&vn=1",f);window.cookieWrite("s_ivc",!0,30);return"1"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `getVisitNum` utilise les arguments suivants :

* **`rp`** (facultatif, entier OU chaîne) : nombre de jours avant la réinitialisation du compteur de visites.  La valeur par défaut est `365` lorsqu’elle n’est pas définie.
   * Lorsque cet argument est défini sur `"w"`, le compteur se réinitialise à la fin de la semaine (ce samedi à 23 h 59).
   * Lorsque cet argument est défini sur `"m"`, le compteur se réinitialise à la fin du mois (le dernier jour de ce mois).
   * Lorsque cet argument est défini sur `"y"`, le compteur se réinitialise à la fin de l’année (le 31 décembre).
* **`erp`** (facultatif, booléen) : lorsque l’argument `rp` est un nombre, cet argument détermine si le délai d’expiration du nombre de visites doit être prolongé. S’il est défini sur `true`, les accès ultérieurs à votre site réinitialisent le compteur de visites. S’il est défini sur `false`, les accès ultérieurs à votre site ne se prolongent pas lorsque le compteur de visites est réinitialisé. La valeur par défaut est `true`. Cet argument n’est pas valide lorsque l’argument `rp` est une chaîne.

Le nombre de visites augmente chaque fois que le visiteur revient sur votre site après 30 minutes d’inactivité. Lʼappel de cette fonction renvoie un nombre entier représentant le nombre de visites actuel du visiteur.

Ce plug-in définit un cookie propriétaire appelé `"s_vnc[LENGTH]"` où `[LENGTH]` est la valeur transmise à l’argument `rp`. Par exemple, `"s_vncw"`, `"s_vncm"`, ou `"s_vnc365"`. La valeur du cookie est une combinaison d’un horodatage Unix qui représente le moment où le compteur de visites se réinitialise, par exemple à la fin de la semaine, à la fin du mois ou après 365 jours d’inactivité. Il contient également le nombre de visites actuel. Ce plug-in définit un autre cookie nommé `"s_ivc"` qui est défini sur `true` et expire après 30 minutes d’inactivité.

## Exemples

```js
// Sets prop4 to the visit number, storing the value in a cookie that expires in 365 days
// The cookie value is reset only if there are 365+ days of inactivity or the visitor clears their cookies.
s.prop4 = getVisitNum();

// Sets eVar4 to the visit number, storing the value in a cookie that expires in 200 days
// The cookie value is reset only if there are 200+ days of inactivity or the visitor clears their cookies.
s.eVar4 = getVisitNum(200);

// Sets eVar16 to the visit number, storing the value in a cookie that expires in 90 days.
// The cookie value is reset after 90 days, regardless of how many visits that happen in those 90 days.
s.eVar16 = getVisitNum(90,false);

// Track the visit number unique to the week, month, and year, all in separate variables
// The plug-in automatically creates three separate cookies to track these values
s.prop1 = getVisitNum("w");
s.prop2 = getVisitNum("m");
s.prop3 = getVisitNum("y");
```

## Historique des versions

### 4.2 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 4.11 (30 septembre 2019)

* Correction d’un problème en raison duquel l’argument `erp` était explicitement défini sur `false`.

### 4.1 (21 mai 2018)

* Mise à jour du plug-in `endOfDatePeriod` vers la version 1.1.

### 4.0 (17 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Suppression des arguments de cookies car le plug-in génère désormais dynamiquement des cookies en fonction de l’argument `rp`.

### 3.0 (5 juin 2016)

* Révision complète.
* Combinaison de toutes les solutions précédentes disponibles dans les différentes versions du plug-in `getVisitNum`.
