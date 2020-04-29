---
description: valeur nulle
title: 'Requêtes de données - Assistant Requête : Étape 1'
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Requêtes de données - Assistant Requête : Étape 1

Le formulaire Assistant Requête : Étape 1 vous permet de sélectionner la suite de rapports, le type de rapport, des segments, ainsi que de configurer des dates.

![](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**:  des suites de rapports disponibles en fonction de vos identifiants de connexion. See [Select Report Suites](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Sélecteur de plage** : permet de sélectionner un identifiant de suite de rapports à partir d’une cellule dans Excel. Reportez-vous à la section [Sélectionner des suites de rapports](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segment** : les segments sont des sous-ensembles personnalisés de données ou des données filtrées selon des règles que vous créez. Les segments dépendent des accès, des visites et des visiteurs. Pour plus d’informations sur les segments, voir le [guide de segmentation d’Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/seg-home.html).

   For example, you can run a [!UICONTROL Pages Report], and then apply a First Time Visits segment.

1. **Autoriser le remplacement de la liste de publication** : lorsque vous planifiez un rapport, vous pouvez choisir une liste de publication à utiliser dans le cadre de la distribution. La configuration des listes de publication s’effectue dans **[!UICONTROL Analytics]** > **[!UICONTROL Admin tools]**. La suite de rapports affectée à cette requête est remplacée par l’identifiant de suite de rapports attribué à chaque destinataire de la liste de publication. Reportez-vous à la section [Autorisation des remplacements de la liste de publication](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md).

1. **Type de rapport** : indique le rapport de base à exécuter dans votre requête de données. Un seul rapport est exécuté par requête. Ce rapport peut contenir des dimensions et des mesures de type « un à plusieurs ». Metrics and dimensions for a report type are displayed on the [!UICONTROL Request Wizard; Step 2] interface. Voir [Sélection des types de rapports](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **Plages de dates** : cette option définit la période couverte par la requête. Il existe plusieurs types de périodes de requête, telles que « prédéfinies », « fixes » et « variables ». Il ne peut pas y avoir plus de 366 périodes. Vous pouvez également choisir une plage de dates spécifiées par une cellule et enregistrer des plages de dates en tant que modèles en vue d’une utilisation ultérieure.  Voir [Configuration des dates des rapports](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).

1. **Appliquer la granularité** : la granularité définit le niveau des détails temporels inclus dans le rapport. Voir [Granularité](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

>[!MORELIKETHIS]
>
>* [Création d’une requête de données](/help/analyze/report-builder/data-requests/t-create-a-data-request.md)

