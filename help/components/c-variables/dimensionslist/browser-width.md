---
description: Mesure de la distance horizontale/verticale des données dans la fenêtre du navigateur uniquement. Plus spécifiquement, le navigateur
seo-description: Mesure de la distance horizontale/verticale des données dans la fenêtre du navigateur uniquement. Plus spécifiquement, le navigateur
seo-title: Largeur/hauteur du navigateur
solution: Analytics
title: Largeur/hauteur du navigateur
topic: Mesures
uuid: 1c0d3ea9-e001-4152-9bfc-8fe6406bc755
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Largeur/hauteur du navigateur

Mesure de la distance horizontale/verticale des données dans la fenêtre du navigateur uniquement. Plus spécifiquement, le navigateur

Adobe Analytics utilise la hauteur et la largeur du navigateur uniquement à partir du premier accès d’une visite. Le reste des accès n’obtient pas l’affectation pour la même visite.
The browser width/height dimensions capture similar but distinct values when compared with [mobile screen size](/help/components/c-variables/dimensionslist/reports-mobile.md#topic_D306EA4558194488AC47A45B9C570150).

Si, par exemple, vous ventilez la largeur ou la hauteur du navigateur selon la résolution de l’appareil mobile, vous devez tenir compte des distinctions ci-après :

* Les résolutions des appareils mobiles sont les valeurs physiques associées à l’appareil. Par exemple, en termes de résolution d’appareil mobile, le Galaxy S8 entrerait dans la catégorie 2 960 x 1 440. La résolution de l’appareil mobile est collectée auprès d’un service tiers, une fois l’appareil identifié.
* D’un autre côté, les valeurs de hauteur et de largeur du navigateur correspondent aux valeurs CSS (logiques) de 740 x 360. Les valeurs du navigateur dépendent des données Javascript/CSS.
* Pour consulter une brève discussion à ce sujet, suivez [ce fil](https://stackoverflow.com/questions/8785643/what-exactly-is-device-pixel-ratio).

