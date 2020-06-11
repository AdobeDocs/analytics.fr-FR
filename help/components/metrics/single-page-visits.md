---
title: Visites mono-page
description: Nombre de fois où la valeur de dimension "Page" n’a pas changé au cours d’une visite.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Visites mono-page

*Cette page d’aide décrit le fonctionnement de la mesure &quot;Visites mono-page&quot;. Pour plus d’informations, voir la dimension Visites[sur une](../dimensions/single-page-visits.md)seule page.*

La mesure Visites mono-page indique le nombre de visites pour lesquelles la valeur de dimension [Page](../dimensions/page.md) ne contenait qu’une seule valeur unique pour la visite complète. Cette mesure s’avère utile dans le contexte des dimensions où vous souhaitez voir des visites courtes, mais qui ne comportent pas de règles aussi strictes que les [rebonds](bounces.md).

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre de visites pour lesquelles la valeur de dimension &quot;Page&quot; ne contenait qu’une seule valeur unique pour la visite entière. Si un visiteur recharge la page ou déclenche des appels de suivi de liens, il compte toujours comme une visite d’une seule page. Dès que la dimension Page est remplacée par une seconde valeur unique, la visite n’est plus considérée comme une visite d’une seule page.

Voir Accès [](single-access.md) unique pour une comparaison entre les mesures.
