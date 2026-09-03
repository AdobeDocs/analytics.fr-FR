---
title: Accord préalable de gestion du consentement
description: Identifiez les paramètres de confidentialité qu’un visiteur a acceptés.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
TQID: https://experienceleague.adobe.com/hvtKcglMPFz4FbInpuSs9haS5SwGNQpVWXn12M1x658
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 90%

---

# Accord préalable de gestion du consentement

La dimension « Accord préalable de gestion du consentement » ](overview.md) affiche les paramètres de confidentialité qu’un visiteur a acceptés. [Vous pouvez utiliser cette dimension pour filtrer les données en fonction des paramètres de confidentialité ou afficher les raisons d’accord préalable les plus courantes.

## Renseigner cette dimension avec des données

Cette dimension collecte les données des [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) suivantes :

* `contextData.['opt.dmp']` lorsqu’elle est définie sur `Y`. Si `opt.dmp` est égal à `N`, la dimension [Droit d’opposition de gestion du consentement](cm-opt-out.md) est renseignée à la place.
* `contextData.['opt.sell']` lorsqu’elle est définie sur `Y`. Si `opt.sell` est égal à `N`, la dimension [Droit d’opposition de gestion du consentement](cm-opt-out.md) est renseignée à la place.

Votre entreprise détermine la logique d’implémentation de ces variables de données contextuelles. Elles ne persistent pas au-delà de l’accès défini. Vous devez donc définir chaque variable de données contextuelles sur chaque page.

## Éléments de dimension

Les éléments de dimension comprennent les deux valeurs suivantes :

* **`DMP`** : le visiteur a accepté le partage sur les plateformes de gestion des données. Cet élément de dimension est présent lorsque la variable de données contextuelles `opt.dmp` est égale à `Y`.
* **`SELL`** : le visiteur a accepté de partager ou de vendre des données à des tiers. Cette dimension est présente lorsque la variable de données contextuelles `opt.sell` est égale à `Y`.
