---
title: Présentation des comptes dynamiques
description: Découvrez le workflow permettant de sélectionner dynamiquement une suite de rapports à l’aide du code H.
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
role: Developer
TQID: 'https://experienceleague.adobe.com/PCeDSQpYH3wym7oG5CYbQblnXkiOQRF4YlcHU6zYfKA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '243'
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

Si `location.hostname` n’était ni `dev.example.com`, ni `example.com`, le hit serait envoyé à `examplersiddefault`.

## Balisage multisuite

Le balisage multisuite peut être utilisé avec la sélection de compte dynamique. Par exemple :

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

Si `location.hostname` contient `example.com`, le hit est envoyé à la fois à `examplersid1` et à `examplersid2`.
