---
title: Visites sur une seule page
description: Nombre de fois où l’élément de dimension Page n’a pas changé au cours d’une visite.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 62%

---


# Visites sur une seule page

*Cette page d’aide décrit le fonctionnement de la mesure « Visites de page unique ». Pour plus d’informations, consultez la dimension[Visites de page unique](../dimensions/single-page-visits.md).*

The &#39;Single page visits&#39; metric shows the number of visits where the [Page](../dimensions/page.md) dimension item contained only a single unique value for the entire visit. Cette mesure est utile pour les dimensions dans lesquelles vous souhaitez consulter des visites de courte durée, mais qui ne comportent pas de règles aussi strictes que les [rebonds](bounces.md).

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre de visites pour lesquelles l’élément de dimension &quot;Page&quot; ne contenait qu’une seule valeur unique pour la visite entière. Même si un visiteur charge à nouveau la page ou déclenche des appels de suivi des liens, il s’agit toujours d’une visite de page unique. Dès que la dimension Page est remplacée par une seconde valeur unique, la visite n’est plus considérée comme une visite de page unique.

Consultez [Accès unique](single-access.md) pour une comparaison des mesures.
