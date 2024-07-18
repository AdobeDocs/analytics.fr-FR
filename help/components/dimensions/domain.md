---
title: Domaine
description: L’organisation ou le FAI que le visiteur utilise pour accéder à Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 52%

---

# Domaine

La [dimension](overview.md) de &quot;domaine&quot; indique les points d’accès que les visiteurs utilisent pour accéder à Internet.

## Renseignement de cette dimension avec des données

Adobe s’associe à [Digital Element](https://www.digitalelement.com/) pour déterminer le domaine du point d’accès. Plusieurs méthodes sont utilisées pour déterminer le domaine du point d’accès, dont la recherche DNS inversée. Elle ne nécessite aucune configuration et ne comporte pas de variable à renseigner.

* Pour les implémentations AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de SDK Web, activez [!UICONTROL Recherche réseau] lors de la [ configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les exemples d’éléments de dimension incluent `comcast.net`, `rr.com`, `sbcglobal.net` et `amazonaws.com`. Ces domaines sont des points d’accès et pas nécessairement le domaine représentant un FAI ou une organisation.

Les valeurs de dimension `None` signifient que le propriétaire de l’adresse IP du point d’accès n’a pas fourni de domaine.
