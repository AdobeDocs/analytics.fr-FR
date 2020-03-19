---
title: getVisitDuration
description: Effectuez le suivi du temps passé par un sur le site jusqu’à présent.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Module externe Adobe : getVisitDuration

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getVisitDuration` module externe effectue le suivi en minutes de la durée de consultation du sur le site jusqu’à ce moment-là. Adobe recommande d’utiliser ce module externe si vous souhaitez effectuer le suivi du temps cumulé sur le site jusqu’à ce point ou pour effectuer le suivi du temps nécessaire pour effectuer un  . Ce module externe ne suit pas la durée entre les  ; si cette fonctionnalité est souhaitée, utilisez le [`getTimeBetweenEvents`](gettimebetweenevents.md) module externe.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe   une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l&#39; [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Catalog] bouton
1. Installation et publication de l’ [!UICONTROL Common Analytics Plugins] extension
1. Si vous ne l’avez pas déjà fait, créez une règle intitulée &quot;Initialiser les modules externes&quot; avec la configuration suivante :
   * Condition : Aucun
   *  : Core - Bibliothèque chargée (Haut de la page)
1. Ajouter une action à la règle ci-dessus avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser getVisitDuration
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du module externe à l’aide de l’éditeur de code personnalisé Lancer

Si vous ne souhaitez pas utiliser l’extension du module externe, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété souhaitée.
1. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous l’extension Adobe Analytics.
1. Développez l’ [!UICONTROL Configure tracking using custom code] accordéon, ce qui révèle le [!UICONTROL Open Editor] bouton.
1. Ouvrez l’éditeur de code personnalisé et collez le code du module externe fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du module externe à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre implémentation permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getVisitDuration` méthode n’utilise aucun argument. Elle renvoie l’une des valeurs suivantes :

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (où `[x]` est le nombre de minutes écoulées depuis que le a atterri sur le site)

Ce module externe crée un cookie propriétaire appelé `"s_dur"`, qui correspond au nombre de millisecondes écoulées depuis que le a atterri sur le site. Le cookie expire après 30 minutes d’inactivité.

## Exemples d’appels

### Exemple n° 1

Le code suivant...

```js
s.eVar10 = s.getVisitDuration();
```

...définit toujours eVar10 sur le nombre de minutes écoulées depuis que le a atterri sur le site

### Exemple n° 2

Le code suivant...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...utilise le plug-in in inList pour vérifier si la variable  de contient le  d’achat.  Si tel est le cas, l’eVar10 est définie sur le nombre de minutes entre le  du de la visite et le moment de l’achat.

### Exemple n° 3

Le code suivant...

```js
s.prop10 = s.getVisitDuration();
```

...définira toujours prop10 comme le nombre de minutes écoulées depuis que le a atterri sur le site.  Cela s’avère utile si le cheminement est activé pour prop10.  L’ajout de la mesure &quot;Sorties&quot; au rapport prop10 affiche un rapport granulaire et &quot;dispersion&quot; du temps qu’a pris une visite quelques minutes avant qu’un ne quitte le site.

## Historique des versions

### 2.0 (2 mai 2018)

* Version ponctuelle (réanalyse/réécriture complète du module externe).
