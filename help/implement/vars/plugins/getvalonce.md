---
title: getValOnce
description: Permet d’empêcher la définition d’une variable Analytics sur la même valeur deux fois de suite.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : getValOnce

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getValOnce` empêche qu’une variable soit définie plusieurs fois sur la même valeur. Adobe recommande d’utiliser ce plug-in lorsque vous souhaitez dédupliquer les occurrences dans lesquelles un visiteur actualise une page ou consulte une page donnée à plusieurs reprises. Ce plug-in n’est pas nécessaire si la mesure « Occurrences » dans Analysis Workspace ne vous intéresse pas.

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
   * Type d’action : initialisation de getValOnce
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
/* Adobe Consulting Plugin: getValOnce v2.0 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getValOnce` utilise les arguments suivants :

* **`vtc`** (obligatoire, chaîne) : variable à vérifier et à examiner pour savoir si elle vient d’être définie sur une valeur identique.
* **`cn`** (facultatif, chaîne) : nom du cookie qui contient la valeur à vérifier. La valeur par défaut est `"s_gvo"`.
* **`et`** (facultatif, entier) : expiration du cookie en jours (ou en minutes, selon l’argument `ep`). La valeur par défaut est `0`, qui expire à la fin de la session du navigateur.
* **`ep`** (facultatif, chaîne) : ne définissez cet argument que si `et` est également défini. Définissez cet argument sur `"m"` si vous souhaitez que le délai d’expiration de l’argument `et` soit exprimé en minutes plutôt qu’en jours. La valeur par défaut est `"d"`, qui définit l’argument `et` en jours.

Si l’argument `vtc` et la valeur du cookie correspondent, cette méthode renvoie une chaîne vide. Si l’argument `vtc` et la valeur du cookie ne correspondent pas, la méthode renvoie l’argument `vtc` sous forme de chaîne.

## Exemples d’appels

### Exemple 1

Utilisez cet appel pour éviter que la même valeur soit transmise à s.campaign plusieurs fois de suite pendant les 30 prochains jours :

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

Dans l’appel ci-dessus, le plug-in va d’abord comparer la valeur déjà contenue dans le cookie s_campaign avec la valeur provenant de la variable s.campaign actuelle.   Si aucune correspondance n’est établie, le plug-in définit le cookie s_campaign sur la nouvelle valeur provenant de s.campaign, puis renvoie la nouvelle valeur.   Cette comparaison sera effectuée au cours des 30 prochains jours.

### Exemple 2

Utilisez cet appel pour éviter que la même valeur soit définie tout au long de la session :

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

Ce code empêche la même valeur d’être transmise à s.eVar2 plusieurs fois de suite au cours de la session d’un utilisateur.  Il ignore également la valeur « m » dans l’argument ep (à la fin de l’appel) puisque le délai d’expiration est défini sur 0.   Le code stocke également la valeur de comparaison dans le cookie s_ev2.

## Historique des versions

### 2.0

* Nouvelle version (recompilé, taille de code réduite).

### 1.1

* Ajout de la possibilité de choisir des minutes ou des jours pour l’expiration via le paramètre `t`.
* Correction de la portée de la variable `k` utilisée pour la limiter au plug-in uniquement. Cette modification permet d’éviter d’éventuelles interférences avec d’autres codes sur la page.
