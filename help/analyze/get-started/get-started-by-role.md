---
description: Cette section contient des informations générales sur Adobe Analytics, notamment des informations sur l’interface d’Analytics, ainsi que des informations de prise en main destinées aux administrateurs, aux analystes, aux utilisateurs et aux développeurs.
title: Prise en main destinée aux administrateurs, analystes, utilisateurs finaux et développeurs
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: f23e0c74072d38d5c6559288b2ced60d98634fac
workflow-type: tm+mt
source-wordcount: '1812'
ht-degree: 34%

---

# Prise en main destinée aux administrateurs, analystes, utilisateurs finaux et développeurs

Il existe trois types d’utilisateurs Adobe Analytics dans une organisation type : administrateurs, analystes et utilisateurs finaux.

Les administrateurs implémentent et configurent Adobe Analytics ; les analystes configurent des projets et créent des analyses à l’aide d’Analysis Workspace ; les utilisateurs finaux obtiennent des informations exploitables sur leurs clients, soit en créant leurs propres analyses, soit en travaillant avec des analystes pour les créer.

Les informations ci-dessous décrivent la prise en main d’Adobe Analytics pour chacun de ces utilisateurs.

## Prise en main pour les administrateurs

Les administrateurs d’Analytics sont chargés de choisir la méthode de mise en oeuvre la plus appropriée pour leur entreprise.

Une fois Adobe Analytics mis en oeuvre, les administrateurs doivent effectuer diverses tâches de configuration pour s’assurer que les analystes et les utilisateurs finaux tirent pleinement parti d’Adobe Analytics. Les administrateurs doivent également surveiller régulièrement leur environnement Analytics pour s’assurer que le système fonctionne efficacement.

### Déterminer les types de données à collecter

Adobe Analytics vous permet de collecter des données à partir de plusieurs types de canaux et de les rassembler pour fournir des informations client en temps réel significatives.

Voici quelques-uns des canaux pris en charge pour la collecte des données :

* Téléphones mobiles

* L&#39;Internet des objets

* TV

* assistants vocaux

* Voitures connectées

* Et plus encore (de nouveaux canaux pris en charge sont ajoutés régulièrement)

La variable [méthode de mise en oeuvre](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=fr) vous choisissez de déterminer le type de données pouvant être collectées.

### Mise en œuvre d’Adobe Analytics

Plusieurs méthodes de mise en oeuvre sont disponibles lors de la mise en oeuvre d’Adobe Analytics sur votre site web ou application mobile.

Pour plus d’informations sur chaque méthode disponible, voir [Mise en oeuvre d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=fr).

| | Méthodes de mise en œuvre |
|---------|---------|
| **Sites web** | <ul><li>Extension SDK Web (recommandée)</li><li>SDK Web</li><li>Extension Analytics</li><li>Code JavaScript hérité</li></ul> |
| **applications mobiles ;** | <ul><li>Extension SDK Mobile (recommandée)</li><li>Extension Analytics</li></ul> |

{style="table-layout:auto"}

### Configuration dʼAdobe Analytics

Les administrateurs d’Analytics doivent effectuer les tâches suivantes avant de mettre Adobe Analytics à la disposition des utilisateurs de l’entreprise :

