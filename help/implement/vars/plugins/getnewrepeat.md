---
title: getNewRepeat
description: Effectuez le suivi   des nouveaux par rapport aux récurrents.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Module externe Adobe : getNewRepeat

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getNewRepeat` module externe vous permet de déterminer si un du site est un nouveau ou un nouveau dans un délai de quelques jours. Adobe recommande d’utiliser ce module externe si vous souhaitez identifier les comme &quot;nouveaux&quot; à l’aide d’un nombre personnalisé de jours. Ce plug-in n’est pas nécessaire si les dimensions Nouveau/Répéter du dans  Espace de travail de  répondent aux besoins de votre entreprise.

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
   * Type d&#39;action : Initialiser getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getNewRepeat` méthode utilise les arguments suivants :

* **`d`** (entier, facultatif) : Nombre minimum de jours requis entre les visites qui réinitialise les sur `"New"`. Si cet argument n’est pas défini, il prend par défaut 30 jours.

Cette méthode renvoie la valeur de `"New"` si le cookie défini par le module externe n’existe pas ou a expiré. Elle renvoie la valeur de `"Repeat"` si le cookie défini par le module externe existe et la durée écoulée depuis l’accès actif et le délai défini dans le cookie est supérieur à 30 minutes. Cette méthode renvoie la même valeur pour une visite complète.

Ce plug-in utilise un cookie nommé `"s_nr[LENGTH]"` où `[LENGTH]` est égal à l’ `d` argument. Le cookie contient un horodatage Unix représentant l’heure actuelle et l’état actuel du (`"New"` ou `"Repeat"`).

## Exemples d’appels

### Exemple n° 1

Le code suivant définira s.eVar1 sur la valeur &quot;New&quot; pour les nouveaux et continuera à définir s.eVar1 sur la valeur de &quot;New&quot; (avec chaque nouvel appel) tout au long du reste de la visite du sur le site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemple n° 2

Si le revient sur le site à tout moment entre 31 minutes et 30 jours depuis le dernier appel de s.getNewRepeat(), le code suivant définit s.eVar1 sur la valeur de &quot;Repeat&quot; et continue de définir s.eVar1 sur la valeur de &quot;Repeat&quot; (avec chaque nouvel appel) tout au long du reste de la visite du sur le site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemple n° 3

Si le n&#39;est pas allé sur le site depuis au moins 30 jours depuis le dernier appel de s.getNewRepeat(), le code suivant définit s.eVar1 sur la valeur de &quot;New&quot; et continue de définir s.eVar1 sur la valeur de &quot;New&quot; (avec chaque nouvel appel) pendant le reste de la visite  du site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemple n° 4

Si le revient sur le site à tout moment entre 31 minutes et 365 jours (c.-à-d. 1 an) depuis le dernier appel de s.getNewRepeat(), le code suivant définit s.eVar1 sur la valeur de &quot;Repeat&quot; et continue de définir s.eVar1 sur la valeur de &quot;Repeat&quot; (avec chaque nouvel appel) tout le reste de la  visite du site.

```js
s.eVar1=s.getNewRepeat(365);
```

### Exemple n° 5

Si le n&#39;est pas allé sur le site depuis au moins 365 jours (c&#39;est-à-dire depuis 1 an) depuis le dernier appel de s.getNewRepeat(), le code suivant définira s.eVar1 sur la valeur de &quot;New&quot; et continuera de définir s.eVar1 sur la valeur de &quot;New&quot; (avec chaque nouvel appel) pendant le reste de la visite . le site.

```js
s.eVar1=s.getNewRepeat(365);
```

## Historique des versions

### 2.1 (30 septembre 2019)

* Réorganisation de la logique JavaScript pour réduire la taille du module externe

### 2.0 (16 avril 2018)

* Recompilé avec une taille de code inférieure
* Suppression de la capacité de nommer le cookie pour stocker les informations de visite. Le module externe nomme désormais dynamiquement le cookie en fonction de la valeur transmise à l’ `d` argument.
