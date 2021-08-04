---
title: Visites sur une seule page
description: Le nombre de fois que l’élément de dimension « Page » n’a pas changé au cours d’une visite.
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 98463103e6e2ba19d11629d40dacc0c02f5b33c9
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 57%

---

# Visites sur une seule page

*Cette page d’aide décrit le fonctionnement de la mesure « Visites de page unique ». Pour plus d’informations, consultez la dimension [Visites de page unique](../dimensions/single-page-visits.md).*

La mesure [!UICONTROL Visites de page unique] indique le nombre de visites pour lesquelles l’élément de dimension [Page](../dimensions/page.md) ne contenait qu’une valeur unique pour l’intégralité de la visite. Cette mesure s’avère utile dans le contexte de dimensions dans lesquelles vous souhaitez afficher des visites courtes, mais qui ne sont pas aussi strictes que le font [[!UICONTROL Bounces]](bounces.md).

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre de visites pour lesquelles l’élément de dimension [!UICONTROL Page] ne contenait qu’une valeur unique pour l’intégralité de la visite. Même si un visiteur charge à nouveau la page ou déclenche des appels de suivi des liens, il s’agit toujours d’une visite de page unique. Dès que la dimension Page est remplacée par une seconde valeur unique, la visite n’est plus considérée comme une visite de page unique.

Consultez [Accès unique](single-access.md) pour une comparaison des mesures.

## Compter les instances répétées

Ce paramètre indique si des instances de répétition sont comptabilisées dans les rapports. Pour plus d’informations, voir [Compter les instances de répétition](/help/components/metrics/count-repeat-instances.md).