| Tâche | Utilisation prévue | Informations supplémentaires |
|---------|----------|---------|
| Définition des rôles d’administrateur | Adobe Analytics prend en charge différents types d’administrateurs | [Rôles d’administrateur dans Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Définition des autorisations | Les administrateurs d’Analytics doivent affecter des profils de produit dans le Admin Console pour Adobe Analytics, les outils de suites de rapports et les outils Analytics. | [Autorisations Analytics dans l’Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=fr) |
| Configurer des suites de rapports et définir des paramètres pour votre entreprise | Une suite de rapports est un ensemble de données utilisé par Adobe Analytics pour générer des rapports.<p>Les administrateurs peuvent également configurer [suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=fr) pour segmenter davantage les données.</p> | <ul><li>[Création d’une suite de rapports](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Présentation des paramètres de l’entreprise](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Importer des données | Les sources de données Adobe Analytics vous permettent d’importer des données en ligne ou hors ligne supplémentaires pour la création de rapports. | [Présentation des sources de données](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Classification des données avec des classifications | Les classifications vous permettent de classer les données afin de mieux utiliser les variables, ce qui vous permet d’inclure plus de contenu dans une seule variable. | |
| Gérer les composants | Utilisez le dictionnaire de données et les zones de gestion pour chaque type de composant pour définir les composants disponibles dans votre implémentation Analytics, ainsi que ceux qui sont approuvés pour votre organisation.<p>Il doit s’agir d’une activité continue visant à vous assurer que les composants sont utilisés efficacement dans votre entreprise. </p> | <ul><li>[Présentation du dictionnaire de données](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=fr)</li><li>[Gestionnaire de mesures calculées](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Gestion des segments](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=fr)</li><li>[Création de périodes personnalisées](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=fr)</li></ul> |
| Détection des anomalies | La détection des anomalies met à votre disposition une méthode statistique pour déterminer la modification d’une mesure donnée par rapport à des données antérieures. | [Détection des anomalies - Aperçu](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=fr) |
| Analyse des contributions | L’analyse des contributions détecte les comportements latents au sein de vos données qui expliquent les anomalies statistiques et identifie les corrélations sous-jacentes aux actions inattendues des clients, aux valeurs hors limites et aux pics et creux soudains de certaines mesures à l’échelle des segments d’audience convergents. | [Analyse des contributions - Aperçu](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html?lang=fr) |
| Segmentation Analytics | Vous permet de créer, gérer, partager et appliquer des segments d’audience puissants et ciblés à vos rapports à l’aide des fonctionnalités d’Analytics, de Adobe Experience Cloud, d’Adobe Target et d’autres produits d’Adobe intégrés. | [Segmentation Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=fr) |
| Publication d’audiences sur Audience Manager | | |
| Intégrations | Vous pouvez afficher des informations provenant d’autres applications dans Adobe Analytics. <p>Voici quelques intégrations courantes :</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=fr">Media Analytics</a></li> | |

{style="table-layout:auto"}

### Surveillance d’Adobe Analytics

Diverses fonctionnalités sont disponibles pour vous aider à surveiller votre environnement Adobe Analytics.

Les administrateurs d’Analytics doivent tenir compte des fonctionnalités suivantes disponibles pour surveiller les aspects importants de votre environnement Analytics :

| Tâche | Utilisation prévue | Informations supplémentaires |
|---------|----------|---------|
| Gestionnaire des activités de rapport | Le gestionnaire des activités de rapport vous permet d’afficher la capacité de création de rapports pour chaque suite de rapports de votre entreprise. Il offre une visibilité détaillée sur la création de rapports sur la consommation et vous aide à diagnostiquer et à corriger facilement les problèmes de capacité pendant les heures de pointe de la création de rapports. | [Gestionnaire des activités de rapport](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
| Utilisation des appels au serveur | Un appel au serveur, nommé également « Accès » ou « Demande d’image », est une instance dans laquelle des données sont envoyées vers les serveurs Adobe pour traitement. Un tableau de bord de l’utilisation de l’appel au serveur est disponible. Il effectue le suivi de vos données de consommation d’appels au serveur et les compare à votre limite contractuelle. Vous pouvez configurer des alertes pour éviter les dépassements. | [Présentation de l’utilisation des appels au serveur](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
| Fichiers de log | Fichiers journaux permettant de savoir quand se connectent les utilisateurs, leur utilisation, l’accès, les suites de rapports et les changements administratifs. | [Journaux](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=fr) |

{style="table-layout:auto"}

## Prise en main d’Analytics

Quoique tout membre d’une entreprise puisse utiliser Adobe Analytics pour obtenir des informations exploitables sur le comportement des clients sur plusieurs sites web et applications, Adobe Analytics est conçu en tenant compte des analystes de données.

Vous trouverez ci-dessous les principales tâches et fonctionnalités que les analystes doivent connaître afin de tirer pleinement parti d’Adobe Analytics et d’Analysis Workspace.

| Fonctionnalité | Utilisation prévue | Informations supplémentaires |
|---------|----------|---------|
| Création et partage de projets dans Analysis Workspace | Analysis Workspace est un outil de navigation flexible qui vous permet de créer rapidement des analyses et de partager des informations. L’interface par glisser-déposer vous permet de concevoir votre analyse, d’ajouter des visualisations pour donner vie aux données, de traiter un jeu de données, de partager et de planifier des projets avec toute personne de votre organisation.<p>Les analystes de données sont souvent chargés de créer des projets dans Analysis Workspace pour les utilisateurs de leur entreprise.</p><p>Une fois les projets créés, les analystes partagent ces projets avec le [utilisateurs finaux](#end-users)(non analystes) de leurs organisations qui ont demandé les données et les ont aidées à comprendre comment les interpréter.</p> | <ul><li>[Création de projets](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Partage de projets](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Attribution | Les analystes peuvent personnaliser la manière dont les éléments de dimension obtiennent du crédit pour les événements de succès en utilisant divers modèles d’attribution et intervalles de recherche en amont dans Analysis Workspace.<p>Les modèles d’attribution linéaire accordent le même crédit à chaque point de contact menant à une conversion, tandis que Première touche accorde un crédit complet au point de première touche. De nombreux autres modèles d’attribution sont disponibles, y compris le modèle algorithmique, qui utilise des techniques statistiques pour déterminer de manière dynamique la distribution optimale du crédit. </p> | [Modèles d’attribution et fenêtres de recherche arrière](/help/analyze/analysis-workspace/attribution/models.md) |
| Détection des anomalies | Dans Analysis Workspace, la modélisation statistique détecte automatiquement des tendances inattendues dans vos données en analysant les mesures et en établissant une plage de valeurs inférieure, supérieure et attendue. En cas de pic ou de creux inattendu, le système vous en avertit par le biais du rapport. | [Détection des anomalies - Aperçu](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Analyse des contributions | Utilisez Analysis Workspace pour découvrir des schémas masqués dans vos données afin d’expliquer les anomalies statistiques et d’identifier les corrélations sous-jacentes aux actions inattendues des clients, aux valeurs hors limites et aux pics ou creux soudains des mesures dans les segments d’audience. | [Analyse des contributions - Aperçu](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Alertes intelligentes | Créez et gérez des alertes basées sur des anomalies de données et des alertes &quot;empilées&quot; qui capturent plusieurs mesures dans une seule alerte. | [Alertes intelligentes - Aperçu](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Exportation des données | Les flux de données et de Data Warehouse vous permettent d’exporter des données vers différentes destinations de cloud, telles que Google Cloud Platform, Azure RBAC, Azure SAS et Amazon S3. | [Guide d’exportation Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=fr) |
| Activity Map | Activity Map est une application Adobe Analytics conçue pour établir un classement de l’activité des liens à l’aide de superpositions visuelles et pour fournir un tableau de bord d’analyses en temps réel visant à contrôler l’engagement du public de vos pages web.<p>Activity Map vous permet de configurer différents affichages afin d’identifier visuellement l’accélération de l’activité des clients, de quantifier les initiatives de marketing et d’agir sur les besoins et les comportements d’audience.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=fr) |
| Report Builder | Le Report Builder est un complément pour Microsoft Excel. Report Builder vous permet de créer des demandes personnalisées à partir des données Adobe Analytics insérées dans vos feuilles de calcul Excel. Ces demandes peuvent référencer des cellules de manière dynamique dans votre feuille de calcul. Vous pouvez, en outre, mettre à jour et personnaliser la manière dont le Report Builder présente les données. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=fr) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

## Prise en main pour les utilisateurs finaux

Les utilisateurs finaux qui ne sont pas des analystes professionnels peuvent soit travailler avec des analystes de leur entreprise pour tirer pleinement parti de la puissance d’Adobe Analytics et d’Analysis Workspace, soit apprendre les bases d’Analysis Workspace afin de commencer à obtenir des informations exploitables sur leurs clients.

### Utilisation d’analystes

En règle générale, les utilisateurs d’une entreprise qui souhaitent en savoir plus sur le comportement des clients sur leurs différents sites ne sont pas des analystes professionnels.

Idéalement, ces utilisateurs doivent travailler avec [analystes](#analysts) au sein d’une organisation pour :

1. Définissez les exigences des analyses en expliquant à l’analyste ce qu’il espère apprendre sur les clients.

1. Examinez les analyses pour vérifier qu&#39;elles répondent aux objectifs.

1. Discuter des données obtenues dans les analyses.

1. Modifiez les analyses selon vos besoins au fil du temps.

### Création d’analyses dans Analysis Workspace

Il n’est pas nécessaire d’être un analyste de données pour obtenir des informations exploitables d’Adobe Analytics.

Certains utilisateurs peuvent trouver utile de travailler avec un analyste de données pour configurer un projet dans Analysis Workspace et expliquer comment interpréter les données, comme décrit dans la section [Utilisation d’analystes](#work-with-analysts); d’autres utilisateurs peuvent être à l’aise pour construire le projet et interpréter les données eux-mêmes.

Analysis Workspace vous permet de créer rapidement des analyses pour recueillir des informations, puis de les partager avec d’autres personnes. L’interface de navigateur par glisser-déposer vous permet de concevoir votre analyse, d’ajouter des visualisations pour donner vie aux données, de traiter un jeu de données et de partager et de planifier des projets avec toute personne de votre choix.

Pour plus d’informations sur la création d’analyses dans Analysis Workspace, voir [Présentation d’Analysis Workspace](/help/analyze/analysis-workspace/home.md).

## Prise en main pour les développeurs

[Les API Analytics vous permettent d’appeler directement les serveurs d’Adobe afin d’effectuer la plupart des actions que vous pouvez effectuer dans l’interface utilisateur.](https://developer.adobe.com/analytics-apis/docs/2.0/)

Vous pouvez créer des rapports pour explorer vos données, obtenir des informations ou répondre à des questions importantes à leur sujet. Vous pouvez également gérer les composants d’Adobe Analytics, tels que la création de segments ou de mesures calculées.