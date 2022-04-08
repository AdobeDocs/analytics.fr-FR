---
title: Durée de session moyenne (mobile)
description: Durée de session moyenne de l’appareil mobile.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: 7966c7d9add0011831c97fbe0dfcca2acd8afb58
workflow-type: ht
source-wordcount: '81'
ht-degree: 100%

---

# Durée de session moyenne (mobile)

La mesure « Durée de session moyenne (mobile) » indique la durée moyenne de présence d’un élément de dimension donné par élément de dimension. Elle est similaire à la mesure [Temps moyen passé sur le site](average-time-on-site.md), sauf que cette mesure utilise des composants spécifiques au SDK mobile dans le cadre de son calcul.

## Méthode de calcul de cette mesure

Cette mesure est calculée à l’aide des [mesures mobiles](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr) `'Total session length' / ('Launches' - 'First launches'`.
