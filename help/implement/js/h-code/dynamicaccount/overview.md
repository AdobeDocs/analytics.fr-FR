---
title: Présentation des comptes dynamiques
description: Découvrez le processus de sélection dynamique d’une suite de rapports à l’aide du code H.
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 100%

---

# Présentation des comptes dynamiques

>[!IMPORTANT]
>
>Les comptes dynamiques sont uniquement pris en charge à l’aide des mises en œuvre JavaScript héritées (code H). Ces variables ne sont pas prises en charge dans les bibliothèques AppMeasurement actuelles ou par les balises dans Adobe Experience Platform.

Les comptes dynamiques sont une fonction de mise en œuvre qui vous permet de déterminer la suite de rapports à utiliser en fonction des critères que vous définissez. Si votre entreprise nécessite plusieurs suites de rapports mais souhaite utiliser la même mise en œuvre entre vos sites, les comptes dynamiques constituent une bonne solution.

>[!TIP]
>
>Adobe recommande d’envoyer des données à une seule suite de rapports, puis d’utiliser des suites de rapports virtuelles pour séparer les données, si nécessaire. Pour plus d’informations, voir [Considérations relatives aux suites de rapports globales](../../../prepare/global-rs.md).

3 variables sont utilisées pour sélectionner dynamiquement une suite de rapports.

* [`dynamicAccountSelection`](dynamicaccountselection.md) : activez ou désactivez la sélection de comptes dynamiques.
* [`dynamicAccountMatch`](dynamicaccountmatch.md) : détermine la valeur à observer. Par exemple, l’URL ou une chaîne de requête.
* [`dynamicAccountList`](dynamicaccountlist.md) : compare les valeurs avec `dynamicAccountMatch` et, si une correspondance est trouvée, renseigne la variable `account`.

Si `dynamicAccountSelection = true`, la valeur `dynamicAccountMatch` est comparée à `dynamicAccountList`. Si les valeurs `dynamicAccountList` correspondent, l’identifiant de la suite de rapports est inclus dans la variable `account`.

## Suite de rapports par défaut

La variable `account` peut être définie en premier. Elle joue le rôle de valeur par défaut si les chaînes spécifiées sont introuvables. Par exemple :

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

Si `location.hostname` n’était ni `dev.example.com`, ni `example.com`, l’accès serait envoyé à `examplersiddefault`.

## Balisage multisuite

Le balisage multisuite peut être utilisé avec la sélection de compte dynamique. Par exemple :

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

Si `location.hostname` contient `example.com`, l’accès est envoyé à la fois à `examplersid1` et à `examplersid2`.
