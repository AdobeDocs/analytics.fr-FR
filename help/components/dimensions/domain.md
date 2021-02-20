---
title: Domaine
description: L’organisation ou le FAI que le visiteur utilise pour accéder à Internet.
translation-type: tm+mt
source-git-commit: c2d371cee2821360ab87240b1a81695798af4f9f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 41%

---


# Domaine

La dimension &quot;Domaine&quot; rapporte les points d&#39;accès utilisés par les visiteurs pour accéder à Internet.

## Renseignement de cette dimension avec des données

L’Adobe s’associe à [Élément numérique](https://info.digitalelement.com/fr/) pour déterminer le domaine du point d’accès. Plusieurs méthodes, y compris la recherche DNS inversée, sont utilisées pour déterminer le domaine du point d’accès. Elle ne nécessite aucune configuration et ne comporte pas de variable à renseigner. Elle est prête à l’emploi avec toutes les implémentations AppMeasurement.

## Éléments de dimension

Les exemples d’éléments de dimension incluent `comcast.net`, `rr.com`, `sbcglobal.net` et `amazonaws.com`. Notez que ces domaines sont des points d’accès et pas nécessairement le domaine représentant un fournisseur de services Internet ou une organisation.

Les valeurs de Dimension `None` signifient que le propriétaire de l&#39;adresse IP du point d&#39;accès n&#39;a pas fourni de domaine.
