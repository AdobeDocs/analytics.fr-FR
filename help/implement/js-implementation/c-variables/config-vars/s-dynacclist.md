---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# s.dynamicAccountList

> [!NOTE] The  variable is not supported in Current AppMeasurement libraries. `s.dynamicAccountList`[](../../c-appmeasurement-js/appmeasure-mjs.md) It is only used in legacy AppMeasurement, such as H Code.

The `s.dynamicAccountList` variable is used to help dynamically determine a report suite to send data to. Il est utilisé conjointement avec les `dynamicAccountSelection` variables et `dynamicAccountMatch` . Les règles dans `dynamicAccountList` sont appliquées si `dynamicAccountSelection` est définie sur `true`, et elles s’appliquent à la section de l’URL spécifiée dans `dynamicAccountMatch`.

## Syntaxe et valeurs possibles

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

Une entrée valide est une liste de paires nom=valeur (règles) séparées par des points-virgules. Chaque liste contient les éléments suivants :

* One or more report suite ID's (separated by commas)
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

* Les règles répertoriées dans cette variable sont appliquées de gauche à droite. If the `dynamicAccountMatch` variable matches more than one rule, the left-most rule is used to determine the report suite. As a result, place more generic rules to the right of the list.
* If no rules match, the default report suite in `s_account` is used.
* If your page is saved to someone's hard drive or translated via a web-based translation engine (such as Google's translated pages), the dynamic account selection likely won't work.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.
* Utilisez le [!DNL Adobe Experience Cloud Debugger] pour tester la suite de rapports de destination.
