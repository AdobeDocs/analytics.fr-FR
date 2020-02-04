---
title: dynamicAccountList
description: Définissez une logique sur la manière dont votre implémentation détermine sa suite de rapports.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# s.dynamicAccountList

> [!IMPORTANT] Les comptes dynamiques sont uniquement pris en charge à l’aide des implémentations JavaScript héritées (code H). Ces variables ne sont pas prises en charge dans les bibliothèques AppMeasurement actuelles ou dans le lancement d’Adobe Experience Platform.

La `s.dynamicAccountList` variable détermine dynamiquement la valeur de `s_account`. Si `dynamicAccountSelection` est défini sur `true`, la `dynamicAccountMatch` variable est comparée à `dynamicAccountList`. Si une correspondance est trouvée, l’identifiant de suite de rapports correspondant est utilisé.

## du lien personnalisé

Cette variable est une chaîne automatiquement analysée par le fichier JavaScript.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

Une entrée valide est une liste de paires rsid et valeur séparées par des points-virgules. Chaque liste contient les éléments suivants :

* Un ou plusieurs identifiants de suite de rapports (séparés par des virgules)
* Un signe égal
* Une ou plusieurs chaînes à faire correspondre (séparées par des virgules)

Seuls les caractères ASCII standard doivent être utilisés dans la chaîne. N’incluez pas d’espaces.

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
