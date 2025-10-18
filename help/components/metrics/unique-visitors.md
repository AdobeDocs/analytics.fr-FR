---
title: Visiteurs ou visiteuses uniques
description: Nombre d’ID de visiteur ou de visiteuse uniques.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: f26f406848ab26092738089aac64ed9b4fc08019
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 83%

---

# Visiteurs ou visiteuses uniques

La [mesure](overview.md) « Visiteurs ou visiteuses uniques » indique le nombre d’identifiants de visiteurs et visiteuses pour l’élément de dimension. Il s’agit de l’une des mesures les plus courantes utilisées pour déterminer le trafic, car elle fournit un aperçu général de la popularité d’un élément de dimension. Par exemple, un visiteur peut venir sur votre site tous les jours pendant un mois et, néanmoins, ne représenter qu’un visiteur unique.

Si vous utilisez l’[analyse entre appareils](../cda/overview.md), cette mesure est remplacée par la mesure [Appareils uniques](unique-devices.md).

## Visiteurs et visiteuses uniques par jour, par semaine, par mois, par trimestre et par an

Analysis Workspace traite les visiteurs uniques en fonction de la granularité du rapport. Par exemple, si vous utilisez la dimension [Jour](../dimensions/day.md), vous verrez les visiteurs uniques par jour pour chaque élément de dimension. Toutefois, le total du rapport indique le nombre de visiteurs uniques dédupliqué pour la période du tableau à structure libre.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’identifiants visiteur uniques pour un élément de dimension donné. Consultez [Aperçu de l’identification des visiteurs](/help/implement/id/overview.md) pour plus d’informations sur la manière dont Adobe Analytics identifie les visiteurs uniques.
