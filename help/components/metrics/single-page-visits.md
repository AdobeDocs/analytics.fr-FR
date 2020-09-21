---
title: Visites sur une seule page
description: Le nombre de fois que l’élément de dimension « Page » n’a pas changé au cours d’une visite.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '166'
ht-degree: 100%

---


# Visites sur une seule page

*Cette page d’aide décrit le fonctionnement de la mesure « Visites de page unique ». Pour plus d’informations, consultez la dimension [Visites de page unique](../dimensions/single-page-visits.md).*

La mesure « Visites de page unique » indique le nombre de visites pour lesquelles l’élément de dimension [Page](../dimensions/page.md) ne contenait qu’une valeur unique pour l’intégralité de la visite. Cette mesure est utile pour les dimensions dans lesquelles vous souhaitez consulter des visites de courte durée, mais qui ne comportent pas de règles aussi strictes que les [rebonds](bounces.md).

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre de visites pour lesquelles l’élément de dimension « Page » ne contenait qu’une valeur unique pour l’intégralité de la visite. Même si un visiteur charge à nouveau la page ou déclenche des appels de suivi des liens, il s’agit toujours d’une visite de page unique. Dès que la dimension Page est remplacée par une seconde valeur unique, la visite n’est plus considérée comme une visite de page unique.

Consultez [Accès unique](single-access.md) pour une comparaison des mesures.
