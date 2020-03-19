---
title: dynamicAccountList
description: Permet de définir une logique sur la manière dont votre mise en œuvre détermine sa suite de rapports.
translation-type: ht
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# s.dynamicAccountList

> [!IMPORTANT] Les comptes dynamiques sont uniquement pris en charge à l’aide des mises en œuvre JavaScript héritées (code H). Ces variables ne sont pas prises en charge dans les bibliothèques AppMeasurement actuelles ou dans Adobe Experience Platform Launch.

La variable `s.dynamicAccountList` détermine dynamiquement la valeur de `s_account`. Si `dynamicAccountSelection` est défini sur `true`, la variable `dynamicAccountMatch` est comparée à `dynamicAccountList`. Si une correspondance est trouvée, l’identifiant de suite de rapports correspondant est utilisé.

## Syntaxe

Cette variable est une chaîne automatiquement analysée par le fichier JavaScript.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

Une entrée valide est une liste de paires rsid et valeur séparées par des points-virgules. Chaque liste contient les éléments suivants :

* Un ou plusieurs identifiants de suite de rapports (séparés par des virgules)
* Un signe égal
* Une ou plusieurs chaînes à faire correspondre (séparées par des virgules)

La chaîne accepte uniquement les caractères ASCII standard. N’incluez pas d’espaces.

## Exemples

Pour tous les exemples suivants, l’URL de la page est `https://example.com/path2/?prod_id=12345`, la variable `dynamicAccountSelection` est définie sur `true` et la variable `s_account` sur `examplersid`.

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

* Les règles répertoriées dans cette variable sont appliquées de gauche à droite. Si la variable `dynamicAccountMatch` correspond à plusieurs règles, celle qui est située le plus à gauche est utilisée pour déterminer la suite de rapports. Par conséquent, déplacez vos règles plus génériques vers la droite de la liste.
* Si aucune correspondance n’est trouvée, la suite de rapports par défaut dans `s_account` est utilisée.
* Si votre page est enregistrée sur le disque dur d’un utilisateur ou traduite au moyen d’un moteur de traduction web (c’est le cas des pages traduites par Google, par exemple), il y a de fortes chances que la sélection de comptes dynamique ne fonctionne pas.
* Les règles `dynamicAccountSelection` s’appliquent uniquement à la section de l’URL spécifiée dans `dynamicAccountMatch`.
* Utilisez le [!DNL Adobe Experience Cloud Debugger] pour tester les suites de rapports de ce type.
