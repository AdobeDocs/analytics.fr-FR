---
title: getVisitDuration
description: Permet d’effectuer le suivi du temps passé par un visiteur sur le site jusqu’à présent.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : getVisitDuration

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getVisitDuration` effectue le suivi en minutes du temps de consultation du site par le visiteur jusqu’à ce moment-là. Adobe recommande d’utiliser ce plug-in si vous souhaitez effectuer le suivi du temps cumulé sur le site jusqu’à ce moment-là ou pour suivre le temps nécessaire à la réalisation d’une activité. Ce plug-in ne permet pas de suivre le temps écoulé entre deux événements. Si vous recherchez cette fonctionnalité, utilisez le plug-in [`getTimeBetweenEvents`](gettimebetweenevents.md).

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
   * Type d’action : initialisation de getVisitDuration
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
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getVisitDuration` n’utilise aucun argument. Elle renvoie l’une des valeurs suivantes :

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (où `[x]` est le nombre de minutes écoulées depuis que le visiteur a accédé au site)

Ce plug-in crée un cookie propriétaire appelé `"s_dur"`, qui correspond au nombre de millisecondes écoulées depuis l’arrivée du visiteur sur le site. Le cookie expire après 30 minutes d’inactivité.

## Exemples d’appels

### Exemple 1

Le code suivant…

```js
s.eVar10 = s.getVisitDuration();
```

…définit toujours eVar10 sur le nombre de minutes écoulées depuis l’arrivée du visiteur sur le site.

### Exemple 2

Le code suivant…

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

…utilise le plug-in inList pour vérifier si la variable events contient l’événement d’achat.  Dans ce cas, eVar10 est défini sur le nombre de minutes entre l’arrivée du visiteur sur le site et le moment de l’achat.

### Exemple 3

Le code suivant…

```js
s.prop10 = s.getVisitDuration();
```

…définit toujours prop10 sur le nombre de minutes écoulées depuis l’arrivée du visiteur sur le site.  Cela s’avère utile si le cheminement est activé pour prop10.  En ajoutant la mesure « exits » au rapport prop10, vous obtenez un rapport granulaire, sous forme de graphique de dispersion, indiquant le temps de visite en minutes avant qu’un visiteur ne quitte le site.

## Historique des versions

### 2.0 (2 mai 2018)

* Nouvelle version (réanalyse/réécriture complète du plug-in).
