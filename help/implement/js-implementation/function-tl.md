---
description: Il est possible d’effectuer le suivi automatique des téléchargements de fichiers et des liens de sortie en fonction des paramètres définis dans le fichier AppMeasurement pour JavaScript.
keywords: Mise en œuvre d’Analytics
seo-description: Il est possible d’effectuer le suivi automatique des téléchargements de fichiers et des liens de sortie en fonction des paramètres définis dans le fichier AppMeasurement pour JavaScript.
seo-title: Fonction s.tl() – Suivi des liens
solution: Analytics
subtopic: Suivi des liens
title: Fonction s.tl() – Suivi des liens
topic: Développeur et mise en œuvre
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 1ed1c6cd3fd6d29fa156cd4b2c4bdfe9120b3c61

---


# Fonction s.tl() – Suivi des liens

Si votre entreprise préfère avoir plus de contrôle sur les liens à suivre et sur leur comportement, il est recommandé d’effectuer un suivi manuel des liens. Utilisez la fonction s.tl() pour envoyer manuellement les demandes d’image de suivi des liens avec le contenu exact souhaité. Si le suivi des liens de base est tout ce qui est nécessaire, voir `s.trackDownloadLinks` et sous Variables `s.trackExitLinks` de [configuration](c-variables/configuration-variables.md). Il est impossible de suivre automatiquement les liens personnalisés.

> [!NOTE] Le code de suivi des liens est souvent très spécifique à votre site et aux besoins de création de rapports. Adobe conseille d’effectuer une mise en oeuvre préalable ou d’avoir recours à un conseiller en implémentation pour comprendre comment utiliser cette fonctionnalité en fonction des besoins de votre entreprise.

## Syntaxe et exemples

Syntaxe de base :

`s.tl(`**`this`**`,`**`linkType`**`,`**`linkName`**`,`**`variableOverrides`**`,`**`doneAction`**`);`

Exemples de base :

```HTML
<!-- Basic HTML link example-->
<a href="example.html" onClick="s.tl(this,'o','Example link');">Click here</a>
```

```JavaScript
// Basic JavaScript link example
s.tl(this,'o','Example Link');
```

### this/true (obligatoire)

Le premier argument détermine si le navigateur attend jusqu’à 500 ms avant de quitter la page. Si une demande d’image est envoyée avant 500 ms, la page accède immédiatement au lien sur lequel l’utilisateur a cliqué.

* `this`: Patientez jusqu’à 500 ms pour laisser à AppMeasurement le temps d’envoyer une demande d’image. Valeur par défaut.
* `true`: N'attendez pas. Si le lien quitte la page, il est possible qu’une demande d’image ne soit pas envoyée.

Ce délai n’est nécessaire que lorsqu’un lien quitte la page.

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType (obligatoire)

Le deuxième argument comporte trois valeurs valides en fonction du type de lien à capturer. Il détermine la dimension que la demande d’image remplit dans Adobe Analytics.

* `d`: Téléchargements de fichiers
* `e`: Liens de sortie
* `o`: Liens personnalisés

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName (obligatoire)

Cet argument peut être n’importe quelle valeur personnalisée jusqu’à 100 octets. Il détermine la valeur de dimension dans les rapports.

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides (facultatif)

Permet de modifier les valeurs de variable pour un appel unique. Si vous utilisez l’argument doneAction et n’avez aucun remplacement de variable, utilisez `null`.

### doneAction (facultatif)

Spécifie une action de navigation à exécuter une fois l’appel de suivi des liens terminé. Nécessite l’utilisation de `s.useForcedLinkTracking` et `s.forcedLinkTrackingTimeout`. The doneAction variable can be the string `navigate`, which causes the method to set `document.location` to the href attribute of `linkObject`. La variable doneAction peut également être une fonction qui autorise une personnalisation avancée.

Si vous fournissez une valeur pour doneAction dans un événement `onClick` d’ancrage, vous devez renvoyer la valeur `false` après l’appel `s.tl` pour empêcher la navigation du navigateur par défaut.
To mirror the default behavior and follow the URL specified by the href attribute, provide a string of `navigate` as the doneAction. Vous pouvez éventuellement fournir votre propre fonction pour gérer l’événement de navigation en la transmettant en tant que doneAction.

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## Utilisation des fonctions JavaScript avec le suivi des liens

Vous pouvez consolider le code de suivi des liens dans une fonction JavaScript autonome définie sur la page ou dans un fichier JavaScript lié. Des appels peuvent alors être effectués dans la fonction onClick de chaque lien.

```JavaScript
// Set in AppMeasurement file or page code
function trackClickInteraction(name){
    s.linkTrackVars='eVar16,eVar17';
    s.eVar16 = name;
    s.eVar17 = s.pageName;
    s.tl(true,'o',name);
}
```

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

## Eviter que les liens soient comptabilisés deux fois {#section_9C3F73DE758F4727943439DED110543C}

Il est possible que les liens soient comptabilisés deux fois lorsque le lien est normalement capturé par le suivi automatique des téléchargements de fichiers ou des liens de sortie. For example, if you are tracking PDF downloads automatically, an `s.tl` call results in a duplicate download count:

```JavaScript
function trackDownload(obj) {}
    s.tl(obj,'d','PDF Document');
}
```

Pour être sûr que les liens ne sont pas comptabilisés deux fois, utilisez la fonction JavaScript modifiée suivante :

```JavaScript
function linkCode(obj) {
    var lt = obj.href != null ? s.lt(obj.href) : "";
    if (lt=="") {
        s.tl(obj,'d','PDF Document');
    }
}
```
