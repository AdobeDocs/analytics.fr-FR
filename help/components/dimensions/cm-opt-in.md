---
title: Accord préalable de gestion du consentement
description: déterminer les paramètres de confidentialité auxquels un visiteur a donné son accord.
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 7%

---

# Accord préalable de gestion du consentement

La dimension &quot;Accord préalable de gestion du consentement&quot; affiche les paramètres de confidentialité auxquels un visiteur a donné son accord. Vous pouvez utiliser cette dimension pour filtrer les données en fonction des paramètres de confidentialité ou consulter les raisons d’inclusion les plus courantes.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données des éléments suivants : [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` lorsque est défini sur `Y`. If `opt.dmp` est égal à `N`, la variable [Exclusion de la gestion du consentement](cm-opt-out.md) est renseignée à la place.
* `contextData.['opt.sell']` lorsque est défini sur `Y`. If `opt.sell` est égal à `N`, la variable [Exclusion de la gestion du consentement](cm-opt-out.md) est renseignée à la place.

Votre entreprise détermine la logique de mise en oeuvre de ces variables de données contextuelles. Elles ne persistent pas au-delà de l’accès sur lequel elles sont définies. Vous devez donc définir chaque variable de données contextuelles sur chaque page.

## Éléments de dimension

Les éléments de Dimension comprennent les deux valeurs suivantes :

* **`DMP`**: Le visiteur a choisi de partager des données sur les plateformes de gestion des données. Cet élément de dimension est présent lorsque la variable de données contextuelles `opt.dmp` est égal à `Y`.
* **`SELL`**: Le visiteur a choisi de partager ou de vendre les données à des tiers. Cette dimension est présente lorsque la variable de données contextuelles `opt.sell` est égal à `Y`.
