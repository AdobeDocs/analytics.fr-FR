---
title: Durée de session moyenne (mobile)
description: Durée de session moyenne de l’appareil mobile.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 26%

---

# Durée de session moyenne (mobile)

&quot;Durée de session moyenne (mobile)&quot; [metric](overview.md) indique la durée moyenne de présence d’un élément de dimension donné par élément de dimension. Elle est similaire à la variable [[!UICONTROL Durée de la visite (secondes)]](time-spent-per-visit.md) , à la différence que cette mesure utilise des composants spécifiques au SDK mobile dans le cadre de son calcul.

## Méthode de calcul de cette mesure

Cette mesure est calculée à l’aide de la variable [Mesures de cycle de vie](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
