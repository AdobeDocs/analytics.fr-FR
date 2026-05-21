---
title: dynamicAccountMatch
description: La variable dynamicAccountMatch détermine la valeur à examiner dans les comptes dynamiques.
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
role: Developer
TQID: https://experienceleague.adobe.com/Ag4YQOjHPMRsktGSbzpErM55lVCydDHXfNiS4HJofIU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 129
ht-degree: 93%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>Les comptes dynamiques sont uniquement pris en charge à l’aide des mises en œuvre JavaScript héritées (code H). Ces variables ne sont pas prises en charge dans les bibliothèques AppMeasurement actuelles ou par les balises dans Adobe Experience Platform.

La variable `dynamicAccountMatch` est la valeur qui examine `dynamicAccountList` et compare ses valeurs. Si `dynamicAccountSelection` n’est pas définie sur `true`, cette variable est ignorée.

Si cette variable n’est pas définie, sa valeur par défaut est `window.location.host`.

## Syntaxe

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

* Plusieurs variables `location` ne sont pas définies pour les pages enregistrées sur un disque dur (par exemple, `location.host` est vide). Veillez à ce que `s_account` contienne une suite de rapports par défaut.
* Lorsqu’une page est traduite au moyen d’un moteur de traduction web, tel que Google, la sélection de compte dynamique ne fonctionne pas comme prévu. Pour un suivi plus précis, renseignez la variable `s_account` côté serveur.
