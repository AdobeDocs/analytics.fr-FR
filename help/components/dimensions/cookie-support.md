---
title: Prise en charge des cookies
description: Détermine si le navigateur prend en charge les cookies.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 100%

---


# Prise en charge des cookies

La dimension « Prise en charge des cookies » indique si le navigateur prend en charge les cookies pour un accès donné. Elle est utile pour déterminer le ratio de visiteurs qui utilisent des navigateurs prenant en charge les cookies et ceux qui les désactivent intentionnellement.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données de la [`k`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement tente de définir un cookie nommé `s_cc`, puis détecte si le cookie existe. Le résultat est la valeur du paramètre de chaîne de requête `Y` (si le navigateur prend en charge les cookies et qu’ils sont activés) ou `N` (si les cookies sont désactivés dans le navigateur). Si vous utilisez AppMeasurement (par le biais d’Adobe Experience Platform Launch, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `k` sur chaque accès avec la valeur `Y` ou `N`.

## Éléments de dimension

Les éléments de dimension comprennent `Enabled`, `Disabled` et `Unknown`.

* **`Enabled`** : le navigateur prend en charge les cookies et ils sont activés.
* **`Disabled`** : le navigateur ne prend pas en charge les cookies ou le visiteur les a désactivés.
* **`Unknown`** : AppMeasurement n’a pas pu déterminer la prise en charge des cookies. La chaîne de requête `k` n’était pas présente dans la demande d’image.
