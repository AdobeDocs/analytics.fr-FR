---
title: rfl
description: Permet de supprimer une valeur spécifique d’une chaîne délimitée par des caractères.
feature: Variables
exl-id: d66b757e-b39f-4b6e-9999-6fbde87505af
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 93%

---

# Plug-in Adobe : rfl (Remove From List)

{{plug-in}}

Le plug-in `rfl` vous permet de supprimer « en toute sécurité » des valeurs de chaînes délimitées, comme [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md) et d’autres. Ce plug-in est utile si vous souhaitez supprimer des valeurs spécifiques d’une chaîne délimitée sans vous soucier des délimiteurs. Plusieurs autres plug-ins dépendent de ce code pour s’exécuter correctement. Ce plug-in n’est pas nécessaire si vous n’avez pas besoin d’exécuter une fonction spécifique sur plusieurs variables Analytics à la fois, ou si vous n’utilisez aucun plug-in dépendant.

Le plug-in utilise la logique suivante :

* Si la valeur que vous souhaitez supprimer existe, le plug-in conserve tout dans la variable, à l’exception de la valeur à supprimer.
* Si la valeur que vous souhaitez supprimer n’existe pas, le plug-in conserve la chaîne d’origine telle quelle.

## Installation du module externe à l’aide du SDK Web ou de l’extension SDK Web

Ce module externe n’est pas encore pris en charge pour une utilisation dans le SDK Web.

