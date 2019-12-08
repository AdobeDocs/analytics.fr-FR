---
description: Il est possible d’effectuer le suivi automatique des téléchargements de fichiers et des liens de sortie en fonction des paramètres définis dans le fichier AppMeasurement pour JavaScript.
keywords: Analytics Implementation
subtopic: Link tracking
title: Fonction s.tl() – Suivi des liens
topic: Developer and implementation
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fonction s.tl() – Suivi des liens

Si votre organisation préfère avoir plus de contrôle sur les liens à suivre et sur leur comportement, il est recommandé d’effectuer un suivi manuel des liens. Utilisez la fonction s.tl() pour envoyer manuellement des demandes d’image de suivi des liens avec le contenu exact souhaité. Si le suivi des liens de base est tout ce qui importe, reportez-vous à `s.trackDownloadLinks` et à `s.trackExternalLinks` sous [Variables de configuration](c-variables/configuration-variables.md). Il est impossible de suivre automatiquement des liens personnalisés.

> [!NOTE] Le code de suivi des liens est souvent très spécifique aux exigences liées à votre site et à la création de rapports. Adobe conseille d’effectuer une mise en œuvre préalable ou d’avoir recours à un conseiller en implémentation pour comprendre la manière d’utiliser cette fonctionnalité en fonction de vos besoins professionnels.

## Syntaxe et exemples

Syntaxe de base :

`s.tl(`**`this`**`,`**`linkType`**`,`**`linkName`**`,`**`variableOverrides`**`,`**`doneAction`**`);`

Exemples de base :

```HTML
<!-- Basic HTML link example-->
<a href="example.html" onClick="s.tl(this,'o','Example link');">Click here</a>
```

```JavaScript
// Basic JavaScript link example
s.tl(this,'o','Example Link');
```

### this/true (requis)

Le premier argument détermine si le navigateur attend jusqu’à 500 ms avant de quitter la page. Si une demande d’image est envoyée avant 500 ms, la page accède immédiatement au lien sur lequel l’utilisateur a cliqué.

* `this` : attendre jusqu’à 500 ms afin de laisser à AppMeasurement le temps d’envoyer une demande d’image. Valeur par défaut.
* `true` : ne pas attendre. Si le lien quitte la page, il est possible qu’une demande d’image ne soit pas envoyée.

Le délai est uniquement nécessaire dans le cas où un lien quitte la page.

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType (requis)

Le second argument a trois valeurs possibles suivant le type de lien que vous souhaitez capturer. Il détermine la dimension d’Adobe Analytics que renseigne la demande d’image.

* `d`: Téléchargements de fichiers
* `e`: Liens de sortie
* `o` : liens personnalisés

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName (requis)

Cet argument peut être toute valeur personnalisée d’une taille maximale de 100 octets. Il détermine la valeur de dimension dans les rapports.

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides (facultatif)

Permet de modifier les valeurs de variable pour un appel unique. Si vous utilisez l’argument doneAction et si vous n’avez aucun remplacement de variable, utilisez `null`.

### doneAction (facultatif)

Spécifie une action de navigation à exécuter une fois l’appel de suivi des liens terminé. Nécessite l’utilisation de `s.useForcedLinkTracking` et de `s.forcedLinkTrackingTimeout`. La variable doneAction peut être la chaîne `navigate`, auquel cas la méthode définit `document.location` sur l’attribut href de `linkObject`. La variable doneAction peut également être une fonction qui autorise une personnalisation avancée.

Si vous fournissez une valeur pour doneAction dans un événement `onClick` d’ancrage, vous devez renvoyer la valeur `false` après l’appel `s.tl` pour empêcher la navigation du navigateur par défaut.
Pour mettre en miroir le comportement par défaut et suivre l’URL spécifiée par l’attribut href, fournissez la chaîne `navigate` en tant que doneAction. Vous pouvez éventuellement fournir votre propre fonction pour gérer l’événement de navigation en la transmettant en tant que doneAction.

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## Utilisation de fonctions JavaScript avec le suivi des liens

Vous pouvez regrouper le code de suivi des liens dans une fonction JavaScript autonome définie sur la page ou dans un fichier JavaScript lié. Vous pouvez alors effectuer des appels dans la fonction onClick de chaque lien.

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

Il est possible que des liens soient comptabilisés deux fois dans les cas où ils sont normalement capturés par le suivi automatique du téléchargement de fichier ou du lien de sortie. Par exemple, si vous activez le suivi automatique des téléchargements PDF, un appel `s.tl` entraîne la double comptabilisation des téléchargements :

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
