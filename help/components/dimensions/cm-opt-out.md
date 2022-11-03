---
title: Droit d’opposition de gestion du consentement
description: Déterminer les paramètres de confidentialité auxquels un visiteur a exercé son droit d’opposition.
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 5%

---

# Droit d’opposition de gestion du consentement

La dimension &quot;Exclusion de la gestion du consentement&quot; affiche les paramètres de confidentialité qu’un visiteur a explicitement exclus. Vous pouvez utiliser cette dimension pour filtrer les données en fonction des paramètres de confidentialité ou afficher les raisons d’exclusion les plus courantes.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données des éléments suivants : [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` lorsque est défini sur `1`. If `cm.ssf` est égal à `0` ou est vide, cette variable ne fait rien.
* `contextData.['opt.dmp']` lorsque est défini sur `N`. If `opt.dmp` est égal à `Y`, la variable [Accord préalable de gestion du consentement](cm-opt-in.md) est renseignée à la place.
* `contextData.['opt.sell']` lorsque est défini sur `N`. If `opt.sell` est égal à `Y`, la variable [Accord préalable de gestion du consentement](cm-opt-in.md) est renseignée à la place.

Votre entreprise détermine la logique de mise en oeuvre de ces variables de données contextuelles. Elles ne persistent pas au-delà de l’accès sur lequel elles sont définies. Vous devez donc définir chaque variable de données contextuelles sur chaque page.

## Éléments de dimension

Les éléments de Dimension comprennent les trois valeurs suivantes :

* **`SSF`**: Le visiteur a exercé son droit d’opposition. [Transfert côté serveur](/help/admin/admin/c-server-side-forwarding/ssf.md). Cet élément de dimension est présent lorsque la variable de données contextuelles `cm.ssf` est égal à `1`. Voir [Présentation de la confidentialité des données](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) pour plus d’informations, voir le guide d’utilisation d’Audience Manager .
* **`DMP`**: Le visiteur s’est désabonné du partage sur les plateformes de gestion des données. Cet élément de dimension est présent lorsque la variable de données contextuelles `opt.dmp` est égal à `N`. L’accès n’est pas transféré vers Adobe Audience Manager.
* **`SELL`**: Le visiteur s’est désabonné du partage ou de la vente des données à des tiers. Cette dimension est présente lorsque la variable de données contextuelles `opt.sell` est égal à `N`.
