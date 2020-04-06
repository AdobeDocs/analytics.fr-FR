---
title: Numbers Suite
description: Permet de générer et de manipuler des nombres pour les utiliser dans d’autres variables JavaScript.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : Numbers Suite

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in Numbers Suite regroupe une série de fonctions JavaScript. Il comprend les plug-ins suivants :

* **`zeroPad`** : permet d’ajouter un nombre spécifique de zéros au début d’un nombre. Ce plug-in est utile si une variable requiert un certain nombre de chiffres, par exemple si vous travaillez avec des objets Date en JavaScript et souhaitez formater le mois et le jour d’une date avec deux chiffres au lieu d’un seul. Par exemple, `01/09/2020` au lieu de `1/9/2020`.
* **`randomNumber`** : permet de générer un nombre aléatoire avec un nombre spécifique de chiffres. Ce plug-in est utile si vous déployez des balises tierces et que vous souhaitez obtenir un nombre aléatoire pour le contournement de la mémoire cache.
* **`twoDecimals`** : permet d’arrondir un nombre au centième près. Ce plug-in est utile à des fins monétaires, car il vous permet d’arrondir un nombre à une valeur monétaire valide.

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
   * Type d’action : initialisation de Numbers Suite
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
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation des plug-ins

La méthode `zeroPad` utilise les arguments suivants :

* **num** (obligatoire, entier) : nombre à remplir. La méthode arrondit la valeur de cet argument s’il contient des décimales.
* **nod** (obligatoire, entier) : nombre de chiffres dans la valeur finale renvoyée. Si le nombre à remplir contient moins de chiffres que le nombre de chiffres à rajouter, le plug-in ajoute des zéros au début de l’argument `num`.

La méthode `randomNumber` utilise les arguments suivants :

* **nod** (facultatif, entier) : nombre de chiffres dans le nombre aléatoire que vous souhaitez générer. La valeur maximale est de 17 chiffres. La valeur par défaut est de 10 chiffres.

La méthode `twoDecimals` utilise les arguments suivants :

* **val** (obligatoire, nombre) : nombre (représenté par un objet String ou Number) que vous souhaitez arrondir au centième le plus proche.

## Retours

* La méthode **zeroPad** renvoie une chaîne égale à l’argument `num`, mais avec un nombre spécifique de zéros ajoutés au début de sa valeur. Ainsi, la valeur renvoyée comporte le nombre correct de chiffres.
* La méthode **randomNumber** renvoie une chaîne égale à un nombre aléatoire avec le nombre de chiffres souhaité.
* La méthode **twoDecimals** renvoie un objet Number arrondi au centième le plus proche.

## Exemples d’appels

### Exemples avec zeroPad

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### Exemples avec randomNumber

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### Exemples avec twoDecimals

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## Historique des versions

### 1.0 (25 mai 2019)

* Version initiale.
