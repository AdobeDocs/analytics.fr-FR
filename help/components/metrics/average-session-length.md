---
title: Durée de session moyenne (mobile)
description: Durée de session moyenne de l’appareil mobile.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 29%

---

# Durée de session moyenne (mobile)

La mesure « Durée de session moyenne (mobile) » [mobile](overview.md) indique la durée moyenne de présence d’un élément de dimension donné par élément de dimension. Elle est similaire à la mesure [[!UICONTROL Temps passé par visite (secondes)]](time-spent-per-visit.md), à la différence que cette mesure utilise des composants spécifiques à SDK mobile dans le cadre de son calcul.

## Méthode de calcul de cette mesure

Cette mesure est calculée à l’aide du [&#x200B; &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)Mesures de cycle de vie`'Total Session length' / ('Launches' - 'First launches'`.
