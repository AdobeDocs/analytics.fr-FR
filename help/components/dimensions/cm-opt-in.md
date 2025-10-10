---
title: Accord préalable de gestion du consentement
description: Identifiez les paramètres de confidentialité qu’un visiteur a acceptés.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 91%

---

# Accord préalable de gestion du consentement

La dimension « Accord préalable de gestion du consentement » [&#128279;](overview.md) affiche les paramètres de confidentialité qu’un visiteur a acceptés. Vous pouvez utiliser cette dimension pour filtrer les données en fonction des paramètres de confidentialité ou afficher les raisons d’accord préalable les plus courantes.

## Renseigner cette dimension avec des données

Cette dimension collecte les données des [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) suivantes :

* `contextData.['opt.dmp']` lorsqu’elle est définie sur `Y`. Si `opt.dmp` est égal à `N`, la dimension [Droit d’opposition de gestion du consentement](cm-opt-out.md) est renseignée à la place.
* `contextData.['opt.sell']` lorsqu’elle est définie sur `Y`. Si `opt.sell` est égal à `N`, la dimension [Droit d’opposition de gestion du consentement](cm-opt-out.md) est renseignée à la place.

Votre entreprise détermine la logique d’implémentation de ces variables de données contextuelles. Elles ne persistent pas au-delà de l’accès défini. Vous devez donc définir chaque variable de données contextuelles sur chaque page.

## Éléments de dimension

Les éléments de dimension comprennent les deux valeurs suivantes :

* **`DMP`** : le visiteur a accepté le partage sur les plateformes de gestion des données. Cet élément de dimension est présent lorsque la variable de données contextuelles `opt.dmp` est égale à `Y`.
* **`SELL`** : le visiteur a accepté de partager ou de vendre des données à des tiers. Cette dimension est présente lorsque la variable de données contextuelles `opt.sell` est égale à `Y`.
