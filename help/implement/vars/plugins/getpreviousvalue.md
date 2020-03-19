---
title: getPreviousValue
description: Récupère la dernière valeur transmise dans une variable.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Module externe Adobe : getPreviousValue

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getPreviousValue` module externe vous permet de définir une variable sur une valeur définie pour un accès précédent. Ce module externe n’est pas nécessaire si votre implémentation contient toutes les valeurs souhaitées dans l’accès actif.

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
   * Type d&#39;action : Initialiser getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getPreviousValue` méthode utilise les arguments suivants :

* **`v`** (chaîne, obligatoire) : Variable dont la valeur doit être transmise à la demande d’image suivante. Une variable courante utilisée est `s.pageName` de récupérer la valeur de page précédente.
* **`c`** (chaîne, facultatif) : Nom du cookie qui stocke la valeur.  Si cet argument n’est pas défini, il prend par défaut la valeur `"s_gpv"`.

Lorsque vous appelez cette méthode, elle renvoie la valeur de chaîne contenue dans le cookie. Le plug-in réinitialise ensuite l’expiration du cookie et lui affecte la valeur de variable à partir de l’ `v` argument. Le cookie expire après 30 minutes d’inactivité.

## Exemples d’appels

### Exemple n° 1

Le code suivant...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* Définit d’abord s.prop7 sur la valeur transmise à s.pageName dans la demande d’image précédente (c.-à-d. la valeur stockée dans le cookie &quot;gpv_Page&quot;).
* Le code réinitialise alors le cookie &quot;gpv_Page&quot;, ce qui le rend égal à la valeur actuelle de s.pageName.
* Si s.pageName n’est pas défini au moment de l’exécution de ce code, celui-ci réinitialise l’expiration de la valeur actuelle du cookie.

### Exemple n° 2

Le code suivant définit s.prop7 sur la dernière valeur transmise à s.pageName, mais uniquement si le 1 est également contenu dans s., comme déterminé par le module externe inList, au moment où l’appel a lieu.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Exemple n° 3

Le code suivant définit s.prop7 sur la dernière valeur transmise à s.pageName, mais uniquement si s.pageName est actuellement défini sur la page en même temps.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Exemple n° 4

Le code suivant définit s.eVar10 sur la valeur transmise à s.eVar1 dans la demande d’image précédente.   La valeur eVar1 précédente aurait été contenue dans le cookie &quot;s_gpv&quot;.  Le code définira alors le cookie &quot;s_gpv&quot; comme la valeur actuelle de s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Quirks improbables

Si la variable associée à l’argument v est définie sur une nouvelle valeur et que le plug-in getPreviousValue s’exécute MAIS qu’un appel au serveur Analytics n’est PAS envoyé en même temps, la nouvelle valeur de l’argument v sera toujours considérée comme la &quot;valeur précédente&quot; lors de la prochaine exécution du plug-in.
Supposons, par exemple, que le code suivant s’exécute sur la première page de la visite :

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Ce code produirait un appel serveur lorsque l’argument pageName est égal à &quot;home&quot; et que l’argument p7 (prop7) n’est pas défini.  Toutefois, l’appel à s.getPreviousValue stockerait la valeur de s.pageName (c.-à-d. &quot;accueil&quot;) dans le cookie spécifié dans l’appel (c’est-à-dire le cookie &quot;gpv_Page&quot;).
Supposons maintenant que, immédiatement après, sur la même page, le code suivant s’exécute (pour une raison quelconque) :

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

La fonction s.t() ne s’exécutant pas dans ce bloc de code, aucune autre demande d’image ne sera créée.  Cependant, lorsque le code de la fonction s.getPreviousValue() s’exécute cette fois, s.prop7 est défini sur la valeur précédente de s.pageName (c.-à-d. &quot;home&quot;), puis stockera la nouvelle valeur de s.pageName (c.-à-d. &quot;happy value&quot;) dans le cookie &quot;gpv_Page&quot;.
Supposons que le accède à une autre page et que le code suivant s’exécute sur cette page :

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Lorsque la fonction d’appel s.t() s’exécute, elle crée une demande d’image où s.pageName=&quot;page 2&quot; et s.prop7 est égale à &quot;heureuse value&quot;, qui était la valeur de s.pageName lorsque le dernier appel à getPreviousValue a eu lieu.   La valeur s.prop7 de &quot;home&quot; n’a jamais été contenue dans une demande d’image réelle, même si &quot;home&quot; était la première valeur transmise à s.pageName.

## Historique des versions

### v2.0 (7 octobre 2019)

* Publication ponctuelle (réécriture logique complète).
