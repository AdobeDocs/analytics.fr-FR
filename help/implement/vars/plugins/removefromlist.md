---
title: rfl
description: Permet de supprimer une valeur spécifique d’une chaîne délimitée par des caractères.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : rfl (Remove From List)

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `rfl` vous permet de supprimer « en toute sécurité » des valeurs de chaînes délimitées, comme [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md) et d’autres. Ce plug-in est utile si vous souhaitez supprimer des valeurs spécifiques d’une chaîne délimitée sans vous soucier des délimiteurs. Plusieurs autres plug-ins dépendent de ce code pour s’exécuter correctement. Ce plug-in n’est pas nécessaire si vous n’avez pas besoin d’exécuter une fonction spécifique sur plusieurs variables Analytics à la fois, ou si vous n’utilisez aucun plug-in dépendant.

Le plug-in utilise la logique suivante :

* Si la valeur que vous souhaitez supprimer existe, le plug-in conserve tout dans la variable, à l’exception de la valeur à supprimer.
* Si la valeur que vous souhaitez supprimer n’existe pas, le plug-in conserve la chaîne d’origine telle quelle.

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
   * Type d’action : initialisation de rfl (Remove From List)
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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `rfl` utilise les arguments suivants :

* **`lv`** (obligatoire, chaîne) : variable (ou chaîne) qui contient une liste de valeurs délimitées.
* **`vr`** (obligatoire, chaîne) : valeur à supprimer de l’argument `lv`. Adobe conseille de ne pas supprimer plusieurs valeurs au cours d’un même appel `rfl`.
* **`d1`** (facultatif, chaîne) : délimiteur utilisé par l’argument `lv`. Par défaut, il s’agit d’une virgule (`,`).
* **`d2`** (facultatif, chaîne) : délimiteur que vous souhaitez voir utilisé par la chaîne renvoyée. La valeur par défaut est la même que celle de l’argument `d1`.
* **`df`** (facultatif, booléen) : s’il est défini sur `true`, il force uniquement les instances en double de l’argument `vr` à partir de l’argument `lv` au lieu de toutes les instances. La valeur par défaut est `false` lorsqu’elle n’est pas définie.

L’appel de cette méthode renvoie une chaîne modifiée contenant l’argument `lv` mais sans aucune instance (ou instance en double) de la valeur spécifiée dans l’argument `vr`.

## Exemples d’appels

### Exemple 1

Si…

```js
s.events = "event22,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events,"event24");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event25";
```

### Exemple 2

Si…

```js
s.events = "event22,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events,"event26");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event24,event25";
```

Dans cet exemple, l’appel rfl n’a apporté aucune modification à s.events, car cette variable ne contenait pas event26.

### Exemple 3

Si…

```js
s.events = "event22,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events);
```

…alors la valeur finale de s.events est :

```js
s.events = "";
```

Si l’argument lv ou vr est vide lors d’un appel s.rfl, alors le plug-in ne renvoie rien.

### Exemple 4

Si…

```js
s.prop4 = "hello|people|today";
```

…et que le code suivant s’exécute…

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

…alors la valeur finale de s.prop4 reste…

```js
s.prop4 = "hello|people|today";
```

…mais la valeur finale de s.eVar5 est :

```js
s.eVar5 = "hello|today";
```

Pour rappel, le plug-in renvoie uniquement une valeur. Il ne « réinitialise » pas réellement la variable transmise par le biais de l’argument lv.

### Exemple 5

Si…

```js
s.prop4 = "hello|people|today";
```

…et que le code suivant s’exécute…

```js
s.prop4 = s.rfl(s.prop4,"people");
```

…alors la valeur finale de s.prop4 reste…

```js
s.prop4 = "hello|people|today";
```

Veillez à définir l’argument d1 lorsque la valeur de l’argument lv contient un délimiteur différent de celui par défaut (c’est-à-dire une virgule).

### Exemple 6

Si…

```js
s.events = "event22,event23,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events,"EVenT23");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event23,event25";
```

Bien que cet exemple ne soit pas concret, il démontre la nécessité de transmettre des valeurs sensibles à la casse.

### Exemple 7

Si…

```js
s.events = "event22,event23:12345,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events,"event23");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event25";
```

### Exemple 8

Si…

```js
s.events = "event22,event23:12345,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events,"event23:12345");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event23:12345,event25";
```

Lorsque vous devez supprimer un événement qui utilise la sérialisation et/ou la syntaxe numérique/monétaire, vous devez spécifier uniquement l’événement en lui-même (soit sans les valeurs de sérialisation/numérique/monétaire) dans l’appel s.rfl.

### Exemple 9

Si…

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events,"event23");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event24,event25");
```

### Exemple 10

Si…

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event23,event24,event25");
```

### Exemple 11

Si…

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

…alors la valeur finale de s.events est :

```js
s.events = "event22|event23|event24|event25");
```

### Exemple 12

Si…

```js
s.events = "event22,event23,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events,"event23,event24");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event23,event24,event25";
```

La définition de valeurs multiples dans l’argument vr n’est pas prise en charge. La logique rfl de l’exemple ci-dessus sépare d’abord les valeurs de l’argument lv (soit s.events) puis tente de faire correspondre chaque valeur délimitée à la valeur complète de l’argument vr (soit « event23,event24 »).

### Exemple 13

Si…

```js
s.events = "event22,event23,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event25");
```

Chaque valeur à supprimer de la liste doit être contenue dans son propre appel s.rfl.

### Exemple 14

Si…

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

…et que le code suivant s’exécute…

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

…alors la valeur finale de s.linkTrackVars est :

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Les trois derniers arguments (c’est-à-dire &quot;,&quot;,&quot;,&quot;,false) à la fin de cet appel s.rfl ne sont pas nécessaires, mais leur présence ne constitue pas un frein puisqu’ils correspondent aux paramètres par défaut.

### Exemple 15

Si…

```js
s.events = "event22,event23,event24";
```

…et que le code suivant s’exécute…

```js
s.rfl(s.events,"event23");
```

…alors la valeur finale de s.events reste :

```js
s.events = "event22,event23,event24";
```

Pour rappel, le plug-in renvoie uniquement une valeur. Il ne « réinitialise » pas réellement la variable transmise par le biais de l’argument lv.

## Historique des versions

### 2.01 (17 septembre 2019)

* Correction d’un bogue mineur pour la valeur par défaut du délimiteur.

### 2.0 (16 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Suppression de la nécessité du plug-in `join`.

### 1.0 (18 juillet 2016)

* Version initiale.
