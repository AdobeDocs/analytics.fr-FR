---
title: Nombres Suite
description: Générer et manipuler des nombres pour les utiliser dans d’autres variables JavaScript.
translation-type: tm+mt
source-git-commit: cae119fab9756bd31f6d835000db0a068cb87834

---


# Module externe Adobe :Nombres Suite

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin d’optimiser l’utilisation d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

La suite Numbers est une série de fonctions JavaScript. Il comprend les plug-ins suivants :

* **`zeroPad`**: Ajoutez un nombre spécifique de zéros au début d’un nombre. Ce plug-in est utile si une variable requiert un certain nombre de chiffres, par exemple si vous travaillez avec des objets de date JavaScript et souhaitez formater un mois et un jour d’une date avec deux chiffres au lieu d’un seul chiffre. Par exemple,`01/09/2020`au lieu de`1/9/2020`.
* **`randomNumber`**: Générez un nombre aléatoire avec un nombre spécifique de chiffres. Ce plug-in est utile si vous déployez des balises tierces et souhaitez obtenir un nombre aléatoire de brouillage de cache.
* **`twoDecimals`**: Arrondissez un numéro au centième placard. Ce module externe est utile à des fins monétaires, ce qui vous permet d’arrondir un nombre à une valeur monétaire valide.

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
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation des plug-ins

La `zeroPad` méthode utilise les arguments suivants :

* **num** (obligatoire, entier) : Numéro à ajouter. La méthode arrondit la valeur de cet argument s’il contient des décimales.
* **nod** (obligatoire, entier) : Nombre de chiffres dans la valeur de retour finale. Si le nombre à insérer dans le pavé contient moins de chiffres que le nombre de chiffres à insérer dans le pavé, le plug-in ajoute des zéros au début de l’ `num` argument.

La `randomNumber` méthode utilise les arguments suivants :

* **nod** (facultatif, entier) : Nombre de chiffres dans le nombre aléatoire que vous souhaitez générer. La valeur maximale est de 17 chiffres. La valeur par défaut est 10 chiffres.

La `twoDecimals` méthode utilise les arguments suivants :

* **val** (obligatoire, nombre) : Nombre (représenté par une chaîne ou un objet numérique) que vous souhaitez arrondir au centième le plus proche.

## Retours

* La méthode **zeroPad** renvoie une chaîne égale à l’ `num` argument, mais avec un nombre spécifique de zéros ajoutés au début de sa valeur, ce qui garantit que la valeur renvoyée comporte le nombre correct de chiffres.
* La méthode **randomNumber** renvoie une chaîne égale à un nombre aléatoire avec le nombre de chiffres souhaité.
* La méthode **twoDecimals** renvoie un objet numérique arrondi au centième le plus proche.

## Exemples d’appels

### Exemples de zeroPad

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### exemples randomNumber

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### deux exemples Decimals

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## Historique des versions

### 1.0 (25 mai 2019)

* Version initiale.
