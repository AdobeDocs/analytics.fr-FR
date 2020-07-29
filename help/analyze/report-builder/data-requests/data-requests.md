---
description: valeur nulle
title: 'Requêtes de données - Assistant Requête : Étape 1'
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 72%

---


# Requêtes de données - Assistant Requête : Étape 1

Le formulaire Assistant Requête : Étape 1 vous permet de sélectionner la suite de rapports, le type de rapport, des segments, ainsi que de configurer des dates.

![](assets/rw1_overview.png)

1. **[!UICONTROL Suite de rapports]** : liste des suites de rapports mises à votre disposition sur la base des vos identifiants de connexion. Reportez-vous à la section [Sélectionner des suites de rapports](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Sélecteur de plage** : permet de sélectionner un identifiant de suite de rapports à partir d’une cellule dans Excel. Reportez-vous à la section [Sélectionner des suites de rapports](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segment** : les segments sont des sous-ensembles personnalisés de données ou des données filtrées selon des règles que vous créez. Les segments dépendent des accès, des visites et des visiteurs. Pour plus d’informations sur les segments, voir le [guide de segmentation d’Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/seg-home.html).

   Vous pouvez, par exemple, exécuter un [!UICONTROL rapport Pages], puis appliquer un segment Premières visites.

1. **Autoriser le remplacement de la liste de publication** : lorsque vous planifiez un rapport, vous pouvez choisir une liste de publication à utiliser dans le cadre de la distribution. Les listes de publication sont configurées dans **[!UICONTROL Analytics]** > **[!UICONTROL Outils d’administration]**. La suite de rapports affectée à cette requête est remplacée par l’identifiant de suite de rapports attribué à chaque destinataire de la liste de publication. Reportez-vous à la section [Autorisation des remplacements de la liste de publication](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md).

1. **Type de rapport** : indique le rapport de base à exécuter dans votre requête de données. Un seul rapport est exécuté par requête. Ce rapport peut contenir des dimensions et des mesures de type « un à plusieurs ». Les mesures et dimensions affectées à un type de rapport sont affichées dans l’interface [!UICONTROL Assistant Requête : Étape 2]. Voir [Sélection des types de rapports](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **Plages de dates** : cette option définit la période couverte par la requête. Il existe plusieurs types de périodes de requête, telles que « prédéfinies », « fixes » et « variables ». Il ne peut pas y avoir plus de 366 périodes. Vous pouvez également choisir une plage de dates spécifiées par une cellule et enregistrer des plages de dates en tant que modèles en vue d’une utilisation ultérieure.  Voir [Configuration des dates des rapports](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).

1. **Appliquer la granularité** : la granularité définit le niveau des détails temporels inclus dans le rapport. Voir [Granularité](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

## Résolution des problèmes

Il arrive que l’Assistant Requête s’affiche hors de l’écran, en particulier pour les utilisateurs qui passent d’une configuration de moniteur à une autre. Par exemple, vous utilisez une station d&#39;accueil au travail et votre écran d&#39;ordinateur portable à la maison. Si vous cliquez de nouveau sur &quot;Créer&quot; alors qu’un Assistant de requête est déjà ouvert, vous obtenez l’erreur suivante :

&quot;Vous devez d’abord terminer le processus de l’Assistant Requête avant d’en lancer un nouveau.&quot;

Le déplacement de l’Assistant Requête à l’écran résout ce problème.

1. Ouvrez Microsoft Excel et connectez-vous au Report Builder.
2. Cliquez sur [!UICONTROL Créer], ce qui ouvre l’Assistant Requête hors de l’écran.
3. Appuyer sur `[Alt]` + `[Space]`.
4. Appuyer sur `[M]`.
5. Appuyez sur l’une des touches fléchées.
6. Déplacez la souris, qui associe l&#39;Assistant Requête à votre curseur.
7. Cliquez sur la souris pour lancer l’Assistant Requête à l’écran.
