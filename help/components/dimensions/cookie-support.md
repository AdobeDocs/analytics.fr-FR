---
title: Prise en charge des cookies
description: Détermine si le navigateur prend en charge les cookies.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 92%

---

# Prise en charge des cookies

La [dimension](overview.md) « Prise en charge des cookies » indique si le navigateur prend en charge les cookies pour un accès donné. Elle est utile pour déterminer le ratio de visiteurs qui utilisent des navigateurs prenant en charge les cookies et ceux qui les désactivent intentionnellement.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données de la [`k`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement tente de définir un cookie nommé `s_cc`, puis détecte si le cookie existe. Le résultat est la valeur du paramètre de chaîne de requête `Y` (si le navigateur prend en charge les cookies et qu’ils sont activés) ou `N` (si les cookies sont désactivés dans le navigateur). Si vous utilisez AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `k` sur chaque accès avec la valeur `Y` ou `N`.

## Éléments de dimension

Les éléments de dimension comprennent `Enabled`, `Disabled` et `Unknown`.

* **`Enabled`** : le navigateur prend en charge les cookies et ils sont activés.
* **`Disabled`** : le navigateur ne prend pas en charge les cookies ou le visiteur les a désactivés.
* **`Unknown`** : AppMeasurement n’a pas pu déterminer la prise en charge des cookies. La chaîne de requête `k` n’était pas présente dans la demande d’image.
