---
description: 'Il convient de prendre en compte deux facteurs importants lorsque vous définissez la période à l’aide d’une Expression personnalisée '
title: Considérations sur les dates personnalisées
topic: Report builder
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Considérations sur les dates personnalisées

Il convient de prendre en compte deux facteurs importants lorsque vous définissez la période à l’aide d’une expression personnalisée :

* Le jour d’exécution du rapport (à partir de) (ou de l’actualisation des requêtes) détermine quelles données sont disponibles.
* La substitution des dates de début et de fin du rapport affecte la période couverte par le rapport.

La disponibilité des données dépend de la période du rapport et de la date à laquelle vous actualisez les requêtes du rapport. Veillez, par conséquent, à exécuter le rapport le jour approprié afin d’extraire les informations souhaitées. Les exemples ci-dessous illustrent ces deux considérations.

Assume you make a request for [!UICONTROL Page Views] using Aggregated granularity. En Amérique du Nord, la semaine commence le dimanche. Afin d’obtenir des rapports à jour pour la période du dimanche au samedi (par exemple, du 23 novembre au 29 novembre 2008), exécutez le rapport (actualisez les requêtes) le dimanche (30 novembre) pour la semaine précédente (23/11 au 29/11).

Utilisez cette expression personnalisée :

*Du :* cw-1w *Au :* cw-1d

An analysis of the customize expression when the inclusive [!UICONTROL End Date] for the request is 11/30:

*Du :* cw-1w

jour de la semaine en cours commençant le dimanche 30 novembre moins sept jours = jour de la semaine passée commençant le dimanche 23 novembre

*Au :* cw-1d

jour de la semaine en cours commençant le dimanche 30 novembre moins un jour = samedi 29 novembre

After the customized expression is mapped to the spreadsheet, refresh the request using Sunday, November 30, 2008 as the inclusive [!UICONTROL End Date] for the floating request. Les données se rapportent à une période d’une semaine.

Si, au lieu de cela, vous actualisez le   et spécifiez samedi 29 novembre comme date [!UICONTROL End Date] de la requête flottante, les données reflètent la semaine du 16/11 au 22/11. En effet, la date de référence de l’actualisation de la requête est un jour plus tôt.

Here are the differences when the inclusive [!UICONTROL End Date] for the request is 11/29:

*Du :* cw-1w

jour de la semaine en cours commençant le dimanche 23 novembre moins sept jours = jour de la semaine passée commençant le dimanche 16 novembre

*Au :* cw-1d

jour de la semaine en cours commençant le dimanche 23 novembre moins un jour = samedi 22 novembre

En Europe et dans d’autres pays du monde, la semaine commence le lundi et non le dimanche. Dans ce cas, vous pouvez personnaliser le calendrier afin de modifier la date de début. (Reportez-vous à la section [Calendrier personnalisé](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).)
