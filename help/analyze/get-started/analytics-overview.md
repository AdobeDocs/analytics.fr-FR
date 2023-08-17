---
description: Informations générales sur Adobe Analytics
title: Présentation d’Adobe Analytics
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: d5a7dfe720cc84b67208e7d30434295caf1e2aac
workflow-type: tm+mt
source-wordcount: '3111'
ht-degree: 32%

---

# Présentation d’Adobe Analytics

Adobe Analytics permet aux entreprises de collecter des données et d’obtenir des informations exploitables à partir de n’importe quelle interaction client numérique. Grâce à une analyse approfondie, à des rapports polyvalents et à des renseignements prédictifs, les entreprises disposent des bases intelligentes dont elles ont besoin pour créer de meilleures expériences pour leurs clients.

## Avantages clés

Vous trouverez ci-dessous quelques-uns des moyens clés par lesquels Adobe Analytics aide les entreprises à obtenir des informations essentielles pour mieux servir leurs clients.

Pour plus d’informations sur les avantages d’Adobe Analytics, voir [Page produit Adobe Analytics](https://business.adobe.com/products/analytics/adobe-analytics.html).

### Web Analytics

Adobe Analytics fournit les outils de segmentation et de prédiction complexes suivants pour analyser le trafic du site web :

* [Analyses ad hoc dans Analysis Workspace](/help/analyze/analysis-workspace/home.md)

* [Analyse des flux](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)

* [Segmentation avancée](/https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)

### Analyses marketing

Adobe Analytics aide les entreprises à comprendre où les clients interagissent avec leurs marques, quels canaux les clients préfèrent et quelles expériences résonnent avec eux.

Les fonctionnalités clés suivantes d’Adobe Analytics fournissent ces fonctionnalités marketing :

* Collecte de données multicanal

* [Intégration des données hors ligne](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en)

* [Analyses ad hoc dans Analysis Workspace](/help/analyze/analysis-workspace/home.md)

### Attribution

L’attribution permet aux entreprises de voir de quelle façon les différentes interactions sur l’ensemble du parcours client affectent la conversion. Outre les options d’attribution plus traditionnelles, telles que les modèles linéaire ou Première touche, l’attribution dans Adobe Analytics utilise également l’apprentissage automatique et les modèles statistiques avancés pour comprendre l’impact précis de chaque touche.

Pour plus d’informations, voir [Modèles d’attribution et intervalles de recherche en amont](/help/analyze/analysis-workspace/attribution/models.md).


### Analyses prédictives

L’analyse prédictive utilise l’apprentissage automatique et la modélisation statistique avancée pour analyser les données client, rechercher des modèles et prédire le comportement futur, comme l’attrition ou la probabilité de conversion. Cela permet aux analystes de données de tirer parti d’énormes jeux de données qui pourraient autrement être gaspillés.

Les fonctions clés suivantes d’Adobe Analytics fournissent ces fonctions prédictives :

* [Détection des anomalies](#anomaly-detection)

* [Analyse des contributions](#contribution-analysis)

* [Alertes intelligentes](#intelligent-alerts)

## Conditions préalables requises pour l’utilisation d’Adobe Analytics

Pour pouvoir utiliser Adobe Analytics, vous devez disposer des éléments suivants :

* Une licence Adobe Analytics valide

  Adobe Analytics nécessite une licence de site. Pour plus d’informations, contactez votre représentant de compte d’Adobe. <!--is this phrased correctly? Is this important? -->

* Navigateur pris en charge

  Chaque utilisateur accédant à Adobe Analytics doit utiliser un navigateur pris en charge. Pour plus d’informations, voir [Configuration requise pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/sys-reqs.html?lang=en).

<!-- are there more? -->

## Présentation de l’interface Analytics

L’interface d’Adobe Analytics se compose des zones principales suivantes :

### Onglet Workspace

La variable [!UICONTROL Workspace] affiche la liste des projets Analysis Workspace.

1. Dans Adobe Analytics, sélectionnez la variable [!UICONTROL **Workspace**] .

   ![Onglet Workspace](assets/landing-all2.png)

Pour plus d’informations sur les fonctionnalités disponibles dans la section [!UICONTROL Workspace] , voir [Page d’entrée Adobe Analytics](/help/analyze/landing.md).

### Onglet Rapports

À compter du 31 décembre 2023, Adobe prévoit dʼabandonner Reports &amp; Analytics et ses rapports et fonctionnalités associés.

Utilisez plutôt la variable [!UICONTROL **Rapports**] dans le rail de gauche sur la [!UICONTROL **Workspace**] . Pour plus d’informations, voir *Navigation dans l’onglet Rapports* in [Page d’entrée Adobe Analytics](/help/analyze/landing.md).

### Onglet Composants

La variable [!UICONTROL Composants] comprend des fonctionnalités qui vous aident à affiner et à optimiser votre analyse des données.

1. Dans Adobe Analytics, sélectionnez la variable [!UICONTROL **Composants**] , puis sélectionnez [!UICONTROL **Tous les composants**].

   ![Onglet Workspace](assets/components-tab.png)

2. Sélectionnez l’une des fonctionnalités de produit suivantes pour la configurer (en fonction de vos autorisations, il se peut que toutes les fonctionnalités ne soient pas visibles).


   | Fonctionnalité du produit | Fonction | Informations supplémentaires |
   |---------|----------|----------|
   | Segments  | Adobe Analytics permet de créer, gérer, partager et appliquer des segments d’audiences, puissants et ciblés, aux rapports à l’aide des fonctionnalités d’Analytics, d’Adobe Experience Cloud, d’Adobe Target et d’autres produits Adobe intégrés. | [Segmentation Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=fr) |
   | Mesures calculées | Les mesures calculées ou calculées avancées (ou dérivées) sont des mesures personnalisées que vous pouvez créer à partir de mesures existantes.  Ils permettent aux marketeurs, aux chefs de produits et aux analystes de poser des questions sur les données sans avoir à modifier la mise en oeuvre d’Analytics. | [Mesures calculées ou calculées avancées (dérivées)](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=fr) |
   | Périodes | Analysis Workspace comprend une liste des périodes par défaut que les utilisateurs peuvent utiliser lors de la création d’analyses. En outre, vous pouvez créer des plages de dates personnalisées et les rendre disponibles pour les utilisateurs dans Analysis Workspace. | [Création de périodes personnalisées](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=fr) <!-- should create an article in the Components Guide for managing/creating date ranges. This article in the Tools Guide needs updating. --> |
   | Suites de rapports virtuelles |  |  |
   | Alertes | Les alertes intelligentes permettent de contrôler plus précisément les alertes et intègrent la détection des anomalies au système d’alerte. | [Alertes intelligentes](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=en) |
   | Cibles | Les cibles vous permettent de mesurer les performances de votre site web et de suivre leur progression par rapport aux objectifs cibles. Lorsque vous créez des cibles, vous sélectionnez quelles mesures d’attribut ou eVars vous souhaitez mesurer. Vous pouvez aussi choisir de mesurer la totalité du site en fonction de la mesure sélectionnée. <p>Les cibles font partie de Reports &amp; Analytics. En savoir plus sur l’[annonce de fin de vie](https://express.adobe.com/page/6WnF8JK6IRDhf/) de Reports &amp; Analytics.</p> | [Cibles](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/targets.html?lang=en) |
   | Événements du calendrier | Pour les rapports de tendances au fil du temps, les événements du calendrier vous permettent d’afficher graphiquement les événements et de déterminer si des campagnes ou d’autres événements ont eu un impact sur le trafic, les recettes ou toute autre mesure de votre site. | [Événements du calendrier](https://experienceleague.adobe.com/docs/analytics/components/t-calendar-event.html?lang=en) |
   | Annotations | Les annotations dans l’espace de travail vous permettent de communiquer efficacement les nuances et informations sur les données contextuelles à votre organisation. Ils vous permettent de lier des événements de calendrier à des dimensions et des mesures spécifiques. | [Gestion des annotations](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/manage-annotations.html?lang=en) |
   | Jeux de classifications | Les jeux de classifications offrent une interface unique pour gérer les classifications et les règles. <p>Une classification est une méthode permettant de catégoriser des données de variables Analytics, puis de les afficher de différentes manières lors de la création de rapports. Vous établissez une relation entre une valeur de variable et les métadonnées associées à cette valeur. Les classifications peuvent être utilisées sur la plupart des dimensions personnalisées, telles que le code de suivi, les props et les eVars.</p> | [Vue d’ensemble des jeux de classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=fr) |
   | Emplacements | Pour importer des données de classification Adobe Analytics à partir d’une destination cloud, vous devez d’abord ajouter et configurer l’emplacement où vous souhaitez que les données de classification soient collectées. Vous pouvez créer, modifier ou supprimer des emplacements. | [Gestionnaire d’emplacements](https://experienceleague.adobe.com/docs/analytics/components/locations/locations-manager.html?lang=en) |
   | Projets planifiés | Lors de la gestion de projets planifiés, vous pouvez modifier et supprimer les plannings de projet récurrents, rechercher un planning dans la barre de recherche ou à l’aide des options de filtrage du rail de gauche, et filtrer par balise, planifications approuvées, propriétaires, etc. | [Projets planifiés](/help/components/scheduled-projects-manager.md) |
   | Signets | Les signets permettent d’accéder aux rapports les plus utilisés. Les signets que vous créez sont ajoutés à Experience Cloud et sont disponibles dans les fonctions intégrées telles que les connecteurs de données. <p>Les signets font partie de Reports &amp; Analytics. En savoir plus sur l’[annonce de fin de vie](https://express.adobe.com/page/6WnF8JK6IRDhf/) de Reports &amp; Analytics. | [Gestionnaire de signets](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/bookmarks.html?lang=en) |
   | Tableaux de bord | Les tableaux de bord sont créés pour visualiser les mesures et fournir une fonctionnalité d’analyse interactive avec des données. En cliquant sur les éléments d’un tableau de bord, vous pouvez segmenter rapidement et facilement les données afin d’extraire des informations de votre analyse. <p>Les tableaux de bord font partie de Data Workbench. En savoir plus sur le Data Workbench [Annonce de fin de vie](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=en). | [Gestionnaire de tableaux de bord](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/dashboard-manage.html?lang=en) |
   | Rapports planifiés | Les utilisateurs de niveau administrateur peuvent afficher et gérer des rapports planifiés à l’échelle de l’entreprise. | [File d’attente des rapports planifiés](https://experienceleague.adobe.com/docs/analytics/components/scheduled-reports-admin.html?lang=en) |
   | Paramètres des rapports | Ces paramètres se rapportent aux produits Adobe Analytics hérités, qui excluent Analysis Workspace et ses composants associés. Pour apporter des modifications aux paramètres d’Analysis Workspace, accédez à Composants > Préférences. |  |
   | Préférences | Gérez les paramètres d’Analysis Workspace et de ses composants associés pour tous les nouveaux projets ou panneaux que vous créez. Les projets et panneaux existants ne sont pas affectés. | [Préférences](/help/analyze/analysis-workspace/user-preferences.md) |

   {style="table-layout:auto"}

### Onglet Outils

L’onglet Outils ...

1. Dans Adobe Analytics, sélectionnez la variable [!UICONTROL **Outils**] , puis sélectionnez [!UICONTROL **Tous les outils**].

   ![Onglet Workspace](assets/tools-tab.png)

2. Sélectionnez l’une des fonctionnalités de produit suivantes pour la configurer :

   | Fonctionnalité du produit | Fonction | Informations supplémentaires |
   |---------|----------|----------|
   | Data Warehouse | Data Warehouse fait référence à la copie de données Analytics pour les rapports de stockage et personnalisés, que vous pouvez exécuter en filtrant les données. <p>Le gestionnaire de requêtes permet d’afficher, de dupliquer et de reclasser par priorité les requêtes.</p> | [Gérer les demandes de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=en) |
   | Activity Map | Activity Map est conçu pour classer l’activité des liens à l’aide de superpositions visuelles et fournir un tableau de bord d’analyses en temps réel afin de surveiller l’engagement de l’audience de vos pages web. Il vous permet de configurer différentes vues afin d’identifier visuellement l’accélération de l’activité des clients, de quantifier les initiatives marketing et d’agir sur les besoins et les comportements de l’audience. | [Activity Map - Aperçu](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=fr) |
   | Recommendations Classic |  |  |
   | Search&amp;Promote |  |  |
   | Mobile Services |  |  |
   | Tableaux de bord Analytics (application mobile) |  |  |
   | Report Builder |  |  |

   {style="table-layout:auto"}

### Onglet Admin

Onglet Admin ...

1. Dans Adobe Analytics, sélectionnez la variable [!UICONTROL **Administration**] , puis sélectionnez [!UICONTROL **Tous les administrateurs**].

   ![Onglet Workspace](assets/admin-tab.png)

## Prise en main pour les administrateurs, les analystes et les utilisateurs finaux

Il existe trois types d’utilisateurs Adobe Analytics dans une organisation type : administrateurs, analystes et utilisateurs finaux.

Les administrateurs implémentent et configurent Adobe Analytics ; les analystes configurent des projets et créent des analyses à l’aide d’Analysis Workspace ; les utilisateurs finaux obtiennent des informations exploitables sur leurs clients, soit en créant leurs propres analyses, soit en travaillant avec des analystes pour les créer.

Développez les sections ci-dessous pour découvrir comment chacun de ces utilisateurs peut commencer à utiliser Adobe Analytics.

### Prise en main pour les administrateurs

Les administrateurs d’Analytics sont chargés de choisir la méthode de mise en oeuvre la plus appropriée pour leur entreprise.

Une fois Adobe Analytics mis en oeuvre, les administrateurs doivent effectuer diverses tâches de configuration pour s’assurer que les analystes et les utilisateurs finaux tirent pleinement parti d’Adobe Analytics.

#### Déterminer les types de données à collecter

Adobe Analytics vous permet de collecter des données à partir de plusieurs types de canaux et de les rassembler pour fournir des informations client en temps réel significatives.

Voici quelques-uns des canaux pris en charge pour la collecte des données :

* Téléphones mobiles

* L&#39;Internet des objets

* TV

* assistants vocaux

* Voitures connectées

* Et plus encore (de nouveaux canaux pris en charge sont ajoutés régulièrement)

La variable [méthode de mise en oeuvre](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=fr) vous choisissez de déterminer le type de données pouvant être collectées.

#### Mise en œuvre d’Adobe Analytics

Plusieurs méthodes de mise en oeuvre sont disponibles lors de la mise en oeuvre d’Adobe Analytics sur votre site web ou application mobile.

Pour plus d’informations sur chaque méthode disponible, voir [Mise en oeuvre d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=fr).

| | Méthodes de mise en œuvre |
|---------|---------|
| **Sites web** | <ul><li>Extension SDK Web (recommandée)</li><li>SDK Web</li><li>Extension Analytics</li><li>Code JavaScript hérité</li></ul> |
| **applications mobiles ;** | <ul><li>Extension SDK Mobile (recommandée)</li><li>Extension Analytics</li></ul> |

{style="table-layout:auto"}

#### Configuration dʼAdobe Analytics

Les administrateurs d’Analytics doivent effectuer les tâches suivantes avant de mettre Adobe Analytics à la disposition des utilisateurs de l’entreprise :

| Tâche | Utilisation prévue | Informations supplémentaires |
|---------|----------|---------|
| Définition des rôles d’administrateur | Adobe Analytics prend en charge différents types d’administrateurs | [Rôles d’administrateur dans Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Définition des autorisations | Les administrateurs d’Analytics doivent affecter des profils de produit dans le Admin Console pour Adobe Analytics, les outils de suites de rapports et les outils Analytics. | [Autorisations Analytics dans l’Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=fr) |
| Configurer des suites de rapports et définir des paramètres pour votre entreprise | Une suite de rapports est un ensemble de données utilisé par Adobe Analytics pour générer des rapports.<p>Les administrateurs peuvent également configurer [suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=fr) pour segmenter davantage les données.</p> | <ul><li>[Création d’une suite de rapports](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Présentation des paramètres de l’entreprise](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Importer des données | Les sources de données Adobe Analytics vous permettent d’importer des données en ligne ou hors ligne supplémentaires pour la création de rapports. | [Présentation des sources de données](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Classification des données avec des classifications | Les classifications vous permettent de classer les données afin de mieux utiliser les variables, ce qui vous permet d’inclure plus de contenu dans une seule variable. | |
| Gérer les composants | Utilisez le dictionnaire de données et les zones de gestion pour chaque type de composant pour définir les composants disponibles dans votre implémentation Analytics, ainsi que ceux qui sont approuvés pour votre organisation.<p>Il doit s’agir d’une activité continue visant à vous assurer que les composants sont utilisés efficacement dans votre entreprise. </p> | <ul><li>[Présentation du dictionnaire de données](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=fr)</li><li>[Gestionnaire de mesures calculées](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Gestion des segments](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=fr)</li><li>[Création de périodes personnalisées](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=fr)</li></ul> |
| Détection des anomalies et analyse des contributions | | |
| Segmentation avancée | | |
| Publication d’audiences sur Audience Manager | | |
| Attribution | | |
| Gestionnaire des activités de rapport | | |
| Intégrations | Vous pouvez afficher des informations provenant d’autres applications dans Adobe Analytics. <p>Voici quelques intégrations courantes :</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=fr">Media Analytics</a></li> | |

{style="table-layout:auto"}

### Prise en main d’Analytics

Quoique tout membre d’une entreprise puisse utiliser Adobe Analytics pour obtenir des informations exploitables sur le comportement des clients sur plusieurs sites web et applications, Adobe Analytics est conçu en tenant compte des analystes de données.

Vous trouverez ci-dessous les principales tâches et fonctionnalités que les analystes doivent connaître afin de tirer pleinement parti d’Adobe Analytics et d’Analysis Workspace.

| Fonctionnalité | Utilisation prévue | Informations supplémentaires |
|---------|----------|---------|
| Création et partage de projets dans Analysis Workspace | Analysis Workspace est un outil de navigation flexible qui vous permet de créer rapidement des analyses et de partager des informations. L’interface par glisser-déposer vous permet de concevoir votre analyse, d’ajouter des visualisations pour donner vie aux données, de traiter un jeu de données, de partager et de planifier des projets avec toute personne de votre organisation.<p>Les analystes de données sont souvent chargés de créer des projets dans Analysis Workspace pour les utilisateurs de leur entreprise.</p><p>Une fois les projets créés, les analystes partagent ces projets avec le [utilisateurs finaux](#end-users)(non analystes) de leurs organisations qui ont demandé les données et les ont aidées à comprendre comment les interpréter.</p> | <ul><li>[Création de projets](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Partage de projets](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Attribution | Les analystes peuvent personnaliser la manière dont les éléments de dimension obtiennent du crédit pour les événements de succès en utilisant divers modèles d’attribution et intervalles de recherche en amont dans Analysis Workspace.<p>Les modèles d’attribution linéaire accordent le même crédit à chaque point de contact menant à une conversion, tandis que Première touche accorde un crédit complet au point de première touche. De nombreux autres modèles d’attribution sont disponibles, y compris le modèle algorithmique, qui utilise des techniques statistiques pour déterminer de manière dynamique la distribution optimale du crédit. </p> | [Modèles d’attribution et fenêtres de recherche arrière](/help/analyze/analysis-workspace/attribution/models.md) |
| Détection des anomalies | Dans Analysis Workspace, la modélisation statistique détecte automatiquement des tendances inattendues dans vos données en analysant les mesures et en établissant une plage de valeurs inférieure, supérieure et attendue. En cas de pic ou de creux inattendu, le système vous en avertit par le biais du rapport. | [Détection des anomalies - Aperçu](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Analyse des contributions | Utilisez Analysis Workspace pour découvrir des schémas masqués dans vos données afin d’expliquer les anomalies statistiques et d’identifier les corrélations sous-jacentes aux actions inattendues des clients, aux valeurs hors limites et aux pics ou creux soudains des mesures dans les segments d’audience. | [Analyse des contributions - Aperçu](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Alertes intelligentes | Créez et gérez des alertes basées sur des anomalies de données et des alertes &quot;empilées&quot; qui capturent plusieurs mesures dans une seule alerte. | [Alertes intelligentes - Aperçu](help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Exportation des données | Les flux de données et de Data Warehouse vous permettent d’exporter des données vers différentes destinations de cloud, telles que Google Cloud Platform, Azure RBAC, Azure SAS et Amazon S3. | [Guide d’exportation Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=fr) |
| Activity Map | Activity Map est une application Adobe Analytics conçue pour établir un classement de l’activité des liens à l’aide de superpositions visuelles et pour fournir un tableau de bord d’analyses en temps réel visant à contrôler l’engagement du public de vos pages web.<p>Activity Map vous permet de configurer différents affichages afin d’identifier visuellement l’accélération de l’activité des clients, de quantifier les initiatives de marketing et d’agir sur les besoins et les comportements d’audience.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=fr) |
| Report Builder | Le Report Builder est un complément pour Microsoft Excel. Report Builder vous permet de créer des demandes personnalisées à partir des données Adobe Analytics insérées dans vos feuilles de calcul Excel. Ces demandes peuvent référencer des cellules de manière dynamique dans votre feuille de calcul. Vous pouvez, en outre, mettre à jour et personnaliser la manière dont le Report Builder présente les données. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=fr) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

### Prise en main pour les utilisateurs finaux

Les utilisateurs finaux qui ne sont pas des analystes professionnels peuvent soit travailler avec des analystes de leur entreprise pour tirer pleinement parti de la puissance d’Adobe Analytics et d’Analysis Workspace, soit apprendre les bases d’Analysis Workspace afin de commencer à obtenir des informations exploitables sur leurs clients.

#### Utilisation d’analystes

En règle générale, les utilisateurs d’une entreprise qui souhaitent en savoir plus sur le comportement des clients sur leurs différents sites ne sont pas des analystes professionnels.

Idéalement, ces utilisateurs doivent travailler avec [analystes](#analysts) au sein d’une organisation pour :

1. Définissez les exigences des analyses en expliquant à l’analyste ce qu’il espère apprendre sur les clients.

1. Examinez les analyses pour vérifier qu&#39;elles répondent aux objectifs.

1. Discuter des données obtenues dans les analyses.

1. Modifiez les analyses selon vos besoins au fil du temps.

#### Création d’analyses dans Analysis Workspace

Il n’est pas nécessaire d’être un analyste de données pour obtenir des informations exploitables d’Adobe Analytics.

Certains utilisateurs peuvent trouver utile de travailler avec un analyste de données pour configurer un projet dans Analysis Workspace et expliquer comment interpréter les données, comme décrit dans la section [Utilisation d’analystes](#work-with-analysts); d’autres utilisateurs peuvent être à l’aise pour construire le projet et interpréter les données eux-mêmes.

Analysis Workspace vous permet de créer rapidement des analyses pour recueillir des informations, puis de les partager avec d’autres personnes. L’interface de navigateur par glisser-déposer vous permet de concevoir votre analyse, d’ajouter des visualisations pour donner vie aux données, de traiter un jeu de données et de partager et de planifier des projets avec toute personne de votre choix.

Pour plus d’informations sur la création d’analyses dans Analysis Workspace, voir [Présentation d’Analysis Workspace](/help/analyze/analysis-workspace/home.md).

### Prise en main pour les développeurs

[Les API Analytics vous permettent d’appeler directement les serveurs d’Adobe afin d’effectuer la plupart des actions que vous pouvez effectuer dans l’interface utilisateur.](https://developer.adobe.com/analytics-apis/docs/2.0/)

Vous pouvez créer des rapports pour explorer vos données, obtenir des informations ou répondre à des questions importantes à leur sujet. Vous pouvez également gérer les composants d’Adobe Analytics, tels que la création de segments ou de mesures calculées.

## Vue d’ensemble des vidéos

Pour en savoir plus sur les principes de base d’Adobe Analytics, consultez cette section *Présentation d’Adobe Analytics - Webinaire Skill Builder* vidéo. La vidéo vous guide tout au long des principes de base de la capture des données, de la manière dont les données sont envoyées à Adobe Analytics et des fonctionnalités de visualisation que vous pouvez utiliser dans Adobe Analytics. La vidéo fournit une base pour créer, déployer, collecter et interpréter les données, ce qui vous permet de fournir des informations pratiques et des recommandations basées sur les données collectées.

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Pour plus d’informations sur l’outil à utiliser, voir la section [Quel outil Adobe Analytics dois-je utiliser ?](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/which-analytics-tool.html?lang=fr).

## Aller plus loin avec le Customer Journey Analytics

Customer Journey Analytics est une solution d’analyse Adobe qui vous permet d’utiliser toute la puissance d’Analysis Workspace avec les données d’Adobe Experience Platform. Elle permet de ventiler, filtrer, interroger et visualiser des données sur plusieurs années, en conjonction avec la capacité de Platform à contenir toutes sortes de schémas et types de données.

Voici quelques avantages de Customer Journey Analytics par rapport à Adobe Analytics :

* **Variables et événements illimités** : Les concepts d’eVars, de props et d’événements n’existent plus. Les données sont principalement axées sur les dimensions et les mesures. Les jeux de données peuvent comporter un nombre illimité de dimensions et de mesures uniques.

* **Valeurs uniques illimitées** : Adobe Experience Platform nʼest soumis à aucune limitation de valeurs uniques.

* **Modification des données historiques** : avec Adobe Experience Platform, les données peuvent être supprimées ou corrigées.

* **Données cross-suites de rapports** : les implémentations existantes de plusieurs jeux de données peuvent être combinées dans Platform.

Pour plus d’informations, voir [Présentation du Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr).

