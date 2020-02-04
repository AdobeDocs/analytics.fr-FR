---
title: getNewRepeat
description: Suivre l’activité des nouveaux visiteurs par rapport aux visiteurs de retour.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Module externe Adobe : getNewRepeat

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getNewRepeat` module externe vous permet de déterminer si un visiteur du site est un nouveau visiteur ou un visiteur récurrent dans un délai de plusieurs jours. Adobe recommande d’utiliser ce module externe si vous souhaitez identifier les visiteurs comme &quot;nouveaux&quot; à l’aide d’un nombre personnalisé de jours. Ce plug-in n’est pas nécessaire si les dimensions Nouveau visiteur/Répéter visiteur d’Analysis Workspace répondent aux besoins de votre entreprise.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur une propriété.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Catalogue] .
1. Installation et publication de l’extension Plugins [!UICONTROL Analytics] communs
1. Pour toute règle de lancement dans laquelle vous souhaitez utiliser le module externe, ajoutez une action avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser addProductEvar
1. Enregistrer et publier les modifications apportées à la règle

## Installation du module externe à l’aide de l’éditeur de code personnalisé Lancer

Si vous ne souhaitez pas utiliser l’extension du module externe, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété souhaitée.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez la section [!UICONTROL Configurer le suivi à l’aide de l’accordéon de code] personnalisé, qui affiche le bouton [!UICONTROL Ouvrir l’éditeur] .
1. Ouvrez l’éditeur de code personnalisé et collez le code du module externe fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du module externe à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide `s_gi`). La conservation des commentaires et des numéros de version du code dans votre implémentation permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getNewRepeat` méthode utilise les arguments suivants :

* **`d`**(entier, facultatif) : nombre minimum de jours requis entre les visites qui réinitialise les visiteurs à`"New"`. Si cet argument n’est pas défini, il prend par défaut 30 jours.

Cette méthode renvoie la valeur de `"New"` si le cookie défini par le module externe n’existe pas ou a expiré. Elle renvoie la valeur de `"Repeat"` si le cookie défini par le module externe existe et la durée écoulée depuis l’accès actif et le délai défini dans le cookie est supérieur à 30 minutes. Cette méthode renvoie la même valeur pour une visite complète.

Ce plug-in utilise un cookie nommé `"s_nr[LENGTH]"` où `[LENGTH]` est égal à l’ `d` argument. Le cookie contient un horodatage Unix représentant l’heure actuelle et l’état actuel du visiteur (`"New"` ou `"Repeat"`).

## Exemples d’appels

### Exemple n° 1

Le code suivant définit s.eVar1 sur la valeur de &quot;New&quot; pour les nouveaux visiteurs et continue à définir s.eVar1 sur la valeur de &quot;New&quot; (avec chaque nouvel appel) pendant toute la durée de la visite du visiteur sur le site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemple n° 2

Si le visiteur revient sur le site à tout moment entre 31 minutes et 30 jours depuis le dernier appel de s.getNewRepeat(), le code suivant définit s.eVar1 sur la valeur de &quot;Repeat&quot; et continue de définir s.eVar1 sur la valeur de &quot;Repeat&quot; (avec chaque nouvel appel) pendant le reste de la visite du visiteur sur le site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemple n° 3

Si le visiteur n&#39;est pas allé sur le site depuis au moins 30 jours depuis le dernier appel de s.getNewRepeat(), le code suivant définit s.eVar1 sur la valeur de &quot;New&quot; et continue de définir s.eVar1 sur la valeur de &quot;New&quot; (avec chaque nouvel appel) pendant le reste de la visite du visiteur sur le site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemple n° 4

Si le visiteur revient sur le site à tout moment entre 31 minutes et 365 jours (c&#39;est-à-dire 1 an) depuis le dernier appel de s.getNewRepeat(), le code suivant définit s.eVar1 sur la valeur de &quot;Repeat&quot; et continue de définir s.eVar1 sur la valeur de &quot;Repeat&quot; (avec chaque nouvel appel) pour le reste du visiteur. visite du site.

```js
s.eVar1=s.getNewRepeat(365);
```

### Exemple n° 5

Si le visiteur ne s&#39;est pas rendu sur le site depuis au moins 365 jours (c&#39;est-à-dire depuis 1 an) depuis le dernier appel de s.getNewRepeat(), le code suivant définit s.eVar1 sur la valeur de &quot;New&quot; et continue de définir s.eVar1 sur la valeur de &quot;New&quot; (avec chaque nouvel appel) tout au long de la visite du visiteur. le site.

```js
s.eVar1=s.getNewRepeat(365);
```

## Historique des versions

### 2.1 (30 septembre 2019)

* Réorganisation de la logique JavaScript pour réduire la taille du module externe

### 2.0 (16 avril 2018)

* Recompilé avec une taille de code inférieure
* Suppression de la capacité de nommer le cookie pour stocker les informations de visite. Le module externe nomme désormais dynamiquement le cookie en fonction de la valeur transmise à l’ `d` argument.
