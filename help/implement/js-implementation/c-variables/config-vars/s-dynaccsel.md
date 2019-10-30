---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.dynamicAccountSelection

La variable vous permet de sélectionner dynamiquement la suite de rapports en fonction de l’URL de chaque page.

> [!NOTE] `dynamicAccountSelection` ne fonctionne pas avec le suivi personnalisé des liens.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | False |

> [!NOTE]Les variables `dynamicAccountList` et `dynamicAccountMatch` sont ignorées si la variable `dynamicAccountSelection` n’est pas déclarée ou définie sur « False ».

## Syntaxe et valeurs possibles

```js
s.dynamicAccountSelection=[true|false]
```

« true » et « false » sont les deux seules valeurs autorisées pour *`dynamicAccountSelection`*.

## Exemples

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* La sélection de compte dynamique n’est pas prise en charge par [AppMeasurement pour JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Utilisez toujours le [!DNL DigitalPulse Debugger] pour déterminer la suite de rapports qui reçoit des données de chaque page.
