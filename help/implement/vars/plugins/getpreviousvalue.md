---
title: getPreviousValue
description: Permet de récupérer la dernière valeur transmise dans une variable.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 100%

---


# Plug-in Adobe : getPreviousValue

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getPreviousValue` vous permet de définir une variable sur une valeur déterminée lors d’un précédent accès. Ce plug-in n’est pas nécessaire si votre mise en œuvre contient toutes les valeurs souhaitées dans l’accès actif.

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
   * Type d’action : initialisation de getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getPreviousValue` utilise les arguments suivants :

* **`v`** (chaîne, obligatoire) : variable dont la valeur doit être transmise à la demande d’image suivante. Une variable courante utilisée est `s.pageName` pour obtenir la valeur de la page précédente.
* **`c`** (chaîne, facultatif) : nom du cookie qui stocke la valeur.  Si cet argument n’est pas défini, il prend par défaut la valeur `"s_gpv"`.

Lorsque vous appelez cette méthode, elle renvoie la valeur de la chaîne contenue dans le cookie. Le plug-in réinitialise ensuite l’expiration du cookie, et lui attribue la valeur de variable de l’argument `v`. Le cookie expire après 30 minutes d’inactivité.

## Exemples d’appels

### Exemple 1

Le code suivant…

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* Définit d’abord s.prop7 sur la valeur transmise à s.pageName dans la demande d’image précédente (c’est-à-dire la valeur stockée dans le cookie gpv_Page).
* Le code réinitialise alors le cookie gpv_Page, ce qui rend sa valeur égale à la valeur actuelle de s.pageName.
* Si s.pageName n’est pas défini au moment de l’exécution de ce code, celui-ci réinitialise l’expiration de la valeur actuelle du cookie.

### Exemple 2

Le code suivant définit s.prop7 sur la dernière valeur transmise à s.pageName, mais uniquement si event1 est également contenu dans s.events, comme déterminé par le plug-in inList, au moment où l’appel a lieu.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Exemple 3

Le code suivant définit s.prop7 sur la dernière valeur transmise à s.pageName, mais uniquement si s.pageName est actuellement défini sur la page en même temps.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Exemple 4

Le code suivant définit s.eVar10 sur la valeur transmise à s.eVar1 dans la demande d’image précédente.   La valeur précédente de eVar1 aurait été contenue dans le cookie s_gpv.  Le code définit alors le cookie s_gpv sur la valeur actuelle de s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Spécificités peu communes

Si la variable associée à l’argument v est définie sur une nouvelle valeur et que le plug-in getPreviousValue s’exécute MAIS qu’un appel au serveur Analytics n’est PAS envoyé en même temps, la nouvelle valeur de l’argument v sera toujours considérée comme la « valeur précédente » lors de la prochaine exécution du plug-in.
Supposons, par exemple, que le code suivant s’exécute sur la première page de la visite :

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Ce code produirait un appel au serveur lorsque l’argument pageName est défini sur « home » et que l’argument p7 (prop7) n’est pas défini.  Toutefois, l’appel à s.getPreviousValue stockerait la valeur de s.pageName (c’est-à-dire « home ») dans le cookie spécifié dans l’appel (soit le cookie gpv_Page).
Maintenant, supposons qu’immédiatement après, sur la même page, le code suivant s’exécute (pour une raison quelconque) :

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

Comme la fonction s.t() ne s’exécute pas dans ce bloc de code, aucune autre demande d’image ne sera créée.  Cependant, lorsque le code de la fonction s.getPreviousValue() s’exécute cette fois-ci, s.prop7 est défini sur la valeur précédente de s.pageName (soit « home »), puis stocke la nouvelle valeur de s.pageName (soit « happy value ») dans le cookie gpv_Page.
Supposons que le visiteur accède à une autre page et que le code suivant s’exécute sur cette page :

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Lorsque la fonction d’appel s.t() s’exécute, elle crée une demande d’image où s.pageName=&quot;page 2&quot; et s.prop7 est défini sur « happy value », qui était la valeur de s.pageName lorsque le dernier appel à getPreviousValue a eu lieu.   La valeur s.prop7 de « home » n’a jamais été contenue dans une demande d’image réelle, même si « home » était la première valeur transmise à s.pageName.

## Historique des versions

### v2.0 (7 octobre 2019)

* Nouvelle version (réécriture complète de la logique).
