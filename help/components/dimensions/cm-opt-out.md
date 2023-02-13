---
title: Droit d’opposition de gestion du consentement
description: Identifiez les paramètres de confidentialité auxquels un visiteur s’est opposé.
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
source-git-commit: dc9cd6bb45af0c992c37ffe20ea22eab67789ec5
workflow-type: ht
source-wordcount: '254'
ht-degree: 100%

---

# Droit d’opposition de gestion du consentement

La dimension « Droit d’opposition de gestion du consentement » affiche les paramètres de confidentialité auxquels un visiteur s’est explicitement opposé. Vous pouvez utiliser cette dimension pour filtrer les données en fonction des paramètres de confidentialité ou afficher les raisons d’opposition les plus courantes.

## Renseigner cette dimension avec des données

Cette dimension collecte les données des [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) suivantes :

* `contextData.['cm.ssf']` lorsqu’elle est définie sur `1`. Si `cm.ssf` est égal à `0` ou est vide, cette variable n’a aucun effet.
* `contextData.['opt.dmp']` lorsqu’elle est définie sur `N`. Si `opt.dmp` est égal à `Y`, la dimension [Accord préalable de gestion du consentement](cm-opt-in.md) est renseignée à la place.
* `contextData.['opt.sell']` lorsqu’elle est définie sur `N`. Si `opt.sell` est égal à `Y`, la dimension [Accord préalable de gestion du consentement](cm-opt-in.md) est renseignée à la place.

Votre entreprise détermine la logique d’implémentation de ces variables de données contextuelles. Elles ne persistent pas au-delà de l’accès défini. Vous devez donc définir chaque variable de données contextuelles sur chaque page.

## Éléments de dimension

Les éléments de dimension comprennent les trois valeurs suivantes :

* **`SSF`** : le visiteur s’est opposé au [Transfert côté serveur](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md). Cet élément de dimension est présent lorsque la variable de données contextuelles `cm.ssf` est égale à `1`. Consultez [Présentation de la confidentialité des données](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=fr) dans le guide d’utilisation d’Audience Manager pour plus d’informations. L’accès n’est pas transféré à Adobe Audience Manager.
* **`DMP`** : le visiteur s’est opposé au partage sur les plateformes de gestion des données. Cet élément de dimension est présent lorsque la variable de données contextuelles `opt.dmp` est égale à `N`. Comme dans `SSF`, l’accès n’est pas transféré à Adobe Audience Manager.
* **`SELL`** : le visiteur s’est opposé au partage ou à la vente des données à des tiers. Cette dimension est présente lorsque la variable de données contextuelles `opt.sell` est égale à `N`.
