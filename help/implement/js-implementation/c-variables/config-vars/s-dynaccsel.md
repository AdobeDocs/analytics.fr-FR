---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountSelection

La variable vous permet de sélectionner dynamiquement la suite de rapports en fonction de l’URL de chaque page.

>[!NOTE]
>
>`dynamicAccountSelection` ne fonctionne pas avec le suivi personnalisé des liens.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | False |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

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

* La sélection de comptes dynamique n’est pas prise en charge par [AppMeasurement pour JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Utilisez toujours le [!DNL DigitalPulse Debugger] pour déterminer la suite de rapports qui reçoit des données de chaque page.
