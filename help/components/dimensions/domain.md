---
title: Domaine
description: L’organisation ou le FAI que le visiteur utilise pour accéder à Internet.
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '124'
ht-degree: 100%

---

# Domaine

La dimension « Domaine » signale les points d’accès utilisés par les visiteurs pour accéder à Internet.

## Renseignement de cette dimension avec des données

Adobe s’associe à [Digital Element](https://info.digitalelement.com/fr/) pour déterminer le domaine du point d’accès. Plusieurs méthodes sont utilisées pour déterminer le domaine du point d’accès, dont la recherche DNS inversée. Elle ne nécessite aucune configuration et ne comporte pas de variable à renseigner. Elle est prête à l’emploi avec toutes les implémentations AppMeasurement.

## Éléments de dimension

Les exemples d’éléments de dimension incluent `comcast.net`, `rr.com`, `sbcglobal.net` et `amazonaws.com`. Notez que ces domaines sont des points d’accès et pas nécessairement le domaine représentant un FAI ou une organisation.

Les valeurs de dimension `None` signifient que le propriétaire de l’adresse IP du point d’accès n’a pas fourni de domaine.
