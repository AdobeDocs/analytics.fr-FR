---
title: Domaine
description: L’organisation ou le FAI que le visiteur utilise pour accéder à Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 89%

---

# Domaine

Le &quot;domaine&quot; [dimension](overview.md) indique les points d’accès que les visiteurs utilisent pour accéder à Internet.

## Renseignement de cette dimension avec des données

Adobe s’associe à [Digital Element](https://www.digitalelement.com/) pour déterminer le domaine du point d’accès. Plusieurs méthodes sont utilisées pour déterminer le domaine du point d’accès, dont la recherche DNS inversée. Elle ne nécessite aucune configuration et ne comporte pas de variable à renseigner. Elle est prête à l’emploi avec toutes les implémentations AppMeasurement.

## Éléments de dimension

Les exemples d’éléments de dimension incluent `comcast.net`, `rr.com`, `sbcglobal.net` et `amazonaws.com`. Notez que ces domaines sont des points d’accès et pas nécessairement le domaine représentant un FAI ou une organisation.

Les valeurs de dimension `None` signifient que le propriétaire de l’adresse IP du point d’accès n’a pas fourni de domaine.
