---
description: Vue d’ensemble des informations générales sur Adobe Analytics, notamment sur l’interface d’Analytics, ainsi que sur la prise en main destinées aux administrateurs et administratrices, aux analystes, aux utilisateurs et utilisatrices et aux développeurs et développeuses.
title: Prise en main destinée aux administrateurs et administratrices, analystes, utilisateurs et utilisatrices finaux et développeurs et développeuses
feature: Analytics Basics
exl-id: 11800de5-224a-4bd2-8cb1-a6318925db71
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: ht
source-wordcount: '1691'
ht-degree: 100%

---

# Prise en main destinée aux administrateurs et administratrices, analystes, utilisateurs et utilisatrices finaux et développeurs et développeuses

Toute organisation possède en général les quatre types d’utilisateurs et d’utilisatrices d’Adobe Analytics suivants :

* **Administrateurs et administratrices :** mettent en œuvre et configurent Adobe Analytics.

* **Analystes :** configurent des projets et créent des analyses à l’aide d’Analysis Workspace.

* **Utilisateurs et utilisatrices finaux :** obtiennent des informations exploitables sur leurs clientes et clients, soit en créant leurs propres analyses, soit en travaillant avec des analystes qui les créent à leur place.

* **Développeurs et développeuses :** utilisent les API Adobe Analytics 2.0 pour appeler directement les serveurs d’Adobe et effectuer pratiquement toute action pouvant être réalisée dans l’interface utilisateur, comme créer des rapports à explorer, obtenir des informations ou répondre à des questions importantes sur les données.

Les informations ci-dessous détaillent comment ces utilisateurs et utilisatrices peuvent commencer à tirer parti d’Adobe Analytics.

## Prise en main pour les administrateurs et les administratrices

Les administrateurs et les administratrices d’Analytics ont le dernier mot sur la méthode de mise en œuvre la plus efficace pour leur organisation.

Une fois la mise en œuvre d’Adobe Analytics terminée, les administrateurs et les administratrices s’attellent à différentes tâches de configuration pour s’assurer que les analystes et les utilisateurs et utilisatrices finaux tirent pleinement parti d’Adobe Analytics. Il leur incombe également de surveiller régulièrement leur environnement Analytics pour s’assurer que le système fonctionne de manière efficace.

### Déterminer les types de données à collecter

Adobe Analytics vous permet de collecter des données à partir de plusieurs types de canaux et de les rassembler pour fournir des informations pertinentes sur la clientèle en temps réel.

Voici quelques-uns des canaux pris en charge pour la collecte des données :

* Téléphones portables

* L’Internet des objets

* TV

* Assistants vocaux

* Voitures connectées

* Et plus encore (de nouveaux canaux pris en charge sont ajoutés régulièrement)

La [méthode de mise en œuvre](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=fr) que vous choisissez détermine le type des données pouvant être collectées.

### Mettre en œuvre Adobe Analytics

Plusieurs méthodes de mise en œuvre sont disponibles lors de la mise en œuvre d’Adobe Analytics sur votre site web ou application mobile.

Pour plus d’informations sur les méthodes disponibles, consultez la section [Mettre en œuvre Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=fr).

| | Méthodes de mise en œuvre |
|---------|---------|
| **Sites web** | <ul><li>Extension SDK Web (recommandé)</li><li>SDK Web</li><li>Extension Analytics</li><li>Code JavaScript hérité</li></ul> |
| **Applications mobiles** | <ul><li>Extension SDK Mobile (recommandé)</li><li>Extension Analytics</li></ul> |

{style="table-layout:auto"}

### Configurer Adobe Analytics

Les administrateurs et administratrices d’Analytics doivent effectuer les tâches suivantes avant de mettre Adobe Analytics à la disposition du personnel de l’organisation :

