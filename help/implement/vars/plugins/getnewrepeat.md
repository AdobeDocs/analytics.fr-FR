---
title: getNewRepeat
description: Permet de suivre l’activité des nouveaux visiteurs par rapport aux visiteurs réguliers.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : getNewRepeat

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getNewRepeat` vous permet de déterminer si un visiteur sur le site est un nouveau visiteur ou un visiteur régulier pendant une période donnée. Adobe recommande d’utiliser ce plug-in si vous souhaitez identifier les visiteurs comme « nouveaux » sur la base d’un nombre de jours personnalisé. Ce plug-in n’est pas nécessaire si le traitement des visiteurs nouveaux/réguliers dans Analysis Workspace répond aux besoins de votre entreprise.

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
   * Type d’action : initialisation de getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getNewRepeat` utilise les arguments suivants :

* **`d`** (entier, facultatif) : nombre minimum de jours requis entre les visites qui réinitialise le statut des visiteurs à `"New"`. Si cet argument n’est pas défini, la période par défaut est de 30 jours.

Cette méthode renvoie la valeur de `"New"` si le cookie défini par le plug-in n’existe pas ou a expiré. Elle renvoie la valeur de `"Repeat"` si le cookie défini par le plug-in existe et si le temps écoulé depuis l’accès actif et celui défini dans le cookie sont supérieurs à 30 minutes. Cette méthode renvoie la même valeur pour une visite complète.

Ce plug-in utilise un cookie nommé `"s_nr[LENGTH]"` où `[LENGTH]` est égal à l’argument `d`. Le cookie contient un horodatage Unix représentant l’heure actuelle et le statut actuel du visiteur (`"New"` ou `"Repeat"`).

## Exemples d’appels

### Exemple 1

Le code suivant définit s.eVar1 sur la valeur de « New » pour les nouveaux visiteurs et continue à définir s.eVar1 sur cette valeur (à chaque nouvel appel) pendant le reste de leur visite sur le site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemple 2

Si le visiteur revient sur le site à tout moment sur une période comprise entre 31 minutes et 30 jours depuis la dernière fois que s.getNewRepeat() a été appelé, le code suivant définit s.eVar1 sur la valeur de « Repeat » et continue de définir s.eVar1 sur cette valeur (à chaque nouvel appel) pendant le reste de sa visite sur le site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemple 3

Si le visiteur ne s’est pas rendu sur le site pendant au moins 30 jours depuis la dernière fois que s.getNewRepeat() a été appelé, le code suivant définit s.eVar1 sur la valeur de « New » et continue de définir s.eVar1 sur cette valeur (à chaque nouvel appel) pendant le reste de sa visite sur le site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemple 4

Si le visiteur revient sur le site à tout moment sur une période comprise entre 31 minutes et 365 jours (c’est-à-dire 1 an) depuis la dernière fois que s.getNewRepeat() a été appelé, le code suivant définit s.eVar1 sur la valeur de « Repeat » et continue de définir s.eVar1 sur cette valeur (à chaque nouvel appel) pendant le reste de sa visite sur le site.

```js
s.eVar1=s.getNewRepeat(365);
```

### Exemple 5

Si le visiteur ne s’est pas rendu sur le site pendant au moins 365 jours (c’est-à-dire 1 an) depuis la dernière fois que s.getNewRepeat() a été appelé, le code suivant définit s.eVar1 sur la valeur de « New » et continue de définir s.eVar1 sur cette valeur (à chaque nouvel appel) pendant le reste de sa visite sur le site.

```js
s.eVar1=s.getNewRepeat(365);
```

## Historique des versions

### 2.1 (30 septembre 2019)

* Réorganisation de la logique JavaScript pour réduire la taille du plug-in.

### 2.0 (16 avril 2018)

* Recompilation avec une taille de code réduite.
* Suppression de la possibilité de nommer le cookie pour stocker les informations relatives à la visite. Le plug-in nomme désormais dynamiquement le cookie en fonction de la valeur transmise à l’argument `d`.
