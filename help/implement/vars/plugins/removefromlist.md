---
title: rfl
description: Supprimez une valeur spécifique d’une chaîne délimitée par des caractères.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Module externe Adobe : rfl (Supprimer de la liste)

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `rfl` plug-in vous permet de supprimer &quot;en toute sécurité&quot; des valeurs des chaînes délimitées, telles que `events`, `products`, variables de liste, etc. Ce module externe est utile si vous souhaitez supprimer des valeurs spécifiques d’une chaîne délimitée sans vous soucier des délimiteurs. Plusieurs autres plug-ins dépendent de ce code pour s’exécuter correctement. Ce module externe n’est pas nécessaire si vous n’avez pas besoin d’exécuter une fonction spécifique sur plusieurs variables Analytics à la fois, ou si vous n’utilisez aucun module externe dépendant.

Le module externe utilise la logique suivante :

* Si la valeur que vous souhaitez supprimer existe, le plug-in conserve tous les éléments de la variable, à l’exception de la valeur à supprimer.
* Si la valeur que vous souhaitez supprimer n’existe pas, le plug-in conserve la chaîne d’origine telle quelle.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur une propriété.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Catalogue] .
1. Installation et publication de l’extension Plugins [!UICONTROL Analytics] communs
1. Si ce n’est déjà fait, créez une règle intitulée &quot;Initialiser les modules externes&quot; avec la configuration suivante :
   * Condition : Aucun
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser la demande de proposition (supprimer de la liste)
1. Enregistrez et publiez les modifications apportées à la règle.

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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `rfl` méthode utilise les arguments suivants :

* **`lv`**(obligatoire, chaîne) : Variable (ou chaîne) contenant une liste de valeurs délimitées
* **`vr`**(obligatoire, chaîne) : Valeur à supprimer de l’`lv`argument. Adobe conseille de ne pas supprimer plusieurs valeurs au cours d’un seul`rfl`appel.
* **`d1`**(facultatif, chaîne) : Délimiteur utilisé par l’`lv`argument. La valeur par défaut est une virgule (`,`).
* **`d2`**(facultatif, chaîne) : Délimiteur que vous souhaitez que la chaîne renvoyée soit utilisée. La valeur par défaut est la même que celle de l’`d1`argument.
* **`df`**(facultatif, booléen) : Si`true`, force uniquement les instances de l’`vr`argument à partir de l’`lv`argument et non de toutes les instances. La valeur par défaut est`false`définie lorsqu’elle n’est pas définie.

L’appel de cette méthode renvoie une chaîne modifiée contenant l’ `lv` argument mais sans instances (ou instances en double) de la valeur spécifiée dans l’ `vr` argument.

## Exemples d’appels

### Exemple n° 1

Si la variable...

```js
s.events = "event22,event24,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events,"event24");
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event25";
```

### Exemple n° 2

Si la variable...

```js
s.events = "event22,event24,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events,"event26");
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event24,event25";
```

Dans cet exemple, l’appel rfl n’a apporté aucune modification à s.events car s.events ne contenait pas &quot;event26&quot;.

### Exemple n° 3

Si la variable...

```js
s.events = "event22,event24,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events);
```

...la valeur finale de s.events sera :

```js
s.events = "";
```

Si l’argument lv ou vr est vide dans un appel s.rfl, le plug-in ne renvoie rien.

### Exemple n° 4

Si la variable...

```js
s.prop4 = "hello|people|today";
```

...et le code suivant s&#39;exécute...

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

...la valeur finale de s.prop4 sera toujours...

```js
s.prop4 = "hello|people|today";
```

...mais la valeur finale de s.eVar5 sera :

```js
s.eVar5 = "hello|today";
```

N’oubliez pas que le module externe renvoie uniquement une valeur ; il ne &quot;réinitialise&quot; pas en fait la variable transmise par l’argument lv.

### Exemple n° 5

Si la variable...

```js
s.prop4 = "hello|people|today";
```

...et le code suivant s&#39;exécute...

```js
s.prop4 = s.rfl(s.prop4,"people");
```

...la valeur finale de s.prop4 sera toujours...

```js
s.prop4 = "hello|people|today";
```

Veillez à définir l’argument d1 lorsque la valeur de l’argument lv contient un délimiteur différent de la valeur par défaut (c.-à-d. une virgule).

### Exemple n° 6

Si la variable...

```js
s.events = "event22,event23,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events,"EVenT23");
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event23,event25";
```

Bien que cet exemple ne soit pas pratique, il montre la nécessité de transmettre des valeurs sensibles à la casse.

### Exemple n° 7

Si la variable...

```js
s.events = "event22,event23:12345,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events,"event23");
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event25";
```

### Exemple n° 8

Si la variable...

```js
s.events = "event22,event23:12345,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events,"event23:12345");
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event23:12345,event25";
```

Lorsque vous devez supprimer un événement qui utilise la sérialisation et/ou la syntaxe numérique/monétaire, vous devez spécifier uniquement l’événement lui-même (c.-à-d. sans les valeurs de sérialisation/numérique/monétaire) dans l’appel s.rfl.

### Exemple n° 9

Si la variable...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events,"event23");
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event24,event25");
```

### Exemple n° 10

Si la variable...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event23,event24,event25");
```

### Exemple 11

Si la variable...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

...la valeur finale de s.events sera :

```js
s.events = "event22|event23|event24|event25");
```

### Exemple n° 12

Si la variable...

```js
s.events = "event22,event23,event24,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events,"event23,event24");
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event23,event24,event25";
```

La définition de plusieurs valeurs dans l’argument vr n’est pas prise en charge. La logique rfl de l’exemple ci-dessus scinde d’abord les valeurs de l’argument lv (c’est-à-dire s.events) puis tente de faire correspondre chaque valeur délimitée à la valeur complète de l’argument vr (c.-à-d. &quot;event23,event24&quot;).

### Exemple n° 13

Si la variable...

```js
s.events = "event22,event23,event24,event25";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event25");
```

Chaque valeur à supprimer de la liste doit être contenue dans son propre appel s.rfl.

### Exemple n° 14

Si la variable...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...et le code suivant s&#39;exécute...

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...la valeur finale de s.linkTrackVars sera :

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Les trois derniers arguments (c.-à-d. &quot;,&quot;,&quot;,&quot;,false) à la fin de cet appel s.rfl ne sont pas nécessaires, mais elles ne &quot;nuisent à rien&quot; en étant présentes puisqu’elles correspondent aux paramètres par défaut.

### Exemple n° 15

Si la variable...

```js
s.events = "event22,event23,event24";
```

...et le code suivant s&#39;exécute...

```js
s.rfl(s.events,"event23");
```

...la valeur finale de s.events sera toujours :

```js
s.events = "event22,event23,event24";
```

Gardez à l’esprit que le module externe renvoie uniquement une valeur ; il ne &quot;réinitialise&quot; pas en fait la variable transmise par l’argument lv.

## Historique des versions

### 2.01 (17 septembre 2019)

* Correction d’un bogue mineur pour la valeur du délimiteur par défaut.

### 2.0 (16 avril 2018)

* Publication ponctuelle (recompilée, taille de code réduite).
* Suppression du besoin du `join` module externe.

### 1.0 (18 juillet 2016)

* Version initiale.
