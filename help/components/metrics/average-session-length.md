---
title: Durée de session moyenne (mobile)
description: Durée moyenne de session du périphérique mobile.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 9%

---


# Durée de session moyenne (mobile)

La mesure Durée moyenne de session (mobile) indique la durée moyenne de présence d’un élément de dimension donné par élément de dimension. Il est similaire à la mesure Durée [moyenne sur site](average-time-on-site.md) , sauf que cette mesure utilise des composants spécifiques au SDK mobile dans le cadre de son calcul.

## Méthode de calcul de cette mesure

Cette mesure est calculée à l’aide des mesures [](https://docs.adobe.com/content/help/en/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) mobiles `'Total session length' / ('Launches' - 'First launches'`.
