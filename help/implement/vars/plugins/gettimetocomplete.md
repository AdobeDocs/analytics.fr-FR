---
title: getTimeToComplete
description: Permet de mesurer le temps nécessaire à l’accomplissement d’une tâche.
translation-type: ht
source-git-commit: 37a3a44053260d9cdb2a3797e07f6d34592abc1f
workflow-type: ht
source-wordcount: '762'
ht-degree: 100%

---


# Plug-in Adobe : getTimeToComplete

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getTimeToComplete` permet d’effectuer le suivi du temps nécessaire à un utilisateur pour terminer un processus sur un site. Le « compte à rebours » commence au moment de l’appel de l’action `start` et se termine lorsque l’action `stop` est appelée. Adobe recommande d’utiliser ce plug-in s’il existe un workflow sur le site qui dure longtemps et que vous souhaitez connaître le temps nécessaire aux visiteurs pour le terminer. Il n’est pas nécessaire d’utiliser ce plug-in si le workflow sur le site ne dure pas longtemps (moins de 3 secondes), car la granularité est réduite à la seconde complète.

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
   * Type d’action : initialisation de getTimeToComplete
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
/* Adobe Consulting Plugin: getTimeToComplete v4.0 */
function getTimeToComplete(sos,cn,exp,tp){var f=sos,m=cn,l=exp,e=tp;if("-v"===f)return{plugin:"getTimeToComplete",version:"4.0"};var k=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof k&&(k.contextData.getTimeToComplete="4.0");window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var h="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,h="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,h="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,h="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,h="seconds",d=isNaN(d)?.2:b/d);h=Math.round(c*d/b)/d+" "+h;0===h.indexOf("1 ")&&(h=h.substring(0,h.length-1));return h}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var e=window.location.hostname,h=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){h=2<h?h:2;var f=e.lastIndexOf(".");if(0<=f){for(;0<=f&&1<h;)f=e.lastIndexOf(".",f-1),h--;f=0<f?e.substring(f):e}}g=f;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""};f=f?f.toLowerCase():"start";if("stop"===f||"start"===f){m=m?m:"s_gttc";e?e="d"===e?864E5:"h"===e?36E5:"s"===e?1E3:6E4:(l=30,e=6E4);l=isNaN(l)?30:l;l*=e;k=cookieRead(m);e=new Date;if("stop"===f&&k)return l=Math.round((e.getTime()-k)/1E3),cookieWrite(m,"",0),formatTime(l);"start"!==f||k?k&&Number(k)<e.getTime()+18E5&&cookieWrite(m,k,30):(f=String(e.getTime()),e.setTime(e.getTime()+l),cookieWrite(m,f,e))}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getTimeToComplete` utilise les arguments suivants :

* **`sos`** (facultatif, chaîne) : définissez sur `"start"` le moment où vous souhaitez démarrer le minuteur. Définissez sur `"stop"` le moment où vous souhaitez arrêter le minuteur. La valeur par défaut est `"start"`.
* **`cn`** (facultatif, chaîne) : nom du cookie permettant de mémoriser l’heure de début. La valeur par défaut est `"s_gttc"`.
* **`exp`** (facultatif, entier) : nombre de jours d’expiration du cookie (et du minuteur). La valeur par défaut est `0`, ce qui représente la fin de la session de navigateur.

L’appel de cette méthode renvoie une chaîne qui contient le nombre de jours, d’heures, de minutes et/ou de secondes écoulés entre les actions `"start"` et `"stop"`.

## Exemples d’appels

### Exemple 1

Utilisez ces appels pour déterminer le temps qui sépare le moment où un visiteur commence le processus de passage en caisse et celui où il effectue un achat.

Démarrez le minuteur lorsque le visiteur passe en caisse :

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Arrêtez le minuteur lorsque le visiteur effectue l’achat et définissez prop1 sur la durée entre l’arrêt et le démarrage :

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 enregistre le temps nécessaire pour terminer le processus d’achat.

### Exemple 2

Si vous souhaitez que plusieurs minuteurs fonctionnent simultanément (pour mesurer différents processus), vous devez définir manuellement l’argument du cookie cn.  Par exemple, si vous souhaitez mesurer le temps nécessaire à la réalisation d’un achat, définissez le code suivant…

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

…mais si vous souhaitez aussi mesurer (simultanément) le temps nécessaire au remplissage d’un formulaire d’inscription, vous devez également exécuter le code suivant :

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

Dans le deuxième exemple, event1 doit saisir le début d’un processus d’inscription qui peut durer jusqu’à 7 jours, quelle qu’en soit la raison, et event2 est censé saisir la fin de l’inscription.  s.prop2 enregistre le temps nécessaire pour terminer le processus d’inscription.

## Historique des versions

### 4.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 3.1 (30 septembre 2019)

* Ajout d’une logique qui requiert une valeur « start » ou « stop » dans le premier argument.  Toutes les autres valeurs transmises empêchent l’exécution du plug-in.
* Mise à jour du plug-in `inList 2.0` vers `inList 2.1`.

### 3.0 (23 août 2018)

* Mise à jour du plug-in `formatTime v1.0` vers `formatTime v1.1`.

### 3.0 (17 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Correction de bogues mineurs.

### 2.0 (21 juin 2016)

* Suppression de la dépendance à l’égard du plug-in `p_fo`.
* Compatibilité avec le code H et AppMeasurement.
* Ajout de la journalisation de la console.
