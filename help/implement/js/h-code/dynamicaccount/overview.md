---
title: Présentation des comptes dynamiques
description: Découvrez le processus de sélection dynamique d’une suite de rapports à l’aide du code H.
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# Présentation des comptes dynamiques

> [!IMPORTANT] Les comptes dynamiques sont uniquement pris en charge à l’aide des implémentations JavaScript héritées (code H). Ces variables ne sont pas prises en charge dans les bibliothèques AppMeasurement actuelles ou dans le lancement d’Adobe Experience Platform.

Les comptes dynamiques sont une fonction d’implémentation qui vous permet de déterminer la suite de rapports à utiliser en fonction des critères que vous définissez. Si votre entreprise nécessite plusieurs suites de rapports mais souhaite utiliser la même mise en oeuvre entre vos sites, les comptes dynamiques constituent une bonne solution.

> [!TIP] Adobe recommande d’envoyer des données à une seule suite de rapports, puis d’utiliser des suites de rapports virtuelles pour séparer les données, si nécessaire. Pour plus d’informations, voir Considérations relatives [aux suites de rapports](../../../prepare/global-rs.md) globales.

3 variables sont utilisées pour sélectionner dynamiquement une suite de rapports.

* [`dynamicAccountSelection`](dynamicaccountselection.md): Activez ou désactivez la sélection de comptes dynamique.
* [`dynamicAccountMatch`](dynamicaccountmatch.md): Détermine la valeur à observer. Par exemple, l’URL ou une chaîne de requête.
* [`dynamicAccountList`](dynamicaccountlist.md): Compare les valeurs avec `dynamicAccountMatch`et, si une correspondance est trouvée, renseigne la `account` variable.

Si `dynamicAccountSelection = true`, la valeur `dynamicAccountMatch` est comparée à `dynamicAccountList`. Si les valeurs `dynamicAccountList` correspondent, l’identifiant de la suite de rapports est inclus dans la `account` variable.

## Suite de rapports par défaut

La variable `account` peut être définie en premier. Elle joue le rôle de valeur par défaut si les chaînes spécifiées sont introuvables. Par exemple :

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

Si `location.hostname` n’était ni `dev.example.com` , ni `example.com`, l’accès serait envoyé à `examplersiddefault`.

## Marquage multisuite

Le balisage multi-suite peut être utilisé avec la sélection de compte dynamique. Par exemple :

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

Si `location.hostname` contient `example.com`, l’accès est envoyé à la fois `examplersid1` et `examplersid2`.
