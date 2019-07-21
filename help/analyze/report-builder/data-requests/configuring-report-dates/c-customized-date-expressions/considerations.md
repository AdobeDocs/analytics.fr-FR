---
description: 'Deux considérations importantes lors de l''utilisation de l''expression Personnaliser pour définir la plage de dates '
seo-description: 'Deux considérations importantes lors de l''utilisation de l''expression Personnaliser pour définir la plage de dates '
seo-title: Considérations
solution: Analytics
title: Considérations de date personnalisées
topic: Créateur de rapports
uuid: a 3 bb 3 a 63-0 f 15-4292-ade 7-4 ea 852 fe 68 c 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Considérations de date personnalisées

Il convient de prendre en compte deux facteurs importants lorsque vous définissez la période à l’aide d’une expression personnalisée :

* Le jour d’exécution du rapport (à partir de) (ou de l’actualisation des requêtes) détermine quelles données sont disponibles.
* La substitution des dates de début et de fin du rapport affecte la période couverte par le rapport.

La disponibilité des données dépend de la période du rapport et de la date à laquelle vous actualisez les requêtes du rapport. Veillez, par conséquent, à exécuter le rapport le jour approprié afin d’extraire les informations souhaitées. Les exemples ci-dessous illustrent ces deux considérations.

Supposons que vous exécutiez une requête pour [!UICONTROL Pages vues] avec la granularité Agrégé. En Amérique du Nord, la semaine commence le dimanche. Afin d’obtenir des rapports à jour pour la période du dimanche au samedi (par exemple, du 23 novembre au 29 novembre 2008), exécutez le rapport (actualisez les requêtes) le dimanche (30 novembre) pour la semaine précédente (23/11 au 29/11).

Utilisez cette expression personnalisée :

*Du :* cw-1w *Au :* cw-1d

Analyse de l’expression personnalisée lorsque la [!UICONTROL Date de fin] incluse de la requête est le 30/11 :

*Du :* cw-1w

jour de la semaine en cours commençant le dimanche 30 novembre moins sept jours = jour de la semaine passée commençant le dimanche 23 novembre

*Au :* cw-1d

jour de la semaine en cours commençant le dimanche 30 novembre moins un jour = samedi 29 novembre

Une fois l’expression personnalisée mise en correspondance avec la feuille de calcul, actualisez la requête en utilisant le dimanche 30 novembre 2008 comme [!UICONTROL Date de fin] incluse pour la requête flottante. Les données se rapportent à une période d’une semaine.

Si, au contraire vous actualisez l’expression et précisez samedi 29 novembre comme [!UICONTROL Date de fin] pour la requête flottante, les données se rapportent à la semaine du 16/11 au 22/11. Cela est dû au fait que la date de référence pour l’actualisation de la requête tombe un jour plus tôt.

Voici les différences quand la [!UICONTROL Date de fin] incluse de la requête est le 29/11 :

*Du :* cw-1w

jour de la semaine en cours commençant le dimanche 23 novembre moins sept jours = jour de la semaine passée commençant le dimanche 16 novembre

*Au :* cw-1d

jour de la semaine en cours commençant le dimanche 23 novembre moins un jour = samedi 22 novembre

En Europe et dans d’autres pays du monde, la semaine commence le lundi et non le dimanche. Dans ce cas, vous pouvez personnaliser le calendrier afin de modifier la date de début. (Reportez-vous à la section [Calendrier personnalisé](../../../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md#concept_4342A844600048759EEDABD164AC3F5A).)
