---
title: Durée de session moyenne (mobile)
description: Durée de session moyenne de l’appareil mobile.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: 47d5a532505aff48d43972836c78620870bd8221
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Durée de session moyenne (mobile)

La mesure « Durée de session moyenne (mobile) » indique la durée moyenne de présence d’un élément de dimension donné par élément de dimension. Elle est similaire au [Durée de la visite [secondes]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) , à la différence que cette mesure utilise des composants spécifiques au SDK mobile dans le cadre de son calcul.

## Méthode de calcul de cette mesure

Cette mesure est calculée à l’aide des [mesures mobiles](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr) `'Total session length' / ('Launches' - 'First launches'`.
