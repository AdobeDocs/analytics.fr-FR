---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# state

Les variables  et  sont des variables de conversion.


<!-- 

state.xml

 -->

Ces variables sont semblables à des eVars, en ce sens qu’elles capturent des événements. Toutefois, contrairement aux eVars, elles ne sont pas persistantes. Les variables Les variables *`zip`* et *`state`* s’apparentent à des eVars qui expirent immédiatement.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 50 octets | state | Conversion &gt; Profil du visiteur &gt; État du visiteur | "" |

Étant donné que les variables *`state`* et *`zip`* expirent immédiatement, les seuls événements qui y sont associés sont ceux qui sont déclenchés sur la même page que celle où elles sont renseignées. Si vous utilisez, par exemple, *`state`* pour comparer des taux de conversion par état, vous devez renseigner la variable *`state`* sur chaque page du processus de passage en caisse. S’agissant des sites de conversion, Adobe conseille d’utiliser l’adresse de facturation comme source du code postal. Vous pouvez toutefois choisir d’utiliser plutôt l’adresse de livraison (à condition qu’il y ait une seule adresse de livraison pour la commande). Un site de médias peut opter pour l’utilisation de *`zip`* et *`state`* dans le cadre de l’enregistrement ou du suivi des clics publicitaires.

**Syntaxe et valeurs possibles** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

La variable *`state`* n’impose aucune valeur spéciale, ni restriction au niveau du format. *`state`* n’est concerné par aucune limite, à l’exception des limites standard.

**Exemples** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**Paramètres de configuration** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

Aucun

**Pièges, questions et conseils** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* Renseignez la variable *`state`* sur chaque page sur laquelle un événement pertinent est déclenché (chaque page du processus de passage en caisse, par exemple).
* Les variables *`zip`* et *`state`* se comportent comme des eVars qui expirent sur la page vue.
