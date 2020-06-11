---
title: Prise en charge des cookies
description: Détermine si le navigateur prend en charge les cookies.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 1%

---


# Prise en charge des cookies

La dimension Prise en charge des cookies se rapporte si le navigateur prend en charge les cookies pour un accès donné. Il est utile de déterminer le ratio des visiteurs qui utilisent des navigateurs qui prennent en charge les cookies et de ceux qui les désactivent intentionnellement.

## Renseigner cette dimension avec des données

Cette dimension collecte les données de la chaîne [`k` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement tente de définir un cookie nommé `s_cc`, puis détecte si le cookie existe. Le résultat est la valeur du paramètre de chaîne de requête `Y` (si le navigateur prend en charge et que les cookies sont activés) ou `N` (si les cookies sont désactivés dans le navigateur). Si vous utilisez AppMeasurement (par exemple via le lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de `k` requête sur chaque accès avec la valeur `Y` ou `N`.

## Valeurs de dimension

Les valeurs de dimension incluent `Enabled`, `Disabled`et `Unknown`.

* **`Enabled`**: Le navigateur prend en charge les cookies et les active.
* **`Disabled`**: Le navigateur ne prend pas en charge les cookies ou le visiteur les a désactivés.
* **`Unknown`**: AppMeasurement n&#39;a pas pu déterminer la prise en charge des cookies. La chaîne de `k` requête n&#39;était pas présente dans la demande d&#39;image.
