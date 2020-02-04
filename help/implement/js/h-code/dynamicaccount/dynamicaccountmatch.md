---
title: dynamicAccountMatch
description: La variable dynamicAccountMatch détermine la valeur à examiner dans les comptes dynamiques.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountMatch

> [!IMPORTANT] Les comptes dynamiques sont uniquement pris en charge à l’aide des implémentations JavaScript héritées (code H). Ces variables ne sont pas prises en charge dans les bibliothèques AppMeasurement actuelles ou dans le lancement d’Adobe Experience Platform.

La `dynamicAccountMatch` variable est la valeur qui `dynamicAccountList` examine et compare ses valeurs. Si `dynamicAccountSelection` n’est pas définie sur `true`, cette variable est ignorée.

Si cette variable n’est pas définie, sa valeur par défaut est `window.location.host`.

## du lien personnalisé

```js
s.dynamicAccountMatch=[DOM object]
```

## Exemples

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## Remarques supplémentaires

* Plusieurs `location` variables ne sont pas définies pour les pages enregistrées sur un disque dur (par exemple, `location.host` est vide). Veillez à `s_account` contenir une suite de rapports par défaut.
* Lorsqu’une page est traduite via un moteur de traduction Web, tel que Google, la sélection de compte dynamique ne fonctionne pas comme prévu. Pour effectuer un suivi plus précis, renseignez la variable `s_account` côté serveur.
