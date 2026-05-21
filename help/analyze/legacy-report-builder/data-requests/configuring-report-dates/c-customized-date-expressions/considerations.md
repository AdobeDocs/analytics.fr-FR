---
description: Il convient de prendre en compte deux facteurs importants lorsque vous définissez la période à l’aide d’une Expression personnalisée
title: Considérations sur les dates personnalisées
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
feature: Report Builder
role: User, Admin
exl-id: 66b817b3-7e9e-4030-92f3-797e730f9661
TQID: https://experienceleague.adobe.com/7PLNffmZnNnQ2X0HgnqYa8R3zWQvFPMSM8sbWocmxH4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 11%

---

# Considérations sur les dates personnalisées

{{legacy-arb}}

Il convient de prendre en compte deux facteurs importants lorsque vous définissez la période à l’aide d’une expression personnalisée :

* Le jour d’exécution du rapport (ou d’actualisation des requêtes) détermine les données disponibles.
* La substitution des dates de début et de fin du rapport affecte la période couverte par le rapport.

Comme la disponibilité des données est sensible à la fois à la période du rapport et à la date à laquelle vous actualisez les requêtes dans le rapport, veillez à exécuter le rapport le jour approprié pour extraire les informations souhaitées. Les exemples ci-dessous montrent ces deux considérations.

Supposons que vous effectuiez une requête pour [!UICONTROL Pages vues] à l’aide de la granularité agrégée. En Amérique du Nord, la semaine commence le dimanche. Pour obtenir des rapports mis à jour pour la période allant du dimanche au samedi (par exemple, du 23 au 29 novembre 2008), exécutez le rapport (demandes d’actualisation) le dimanche (30 novembre) pour la semaine précédente (du 23 novembre au 29 novembre).

Utilisez cette expression personnalisée :

*De:* cw-1w *À:* cw-1d

Analyse de l’expression personnalisée lorsque la [!UICONTROL date de fin] incluse pour la requête est le 30/11 :

*De:* cw-1w

le jour de la semaine en cours commençant le dimanche 30 novembre moins sept jours = le jour de la semaine écoulée commençant le dimanche 23 novembre

*To:* cw-1d

le jour de la semaine en cours commençant le dimanche 30 novembre moins un jour = samedi 29 novembre

Une fois l’expression personnalisée mappée à la feuille de calcul, actualisez la requête en utilisant le dimanche 30 novembre 2008 comme [!UICONTROL date de fin] incluse pour la requête flottante. Les données refléteront la période d&#39;une semaine.

Si, à la place, vous actualisez l’expression et indiquez le samedi 29 novembre comme [!UICONTROL date de fin] pour la requête flottante, les données refléteront les semaines du 11/16 au 11/22. En effet, la date de référence de l’actualisation de la demande est un jour plus tôt.

Voici les différences lorsque la [!UICONTROL Date de fin] incluse pour la requête est le 29/11 :

*De:* cw-1w

le jour de la semaine en cours commençant le dimanche 23 novembre moins sept jours = le jour de la semaine écoulée commençant le dimanche 16 novembre

*To:* cw-1d

le jour de la semaine en cours commençant le dimanche 23 novembre moins un jour = samedi 22 novembre

En Europe et dans d’autres pays du monde, la semaine commence le lundi et non le dimanche. Dans ce cas, vous pouvez personnaliser le calendrier pour modifier la date de début. (Voir [Calendrier personnalisé](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md).)
