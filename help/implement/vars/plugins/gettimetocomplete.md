---
title: getTimeToComplete
description: Permet de mesurer le temps nécessaire à l’accomplissement d’une tâche.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : getTimeToComplete

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
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
