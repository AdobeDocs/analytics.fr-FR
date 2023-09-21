---
title: Visites sur une seule page (mesures)
description: Le nombre de fois que l’élément de dimension « Page » n’a pas changé au cours d’une visite.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 97%

---

# Visites de page unique

*Cette page d’aide décrit le fonctionnement de la mesure « Visites de page unique ». Pour plus d’informations, consultez la dimension [Visites de page unique](../dimensions/single-page-visits.md).*

La mesure [!UICONTROL Visites sur une seule page][](overview.md) indique le nombre de visites pour lesquelles l’élément de dimension [Page](../dimensions/page.md) ne contenait qu’une valeur unique pour l’intégralité de la visite. Cette mesure est utile pour les dimensions dans lesquelles vous souhaitez consulter des visites de courte durée, mais qui ne comportent pas de règle aussi stricte que les [[!UICONTROL Rebonds]](bounces.md).

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre de visites pour lesquelles l’élément de dimension [!UICONTROL Page] ne contenait qu’une valeur unique pour l’intégralité de la visite. Même si un visiteur charge à nouveau la page ou déclenche des appels de suivi des liens, il s’agit toujours d’une visite de page unique. Dès que la dimension Page est remplacée par une seconde valeur unique, la visite n’est plus considérée comme une visite de page unique.

Consultez [Accès unique](single-access.md) pour une comparaison des mesures.

## Compter les instances répétées

Ce paramètre indique si des instances de répétition sont comptabilisées dans les rapports. Pour plus d’informations, consultez la section [Compter les instances répétées](/help/components/metrics/count-repeat-instances.md).
