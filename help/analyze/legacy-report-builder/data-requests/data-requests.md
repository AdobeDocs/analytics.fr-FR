---
description: Première étape lors de la création d’une requête dans Report Builder.
title: 'Requêtes de données - Assistant Requête : Étape 1'
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
TQID: https://experienceleague.adobe.com/87MzdxBePRZKBttF3P6XhuDq5hR6XpEWaLdrYDMu-5Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 401
ht-degree: 83%

---

# Requêtes de données - Assistant Requête : Étape 1

{{legacy-arb}}

Le formulaire Assistant Requête : Étape 1 vous permet de sélectionner la suite de rapports, le type de rapport, des segments, ainsi que de configurer des dates.

![Capture d’écran affichant l’Assistant Requête : formulaire de l’étape 1.](assets/rw1_overview.png)

1. **[!UICONTROL Suite de rapports]** : liste des suites de rapports mises à votre disposition sur la base des vos identifiants de connexion. Voir [Sélectionner des suites de rapports](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Sélecteur de plage** : permet de sélectionner un identifiant de suite de rapports à partir d’une cellule dans Excel. Voir [Sélectionner des suites de rapports](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segment** : les segments sont des sous-ensembles personnalisés de données ou des données filtrées selon des règles que vous créez. Les segments dépendent des accès, des visites et des visiteurs. Pour plus d’informations sur les segments, voir le [guide de segmentation d’Analytics](/help/components/segmentation/seg-home.md).

   Vous pouvez, par exemple, exécuter un [!UICONTROL rapport Pages], puis appliquer un segment Premières visites.

1. **Autoriser le remplacement de la liste de publication** : les listes de publication étaient une fonctionnalité de Reports &amp; Analytics, en [fin de vie](https://new.express.adobe.com/webpage/WFCyq7w8kijmB ?).

1. **Type de rapport** : indique le rapport de base à exécuter dans votre requête de données. Un seul rapport est exécuté par requête. Ce rapport peut contenir des dimensions et des mesures de type « un à plusieurs ». Les mesures et dimensions affectées à un type de rapport sont affichées dans l’interface [!UICONTROL Assistant Requête : Étape 2]. Voir [Sélection des types de rapports](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md).

1. **Périodes** : cette option définit la période couverte par la requête. Il existe plusieurs types de périodes de requête, telles que « prédéfinies », « fixes » et « variables ». Le nombre maximal de périodes est de 366. Vous pouvez également choisir une période spécifiée par une cellule et enregistrer les périodes en tant que modèles pour une utilisation ultérieure.  Voir [Configuration des dates des rapports](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md).

1. **Appliquer la granularité** : la granularité définit le niveau des détails temporels inclus dans le rapport. Voir [Granularité](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md).

## Résolution des problèmes

Il arrive que l’Assistant Requête s’affiche hors de l’écran, en particulier pour les utilisateurs qui passent d’une configuration de moniteur à une autre. Par exemple, si vous utilisez une station d’accueil au travail et votre écran d’ordinateur portable à la maison. Si vous cliquez de nouveau sur « Créer » alors qu’un Assistant Requête est déjà ouvert, vous obtenez l’erreur suivante :

« Vous devez terminer le processus Assistant Requête avant d’en commencer un nouveau. »

Il suffit de ramener l’Assistant Requête à l’écran pour résoudre ce problème.

1. Ouvrez Microsoft Excel et connectez-vous à Report Builder.
2. Cliquez sur [!UICONTROL Créer], ce qui ouvre l’Assistant Requête hors de l’écran.
3. Appuyez sur `[Alt]` + `[Space]`.
4. Appuyez sur `[M]`.
5. Appuyez sur l’une des touches fléchées.
6. Déplacez votre souris, ce qui permet de fixer l’Assistant Requête à votre curseur.
7. Cliquez sur la souris pour relâcher l’Assistant Requête sur l’écran.
