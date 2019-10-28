---
description: La prise en charge des modules externes a été modifiée dans la nouvelle version d’AppMeasurement pour JavaScript.
keywords: Mise en œuvre d’Analytics;appmeasurement;javascript;module externe
seo-description: La prise en charge des modules externes a été modifiée dans la nouvelle version d’AppMeasurement pour JavaScript.
seo-title: Prise en charge des modules dans AppMeasurement
solution: Analytics
subtopic: AppMeasurement pour JavaScript
title: Prise en charge des modules dans AppMeasurement
topic: Développeur et mise en œuvre
uuid: e048e16b-994a-4079-bde4-3faa3df8c96d
translation-type: ht
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Prise en charge des modules dans AppMeasurement

Prise en charge des modules externes dans la version actuelle d’AppMeasurement pour JavaScript.

## Modules externes testés {#section_48415FB895E6455FAC34B0B96DE6EBE7}

Les modules externes suivants ont été testés et leur compatibilité a été vérifiée :

* [Indicateur s.abort](/help/implement/js-implementation/plugins/abort.md)
* [appendList](/help/implement/js-implementation/plugins/appendlist.md)
* [Fonction doPlugins](/help/implement/js-implementation/plugins/function-doplugins.md)
* [getAndPersistValue](/help/implement/js-implementation/plugins/getandpersistvalue.md)
* [getDaysSinceLastVisit](../../../implement/js-implementation/plugins/getdayssincelastvisit.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)
* [getLoadTime](/help/implement/js-implementation/plugins/getloadtime.md)
* [getNewRepeat](../../../implement/js-implementation/plugins/getnewrepeat.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)
* [getPageVisibility](/help/implement/js-implementation/plugins/pagevisibility.md)
* [getPercentPageViewed](/help/implement/js-implementation/plugins/getpercentpageviewed.md)
* [getPreviousValue](/help/implement/js-implementation/plugins/getpreviousvalue.md)
* [getQueryParam](/help/implement/js-implementation/plugins/getqueryparam.md)
* [getTimeParting](../../../implement/js-implementation/plugins/gettimeparting.md#concept_3746EA1D1EF746049AE84105B911F44A)
* [getValOnce](/help/implement/js-implementation/plugins/getvalonce.md).
* [getVisitNum](/help/implement/js-implementation/plugins/getvisitnum.md)
* [getVisitStart](/help/implement/js-implementation/plugins/getvisitstart.md)
* [hitGovernor](/help/implement/js-implementation/plugins/hitgovernor.md)
* [Trafic interne](/help/implement/js-implementation/plugins/internal-traffic.md)
* [performanceTiming](/help/implement/js-implementation/plugins/performancetiming.md)
* [trackTNT](/help/implement/js-implementation/plugins/tracktnt.md)

## Modules externes non testés {#section_32BA7CAB37554A278170A728F1D65CE9}

Les modules externes ci-après doivent continuer à fonctionner dans la mesure où les fonctionnalités sous-jacentes sont toujours prises en charge. Ils n’ont toutefois pas été testés, et leur compatibilité n’a pas été vérifiée. Vous devez tester ces modules externes dans votre environnement de développement avant toute migration.

* getActionDepth
* getCookiesAccepted