| Tâche | Utilisation prévue | Informations supplémentaires |
|---------|----------|---------|
| Définir les rôles d’administration | Adobe Analytics prend en charge différents types d’administrateurs et d’administratrices | [Rôles d’administrateur ou d’administratrice dans Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=fr) |
| Définir les autorisations | Les administrateurs et administratrices d’Analytics doivent affecter des profils de produit dans l’Admin Console pour Adobe Analytics, les outils de suites de rapports et les outils Analytics. | [Autorisations Analytics dans l’Admin Console](/help/admin/admin-console/permissions/analytics-tools.md) |
| Configurer des suites de rapports et définir des paramètres pour votre entreprise | Une suite de rapports est un ensemble de données utilisé par Adobe Analytics pour générer des rapports.<p>Les administrateurs et les administratrices peuvent également configurer des [suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=fr) pour segmenter davantage les données.</p> | <ul><li>[Création d’une suite de rapports](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=fr)</li><li>[Vue d’ensemble des paramètres d’entreprise](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=fr)</li></ul> |
| Importer des données | Les sources de données Adobe Analytics permettent d’importer des données en ligne et hors ligne supplémentaires pour la création de rapports. | [Vue d’ensemble des sources de données](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=fr) |
| Classer les données avec des classifications | Les classifications vous permettent de classer les données afin de tirer pleinement parti des variables et d’inclure plus de contenu dans une seule variable. | [Présentation des classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=fr) |
| Gérer les composants | Utilisez le dictionnaire de données et les zones de gestion de chaque type de composant pour définir les composants disponibles dans votre mise en œuvre d’Analytics, ainsi que ceux qui sont approuvés pour votre organisation.<p>Effectuez un suivi régulier afin de vous assurer que les composants sont utilisés à bon escient au sein de votre organisation. </p> | <ul><li>[Vue d’ensemble du dictionnaire de données](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=fr)</li><li>[Gestionnaire de mesures calculées](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=fr)</li><li>[Gérer les segments](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=fr)</li><li>[Création de périodes personnalisées](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=fr)</li></ul> |
| Détection des anomalies | La détection des anomalies met à votre disposition une méthode statistique pour déterminer la modification d’une mesure donnée par rapport à des données antérieures. | [Vue d’ensemble de la détection des anomalies](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=fr) |
| Analyse des contributions | L’analyse des contributions détecte les comportements latents au sein de vos données qui expliquent les anomalies statistiques et identifie les corrélations sous-jacentes aux actions inattendues des clientes et des clients, aux valeurs hors limites et aux pics et creux soudains de certaines mesures à l’échelle des segments d’audience convergents. | [Vue d’ensemble de l’analyse des contributions](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) |
| Segmentation Analytics | Permet de créer, gérer, partager et appliquer des segments d’audiences puissants et ciblés aux rapports à l’aide des fonctionnalités d’Analytics, d’Adobe Experience Cloud, d’Adobe Target et d’autres produits Adobe intégrés. | [Segmentation Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=fr) |
| Publier des audiences sur Audience Manager | Adobe Audience Manager est une puissante plateforme de gestion des données qui permet de créer des profils d’audience uniques à partir d’intégrations de données de première partie, de seconde partie (partenaire) et de tierce partie. | [Présentation d’Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=fr) |
| Intégrations | Vous pouvez afficher des informations provenant d’autres applications dans Adobe Analytics. <p>Voici quelques intégrations courantes :</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=fr">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=fr">Module complémentaire Streaming Media Collection</a></li> | [Intégration d’Analytics](https://experienceleague.adobe.com/docs/analytics/integration/home.html?lang=fr) |

{style="table-layout:auto"}

### Surveiller Adobe Analytics

Plusieurs fonctionnalités sont dédiées à la surveillance de votre environnement Adobe Analytics.

Les administrateurs et les administratrices d’Analytics disposent des fonctionnalités suivantes pour surveiller les aspects importants de l’environnement Analytics :

| Tâche | Utilisation prévue | Informations supplémentaires |
|---------|----------|---------|
| Gestionnaire des activités de rapport | Le gestionnaire des activités de rapport vous permet d’afficher la capacité de création de rapports pour chaque suite de rapports de votre organisation. Il vous offre une visibilité détaillée sur la consommation de rapports et vous permet de diagnostiquer et de résoudre facilement les problèmes de capacité pendant les heures de pointe de la création de rapports. | [Gestionnaire des activités de rapport](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=fr) |
| Utilisation de l’appel au serveur | Un appel au serveur, nommé également « Accès » ou « Demande d’image », est une instance dans laquelle des données sont envoyées vers les serveurs Adobe pour traitement. Le tableau de bord Utilisation de l’appel au serveur est disponible pour suivre les données relatives à votre consommation d’appels au serveur et les comparer avec votre limite contractuelle. Vous pouvez configurer des alertes pour éviter les dépassements. | [Vue d’ensemble de l’utilisation de l’appel au serveur](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=fr) |
| Fichiers journaux | Fichiers journaux permettant de savoir quand se connectent les utilisateurs et les utilisatrices, leur utilisation, l’accès, les suites de rapports et les changements d’administration. | [Journaux](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=fr) |

{style="table-layout:auto"}

## Prise en main pour les analystes

Même si Adobe Analytics permet à toutes les personnes membres d’une organisation d’obtenir des informations exploitables sur le comportement de la clientèle sur les différents sites web et applications, Adobe Analytics est avant tout destiné aux analystes de données.

Vous trouverez ci-dessous les principales tâches et fonctionnalités conçues pour permettre aux analystes de tirer pleinement parti d’Adobe Analytics et d’Analysis Workspace.

| Fonctionnalité | Utilisation prévue | Informations supplémentaires |
|---------|----------|---------|
| Créer et partager des projets dans Analysis Workspace | Analysis Workspace est un outil de navigation flexible qui vous permet de créer rapidement des analyses et de partager des informations. L’interface par glisser-déposer vous permet de concevoir votre analyse, d’ajouter des visualisations pour donner vie aux données, de traiter un jeu de données, de partager et de planifier des projets avec toute personne de votre organisation.<p>Les analystes de données sont des personnes souvent chargées de créer des projets dans Analysis Workspace pour les utilisateurs et les utilisatrices de leur organisation.</p><p>Une fois les projets créés, les analystes partagent ces projets avec les [utilisateurs et utilisatrices finaux](#end-users) (qui ne sont pas des analystes) de leur organisation qui ont sollicité les données et participent à leur compréhension et interprétation.</p> | <ul><li>[Création de projets](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Partage de projets](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Attribution | Les analystes peuvent personnaliser la manière dont les éléments de dimension reçoivent du crédit pour les événements de succès en utilisant divers modèles d’attribution et intervalles de recherche en amont dans Analysis Workspace.<p>Les modèles d’attribution linéaire accordent le même crédit à chaque point de contact menant à une conversion, tandis que Première touche accorde un crédit complet au premier point de contact. De nombreux autres modèles d’attribution sont disponibles, y compris le modèle algorithmique, qui utilise des techniques statistiques pour déterminer de manière dynamique la distribution optimale du crédit. </p> | [Modèles d’attribution et fenêtres de recherche en amont](/help/analyze/analysis-workspace/attribution/models.md) |
| Détection des anomalies | Dans Analysis Workspace, la modélisation statistique détecte automatiquement des tendances inattendues dans vos données en analysant les mesures et en établissant des plages de valeurs inférieure, supérieure et attendue. En cas de pic ou de creux inattendu, le système vous en avertit par le biais du rapport. | [Vue d’ensemble de la détection des anomalies](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| Analyse des contributions | Analysis Workspace permet de détecter les comportements latents au sein de vos données qui expliquent les anomalies statistiques et identifie les corrélations sous-jacentes aux actions inattendues des clientes et des clients, aux valeurs hors limites et aux pics et creux soudains de mesures à l’échelle des segments d’audience. | [Analyse des contributions](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) dans [Détection des anomalies - Vue d’ensemble](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| Alertes | Créez et gérez des alertes en fonction des anomalies de données et des alertes « empilées », qui regroupent plusieurs mesures dans une seule alerte. | [Vue d’ensemble des alertes](/help/components/c-alerts/intellligent-alerts.md) |
| Exportation de données | Data Warehouse et les flux de données vous permettent d’exporter des données vers différents espaces de stockage, tels que Google Cloud Platform, Azure RBAC, Azure SAS et Amazon S3. | [Guide d’exportation Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=fr) |
| Activity Map | Activity Map est une application Adobe Analytics conçue pour établir un classement de l’activité des liens à l’aide de superpositions visuelles et pour fournir un tableau de bord d’analyses en temps réel visant à contrôler l’engagement de l’audience de vos pages web.<p>Activity Map vous permet de configurer différents affichages afin d’identifier visuellement l’accélération de l’activité des clients, de quantifier les initiatives de marketing et d’agir sur les besoins et les comportements d’audience.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=fr) |
| Report Builder | Le Report Builder est un complément pour Microsoft Excel. Report Builder vous permet de créer des demandes personnalisées à partir des données Adobe Analytics insérées dans vos feuilles de calcul Excel. Ces demandes peuvent référencer des cellules de manière dynamique dans votre feuille de calcul. Vous pouvez, en outre, mettre à jour et personnaliser la manière dont le Report Builder présente les données. | [Report Builder](https://experienceleague.adobe.com/fr/docs/analytics/analyze/report-builder/report-buider-overview) |

<!-- * Realtime reporting? -->

## Prise en main pour les utilisateurs et utilisatrices finaux

Les utilisateurs et utilisatrices finaux qui ne sont pas des personnes professionnelles de l’analyse peuvent collaborer avec les analystes de leur organisation pour tirer pleinement parti de la puissance d’Adobe Analytics et d’Analysis Workspace. Ils peuvent également apprendre les principes de base d’Analysis Workspace afin d’obtenir des informations exploitables sur leur clientèle.

### Collaborer avec les analystes

En général, les personnes membres d’une organisation qui souhaitent en savoir plus sur le comportement de la clientèle sur leurs différents sites ne sont pas des personnes professionnelles de l’analyse.

Dans l’idéal, elles travaillent de concert avec les [analystes](#analysts) au sein d’une organisation pour :

1. définir les modalités des analyses en expliquant à l’analyste ce qu’elles souhaitent connaître sur la clientèle ;

1. examiner les analyses pour s’assurer qu’elles répondent aux objectifs ;

1. discuter des données obtenues dans les analyses ;

1. modifier les analyses selon les besoins au fil du temps ;

### créer des analyses dans Analysis Workspace

Il n’est pas nécessaire d’être une personne professionnelle de l’analyse de données pour obtenir des informations exploitables avec Adobe Analytics.

Certains utilisateurs utilisatrices peuvent apprécier de travailler avec une personne professionnelle de l’analyse de données pour configurer un projet dans Analysis Workspace et savoir comment interpréter les données, comme décrit dans la section [Collaborer avec les analystes](#work-with-analysts), tandis que d’autres préfèrent créer le projet et interpréter les données de manière autonome.

Analysis Workspace vous permet de créer rapidement des analyses pour recueillir des informations, puis de les partager avec d’autres personnes. L’interface de navigateur par glisser-déposer vous permet de concevoir votre analyse, d’ajouter des visualisations pour donner vie aux données, de traiter un jeu de données et de partager et de planifier des projets avec toute personne de votre choix.

Pour plus d’informations sur la création d’analyses dans Analysis Workspace, consultez la [Vue d’ensemble d’Analysis Workspace](/help/analyze/analysis-workspace/home.md).

## Prise en main pour les développeurs et les développeuses

[Les API Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/) vous permettent d’appeler directement les serveurs d’Adobe afin d’effectuer la plupart des actions que vous pouvez effectuer dans l’interface utilisateur.

Vous pouvez créer des rapports pour explorer vos données, obtenir des informations ou répondre à des questions importantes à leur sujet. Vous pouvez également gérer les composants d’Adobe Analytics, tels que la création de segments ou de mesures calculées.
