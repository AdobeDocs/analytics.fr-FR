---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountList

> [!NOTE] La `s.dynamicAccountList` variable n’est pas prise en charge dans les bibliothèques [AppMeasurement](../../c-appmeasurement-js/appmeasure-mjs.md)actives. Elle est uniquement utilisée dans AppMeasurement hérité, tel que le code H.

La `s.dynamicAccountList` variable permet de déterminer de manière dynamique une suite de rapports à laquelle envoyer des données. Il est utilisé conjointement avec les `dynamicAccountSelection` variables et `dynamicAccountMatch` . The rules in `dynamicAccountList` are applied if `dynamicAccountSelection` is set to `true`, and they apply to the section of the URL specified in `dynamicAccountMatch`.

## Syntaxe et valeurs possibles

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

Une entrée valide est une liste de paires nom=valeur (règles) séparées par des points-virgules. Chaque liste contient les éléments suivants :

* Un ou plusieurs identifiants de suite de rapports (séparés par des virgules)
* Un signe égal
* Un ou plusieurs filtres d’URL (séparés par des virgules)

La chaîne accepte uniquement les caractères ASCII standard (pas d’espaces).

## Exemples

Pour tous les exemples suivants, l’URL de la page est `https://example.com/path2/?prod_id=12345`, la `dynamicAccountSelection` variable est définie sur `true`et la `s_account` variable sur `examplersid`.

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## Pièges, questions et conseils

* Les règles répertoriées dans cette variable sont appliquées de gauche à droite. If the `dynamicAccountMatch` variable matches more than one rule, the left-most rule is used to determine the report suite. Par conséquent, placez des règles plus génériques à droite de la liste.
* If no rules match, the default report suite in `s_account` is used.
* Si votre page est enregistrée sur le disque dur d’une personne ou traduite via un moteur de traduction Web (comme les pages traduites de Google), la sélection de compte dynamique ne fonctionnera probablement pas.
* Les règles `dynamicAccountSelection` s’appliquent uniquement à la section de l’URL spécifiée dans `dynamicAccountMatch`.
* Use the [!DNL Adobe Experience Cloud Debugger] to test the destination report suite.