## Installation du module externe à l’aide de l’extension Adobe Analytics

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation de rfl (Remove From List)
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension de plug-in Plugins Analytics communs, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à la [collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.1  */
function rfl(lv,vr,d1,d2,df){var b=lv,f=vr,e=d1,h=d2,g=df;if("-v"===b)return{plugin:"rfl",version:"2.1"};a:{if("undefined"!==typeof window.s_c_il){var c=0;for(var a;c<window.s_c_il.length;c++)if(a=window.s_c_il[c],a._c&&"s_c"===a._c){c=a;break a}}c=void 0}"undefined"!==typeof c&&(c.contextData.rfl="2.1");if(!b||!f)return"";c=[];a="";e=e||",";h=h||e;g=g||!1;b=b.split(e);e=b.length;for(var d=0;d<e;d++)-1<b[d].indexOf(":")&&(a=b[d].split(":"),a[1]=a[0]+":"+a[1],b[d]=a[0]),-1<b[d].indexOf("=")&&(a=b[d].split("="),a[1]=a[0]+"="+a[1],b[d]=a[0]),b[d]!==f&&a?c.push(a[1]):b[d]!==f?c.push(b[d]):b[d]===f&&g&&(a?c.push(a[1]):c.push(b[d]),g=!1),a="";return c.join(h)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `rfl` utilise les arguments suivants :

* **`lv`** (obligatoire, chaîne) : variable (ou chaîne) qui contient une liste de valeurs délimitées.
* **`vr`** (obligatoire, chaîne) : valeur à supprimer de l’argument `lv`. Adobe conseille de ne pas supprimer plusieurs valeurs au cours d’un même appel `rfl`.
* **`d1`** (facultatif, chaîne) : délimiteur utilisé par l’argument `lv`. Par défaut, il s’agit d’une virgule (`,`).
* **`d2`** (facultatif, chaîne) : délimiteur que vous souhaitez voir utilisé par la chaîne renvoyée. La valeur par défaut est la même que celle de l’argument `d1`.
* **`df`** (facultatif, booléen) : s’il est défini sur `true`, il force uniquement les instances en double de l’argument `vr` à partir de l’argument `lv` au lieu de toutes les instances. La valeur par défaut est `false` lorsqu’elle n’est pas définie.

Lʼappel de cette fonction renvoie une chaîne modifiée contenant lʼargument `lv`, mais sans aucune instance (ou instance en double) de la valeur spécifiée dans lʼargument `vr`.

## Exemples d’appels

### Exemple 1

Si…

```js
s.events = "event22,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = rfl(s.events,"event24");
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
s.events = rfl(s.events,"event26");
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
s.events = rfl(s.events);
```

…alors la valeur finale de s.events est :

```js
s.events = "";
```

Si lʼargument `lv` ou `vr` est vide lors dʼun appel `rfl`, alors le plug-in ne renvoie rien.

### Exemple 4

Si…

```js
s.prop4 = "hello|people|today";
```

…et que le code suivant s’exécute…

```js
s.eVar5 = rfl(s.prop4,"people","|");
```

…alors la valeur finale de s.prop4 reste…

```js
s.prop4 = "hello|people|today";
```

…mais la valeur finale de s.eVar5 est :

```js
s.eVar5 = "hello|today";
```

Pour rappel, le plug-in renvoie uniquement une valeur. Il ne « réinitialise » pas réellement la variable transmise par le biais de lʼargument `lv`.

### Exemple 5

Si…

```js
s.prop4 = "hello|people|today";
```

…et que le code suivant s’exécute…

```js
s.prop4 = rfl(s.prop4,"people");
```

…alors la valeur finale de s.prop4 reste…

```js
s.prop4 = "hello|people|today";
```

Veillez à définir lʼargument `d1` lorsque la valeur de lʼargument `lv` contient un délimiteur différent de celui par défaut (cʼest-à-dire une virgule).

### Exemple 6

Si…

```js
s.events = "event22,event23,event25";
```

…et que le code suivant s’exécute…

```js
s.events = rfl(s.events,"EVenT23");
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
s.events = rfl(s.events,"event23");
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
s.events = rfl(s.events,"event23:12345");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event23:12345,event25";
```

Lorsque vous devez supprimer un événement qui utilise la sérialisation et/ou la syntaxe numérique/monétaire, vous devez spécifier uniquement lʼévénement en lui-même (soit sans les valeurs de sérialisation/numérique/monétaire) dans lʼappel `rfl`.

### Exemple 9

Si…

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = rfl(s.events,"event23");
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
s.events = rfl(s.events,"event23", "", "",true);
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
s.events = rfl(s.events,"event23", "", "|",true);
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
s.events = rfl(s.events,"event23,event24");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event23,event24,event25";
```

La définition de valeurs multiples dans lʼargument `vr` nʼest pas prise en charge. La logique `rfl` de lʼexemple ci-dessus sépare dʼabord les valeurs de lʼargument `lv` (soit s.events), puis tente de faire correspondre chaque valeur délimitée à la valeur complète de lʼargument `vr` (soit `"event23,event24"`).

### Exemple 13

Si…

```js
s.events = "event22,event23,event24,event25";
```

…et que le code suivant s’exécute…

```js
s.events = rfl(s.events,"event23");
s.events = rfl(s.events,"event24");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event25");
```

Chaque valeur à supprimer de la liste doit être contenue dans son propre appel `rfl`.

### Exemple 14

Si…

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

…et que le code suivant s’exécute…

```js
s.linkTrackVars = rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

…alors la valeur finale de s.linkTrackVars est :

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Les trois derniers arguments (cʼest-à-dire &quot;,&quot;,&quot;,&quot;,false) à la fin de cet appel `rfl` ne sont pas nécessaires, mais leur présence ne constitue pas un frein puisquʼils correspondent aux paramètres par défaut.

### Exemple 15

Si…

```js
s.events = "event22,event23,event24";
```

…et que le code suivant s’exécute…

```js
rfl(s.events,"event23");
```

…alors la valeur finale de s.events reste :

```js
s.events = "event22,event23,event24";
```

Pour rappel, le plug-in renvoie uniquement une valeur. Il ne « réinitialise » pas réellement la variable transmise par le biais de lʼargument `lv`.

## Historique des versions

### 2.1 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 2.01 (17 septembre 2019)

* Correction d’un bogue mineur pour la valeur par défaut du délimiteur.

### 2.0 (16 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Suppression de la nécessité du plug-in `join`.

### 1.0 (18 juillet 2016)

* Version initiale.
