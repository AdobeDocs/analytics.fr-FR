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


# zip

Les variables  et  sont des variables de conversion.


<!-- 

zip.xml

 -->

Ces variables sont semblables à des eVars, en ce sens qu’elles capturent des événements. Toutefois, contrairement aux eVars, elles ne sont pas persistantes. Les variables Les variables *`zip`* et *`state`* s’apparentent à des eVars qui expirent immédiatement.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 50 octets | zip | Conversion &gt; Profil du visiteur &gt; Codes postaux | "" |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. Si vous utilisez, par exemple, *`zip`* pour comparer des taux de conversion par code postal, vous devez renseigner la variable *`zip`* sur chaque page du processus de passage en caisse. Adobe conseille d’utiliser l’adresse de facturation comme source du code postal. Vous pouvez toutefois choisir d’utiliser plutôt l’adresse de livraison (à condition qu’il y ait une seule adresse de livraison pour la commande). Un site de médias peut opter pour l’utilisation de *`zip`* et *`state`* dans le cadre de l’enregistrement ou du suivi des clics publicitaires.

**Syntaxe et valeurs possibles** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

La variable *`zip`* n’impose aucune valeur, ni restriction au niveau du format. *`zip`* n’est concerné par aucune limite, à l’exception des limites standard.

**Exemples** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Paramètres de configuration** {#section_7987084EECC34DD38B643B94F82385CA}

Aucun

**Pièges, questions et conseils** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Renseignez la variable [!UICONTROL zip] sur chaque page sur laquelle un événement pertinent est déclenché (chaque page du processus de passage en caisse, par exemple).
* Les variables *`zip`* et *`state`* se comportent comme des eVars qui expirent sur la page vue.

