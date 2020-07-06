---
title: getResponsiveLayout
description: Permet de déterminer la mise en page d’un site web actuellement consulté.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 100%

---


# Plug-in Adobe : getResponsiveLayout

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getResponsiveLayout` vous permet de savoir quelle version de votre site web basé sur une conception adaptée est actuellement consultée par un visiteur. Adobe recommande d’utiliser ce plug-in si votre site utilise une conception adaptée et que vous souhaitez effectuer le suivi de la version du site consultée par un visiteur. Ce plug-in n’est pas nécessaire si votre site n’utilise pas de conception adaptée.

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
   * Type d’action : initialisation de getResponsiveLayout
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
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getResponsiveLayout` utilise les arguments suivants :

* **`ppw`** (obligatoire, entier) : largeur maximale possible en pixels d’une fenêtre de navigateur avant que la page ne passe du mode portrait au mode paysage.
* **`plw`** (obligatoire, entier) : largeur maximale possible en pixels d’une fenêtre de navigateur avant que la page ne passe du mode paysage au mode tablette.
* **`tw`** (obligatoire, booléen) : largeur maximale possible en pixels d’une fenêtre de navigateur avant que la page ne passe du mode tablette au mode bureau.

L’appel de cette méthode renvoie une chaîne contenant deux parties. La première partie utilise les valeurs suivantes, selon la largeur de la fenêtre du navigateur et les arguments ci-dessus :

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (pour les sites qui n’ont pas de format portrait et paysage)
* `"tablet layout"`
* `"desktop layout"`

La deuxième partie de la chaîne renvoyée correspond aux dimensions en largeur et en hauteur du navigateur. Par exemple : `"desktop layout:1243x700"`.

## Exemples d’appels

### Exemple 1

Si…

* Votre site passe du mode portrait au mode paysage lorsque la largeur de la fenêtre du navigateur est supérieure à 500 pixels
* Votre site passe du mode paysage au mode tablette lorsque la largeur de la fenêtre du navigateur est supérieure à 700 pixels
* Votre site passe du mode tablette au mode bureau lorsque la largeur de la fenêtre du navigateur est supérieure à 1 000 pixels

…le code suivant définit eVar10 sur la disposition actuelle de la conception adaptée selon l’expérience du visiteur ainsi que la largeur et les dimensions du navigateur.

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### Exemple 2

Si…

* Votre site ne dispose que d’un mode téléphone, d’un mode tablette et d’un mode bureau
* Votre site passe du mode téléphone au mode tablette lorsque la largeur de la fenêtre du navigateur est supérieure à 500 pixels
* Votre site passe du mode tablette au mode bureau lorsque la largeur de la fenêtre du navigateur est supérieure à 1 100 pixels

…le code suivant définit eVar10 sur la disposition actuelle de la conception adaptée selon l’expérience du visiteur ainsi que la largeur et les dimensions du navigateur.

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## Historique des versions

### 1.0 (2 mai 2018)

* Version initiale.
