---
description: valeur nulle
seo-description: valeur nulle
seo-title: Requêtes de données - Assistant Requête Etape 1
title: Requêtes de données - Assistant Requête Etape 1
uuid: 717542 c 3-e 4 aa -4 e 00-b 0 ca-cadlux 219 d 13
translation-type: tm+mt
source-git-commit: 1e7dc9c769a9980e7b60bd395e7c68d5e446dae3

---


# Requêtes de données - Assistant Requête Etape 1

Le formulaire Assistant Requête : Étape 1 vous permet de sélectionner la suite de rapports, le type de rapport, des segments, ainsi que de configurer des dates.

![](assets/rw1_overview.png)

1. **[!UICONTROL Suite de rapports]** : liste des suites de rapports mises à votre disposition sur la base des vos identifiants de connexion. See [Select Report Suites](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913).

1. **Sélecteur de plage** : permet de sélectionner un identifiant de suite de rapports à partir d’une cellule dans Excel. Reportez-vous à la section [Sélectionner des suites de rapports](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913).

1. **Segment** : les segments sont des sous-ensembles personnalisés de données ou des données filtrées selon des règles que vous créez. Les segments dépendent des accès, des visites et des visiteurs. Pour plus d’informations sur les segments, voir le [guide de segmentation d’Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/segment/).

   Vous pouvez, par exemple, exécuter un [!UICONTROL rapport Pages], puis appliquer un segment Premières visites.

1. **Autoriser le remplacement de la liste de publication** : lorsque vous planifiez un rapport, vous pouvez choisir une liste de publication à utiliser dans le cadre de la distribution. Publishing lists are set up in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin tools]**. La suite de rapports affectée à cette requête est remplacée par l’identifiant de suite de rapports attribué à chaque destinataire de la liste de publication. Reportez-vous à la section [Autorisation des remplacements de la liste de publication](../../../analyze/report-builder/data-requests/allow-publishing-list-overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C).

1. **Type de rapport** : indique le rapport de base à exécuter dans votre requête de données. Un seul rapport est exécuté par requête. Ce rapport peut contenir des dimensions et des mesures de type « un à plusieurs ». Les mesures et dimensions affectées à un type de rapport sont affichées dans l’interface [!UICONTROL Assistant Requête : Étape 2]. See [Select Report Types](../../../analyze/report-builder/data-requests/c-report-types/select-report-types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC).

1. **Plages de dates** : cette option définit la période couverte par la requête. Il existe plusieurs types de périodes de requête, telles que « prédéfinies », « fixes » et « variables ». Il ne peut pas y avoir plus de 366 périodes. Vous pouvez également choisir une plage de dates spécifiées par une cellule et enregistrer des plages de dates en tant que modèles en vue d’une utilisation ultérieure.  See [Configuring Report Dates](../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **Appliquer la granularité** : la granularité définit le niveau des détails temporels inclus dans le rapport. Reportez-vous à la section [Granularité](../../../analyze/report-builder/data-requests/configuring-report-dates/granularity.md#concept_A13CBA2962E24FF882456135431B7ADB).

>[!MORE_LIKE_THIS]
>
>* [Créer une requête de données](/help/analyze/report-builder/data-requests/t-create-a-data-request.md)