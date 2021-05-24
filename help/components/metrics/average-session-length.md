---
title: Durée de session moyenne (mobile)
description: Durée de session moyenne de l’appareil mobile.
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '83'
ht-degree: 100%

---

# Durée de session moyenne (mobile)

La mesure « Durée de session moyenne (mobile) » indique la durée moyenne de présence d’un élément de dimension donné par élément de dimension. Elle est similaire à la mesure [Temps moyen passé sur le site](average-time-on-site.md), sauf que cette mesure utilise des composants spécifiques au SDK mobile dans le cadre de son calcul.

## Méthode de calcul de cette mesure

Cette mesure est calculée à l’aide des [mesures mobiles](https://docs.adobe.com/content/help/fr-FR/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) `'Total session length' / ('Launches' - 'First launches'`.
