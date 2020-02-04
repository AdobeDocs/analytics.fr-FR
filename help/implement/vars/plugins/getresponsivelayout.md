---
title: ' getResponsiveLayout'
description: Déterminer la mise en page d’un site Web actuellement consulté.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Module externe Adobe : getResponsiveLayout

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getResponsiveLayout` module vous permet de suivre la version de votre site Web réactif basé sur la conception qu’un visiteur consulte actuellement. Adobe recommande d’utiliser ce module externe si votre site utilise une conception adaptée et que vous souhaitez effectuer le suivi de la version du site consulté par un visiteur. Ce module externe n’est pas nécessaire si votre site n’utilise pas de conception adaptée.

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
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getResponsiveLayout` méthode utilise les arguments suivants :

* **`ppw`**(obligatoire, entier) : Largeur maximale de pixels qu’une fenêtre du navigateur peut avoir avant que la page ne passe d’une mise en page portrait pour smartphone à une mise en page paysage pour smartphone.
* **`plw`**(obligatoire, entier) : Largeur maximale de pixels qu’une fenêtre du navigateur peut avoir avant que la page ne passe d’une disposition paysage pour smartphone à une disposition pour tablette
* **`tw`**(obligatoire, booléen) : Largeur maximale de pixels qu’une fenêtre du navigateur peut avoir avant que la page ne passe d’une mise en page pour tablette à une mise en page pour ordinateur de bureau.

L’appel de cette méthode renvoie une chaîne contenant deux parties. La première partie utilise les valeurs suivantes, selon la largeur du navigateur et les arguments ci-dessus :

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (pour les sites qui n’ont pas de mise en page portrait et paysage)
* `"tablet layout"`
* `"desktop layout"`

La deuxième partie de la chaîne renvoyée correspond aux dimensions de largeur et de hauteur du navigateur. Par exemple : `"desktop layout:1243x700"`.

## Exemples d’appels

### Exemple n° 1

Si la variable...

* Votre site passe du mode Portrait du téléphone au mode Paysage du téléphone lorsque la largeur du navigateur est supérieure à 500 pixels
* Votre site passe du mode paysage pour smartphone au mode tablette lorsque la largeur du navigateur est supérieure à 700 pixels
* Votre site passe du mode Tablette au mode Bureau lorsque la largeur du navigateur est supérieure à 1 000 pixels

...le code suivant définit eVar10 sur la disposition de la conception adaptée actuelle comme expérience du visiteur, ainsi que la largeur et les dimensions du navigateur.

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### Exemple n° 2

Si la variable...

* Votre site ne dispose que d’un mode pour smartphone, d’un mode pour tablette et d’un mode pour ordinateur de bureau.
* Votre site passe du mode smartphone au mode tablette lorsque la largeur du navigateur est supérieure à 500 pixels
* Votre site passe du mode Tablette au mode Bureau lorsque la largeur du navigateur est supérieure à 1 100 pixels

...le code suivant définit eVar10 sur la disposition de la conception adaptée actuelle comme expérience du visiteur, ainsi que la largeur et les dimensions du navigateur.

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## Historique des versions

### 1.0 (2 mai 2018)

* Version initiale.
