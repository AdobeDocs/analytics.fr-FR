---
title: getVisitNum
description: Permet d’assurer le suivi du nombre de visites actuelles d’un visiteur.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : getVisitNum

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getVisitNum` renvoie le nombre de visites pour tous les visiteurs qui se rendent sur le site au cours du nombre de jours souhaité. Analysis Workspace propose une dimension « Nombre de visites » qui offre des fonctionnalités similaires. Adobe recommande d’utiliser ce plug-in si vous souhaitez avoir un meilleur contrôle sur la manière dont le nombre de visites est incrémenté. Ce plug-in n’est pas nécessaire si la dimension « Nombre de visites » intégrée dans Analysis Workspace est suffisante pour vos besoins en matière de rapports.

## Installation du plug-in à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Installation et publication de l’ [!UICONTROL Common Analytics Plugins] extension
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
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Développez l’ [!UICONTROL Configure tracking using custom code] accordéon, ce qui révèle le [!UICONTROL Open Editor] bouton.
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
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

### 4.11 (30 septembre 2019)

* Correction d’un problème en raison duquel l’argument `erp` était explicitement défini sur `false`.

### 4.1 (21 mai 2018)

* Mise à jour du plug-in `endOfDatePeriod` vers la version 1.1.

### 4.0 (17 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Suppression des arguments de cookies car le plug-in génère désormais dynamiquement des cookies en fonction de l’argument `rp`.

### 3.0 (5 juin 2016)

* Révision complète
* Combinaison de toutes les solutions précédentes disponibles dans les différentes versions du plug-in `getVisitNum`.
