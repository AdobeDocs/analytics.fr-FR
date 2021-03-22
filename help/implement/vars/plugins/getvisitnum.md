---
title: getVisitNum
description: Permet d’assurer le suivi du nombre de visites actuelles d’un visiteur.
translation-type: tm+mt
source-git-commit: fb1cdcb53732be46037a79587fc2541e629496e3
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 99%

---


# Plug-in Adobe : getVisitNum

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getVisitNum` renvoie le nombre de visites pour tous les visiteurs qui se rendent sur le site au cours du nombre de jours souhaité. Analysis Workspace propose une dimension « Nombre de visites » qui offre des fonctionnalités similaires. Adobe recommande d’utiliser ce plug-in si vous souhaitez avoir un meilleur contrôle sur la manière dont le nombre de visites est incrémenté. Ce plug-in n’est pas nécessaire si la dimension « Nombre de visites » intégrée dans Analysis Workspace est suffisante pour vos besoins en matière de rapports.

## Installation du plug-in à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation de getVisitNum
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé de Launch

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
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

La méthode `getVisitNum` utilise les arguments suivants :

* **`rp`** (facultatif, entier OU chaîne) : nombre de jours avant la réinitialisation du compteur de visites.  La valeur par défaut est `365` lorsqu’elle n’est pas définie.
   * Lorsque cet argument est défini sur `"w"`, le compteur se réinitialise à la fin de la semaine (ce samedi à 23 h 59).
   * Lorsque cet argument est défini sur `"m"`, le compteur se réinitialise à la fin du mois (le dernier jour de ce mois).
   * Lorsque cet argument est défini sur `"y"`, le compteur se réinitialise à la fin de l’année (le 31 décembre).
* **`erp`** (facultatif, booléen) : lorsque l’argument `rp` est un nombre, cet argument détermine si le délai d’expiration du nombre de visites doit être prolongé. S’il est défini sur `true`, les accès ultérieurs à votre site réinitialisent le compteur de visites. S’il est défini sur `false`, les accès ultérieurs à votre site ne se prolongent pas lorsque le compteur de visites est réinitialisé. La valeur par défaut est `true`. Cet argument n’est pas valide lorsque l’argument `rp` est une chaîne.

Le nombre de visites augmente chaque fois que le visiteur revient sur votre site après 30 minutes d’inactivité. L’appel de cette méthode renvoie un entier représentant le nombre de visites actuel du visiteur.

Ce plug-in définit un cookie propriétaire appelé `"s_vnc[LENGTH]"` où `[LENGTH]` est la valeur transmise à l’argument `rp`. Par exemple, `"s_vncw"`, `"s_vncm"`, ou `"s_vnc365"`. La valeur du cookie est une combinaison d’un horodatage Unix qui représente le moment où le compteur de visites se réinitialise, par exemple à la fin de la semaine, à la fin du mois ou après 365 jours d’inactivité. Il contient également le nombre de visites actuel. Ce plug-in définit un autre cookie nommé `"s_ivc"` qui est défini sur `true` et expire après 30 minutes d’inactivité.

## Exemples d’appels

### Exemple 1

Pour un visiteur qui ne s’est pas rendu sur le site au cours des 365 derniers jours, le code suivant définit s.prop1 sur la valeur 1 :

```js
s.prop1=s.getVisitNum();
```

### Exemple 2

Pour un visiteur qui revient sur le site dans les 364 jours suivant sa première visite, le code suivant définit s.prop1 sur 2 :

```js
s.prop1=s.getVisitNum(365);
```

Si ce visiteur revient sur le site dans les 364 jours suivant sa deuxième visite, le code suivant définit s.prop1 sur 3 :

```js
s.prop1=s.getVisitNum(365);
```

### Exemple 3

Pour un visiteur qui revient sur le site dans les 179 jours suivant sa première visite, le code suivant définit s.prop1 sur 2 :

```js
s.prop1=s.getVisitNum(180,false);
```

Cependant, si ce visiteur revient sur le site un ou plusieurs jours après sa deuxième visite, le code suivant définit s.prop1 sur 1 :

```js
s.prop1=s.getVisitNum(180,false);
```

Lorsque le second argument de l’appel est défini sur false, la routine qui détermine le moment où le nombre de visites doit être « réinitialisé » sur 1 s’exécute « x » nombre de jours (dans cet exemple, 365 jours) après la première visite du visiteur sur le site.

Lorsque le second argument est défini sur true (ou n’est pas du tout défini), le plug-in ne réinitialise le nombre de visites sur 1 qu’après « x » nombre de jours (encore une fois, 365 jours) d’inactivité du visiteur.

### Exemple 4

Pour tous les visiteurs qui se rendent sur le site pour la première fois pendant la semaine en cours (à compter du dimanche), le code suivant définit s.prop1 sur 1 :

```js
s.prop1=s.getVisitNum("w");
```

### Exemple 5

Pour tous les visiteurs qui se rendent sur le site pour la première fois pendant le mois en cours (à compter du premier jour de chaque mois), le code suivant définit s.prop1 sur 1 :

```js
s.prop1=s.getVisitNum("m");
```

Pour rappel, le plug-in getVisitNum ne prend pas en compte les calendriers basés sur la vente au détail (c’est-à-dire 4-5-4, 4-4-5, etc.).

### Exemple 6

Pour tous les visiteurs qui se rendent sur le site pour la première fois pendant l’année en cours (à compter du 1er janvier), le code suivant définit s.prop1 sur 1 :

```js
s.prop1=s.getVisitNum("y");
```

### Exemple 7

Si vous souhaitez effectuer le suivi du nombre de visites d’une personne au cours de la semaine, du mois et de l’année (toutes dans des variables Analytics différentes), utilisez un code qui ressemble à celui ci-dessous :

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

Dans ce cas, le plug-in crée trois cookies différents, un pour chacune des différentes périodes, afin de suivre le nombre de visites individuelles par période.

## Historique des versions

### 4.2 (19 mars 2021)

* Numéro de version Ajouté en tant que données contextuelles.

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
