---
description: Cette section présente des concepts clés liés à Adobe Analytics, une brève description du concept et un lien vers une documentation spécifique comprenant des détails supplémentaires sur le sujet.
title: Adobe Analytics – Concepts clés
translation-type: ht
source-git-commit: 232a8376d605fc2345b16fc6579b77dbe2eb7709
workflow-type: ht
source-wordcount: '1864'
ht-degree: 100%

---


# Adobe Analytics – Concepts clés

Cette section présente des concepts clés liés à Adobe Analytics, une brève description du concept et un lien vers une documentation spécifique comprenant des détails supplémentaires sur le sujet.

## Outils Analytics {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Product | Description | Lien vers la documentation |
| --- | --- | --- |
| Analysis Workspace | Solution de navigateur pour créer des projets d’analyse personnalisés et fiables et démocratiser les informations. Offre une meilleure flexibilité que Reports and Analytics. | [Accueil d’Analysis Workspace](/help/analyze/analysis-workspace/home.md) |
| Reports and Analytics (anciennement SiteCatalyst) | Solution de navigateur pour la création de rapports et l’analyse. Outil de démarrage de la solution Analytics. | [Accueil de Reports and Analytics](/help/analyze/reports-analytics/getting-started.md) |
| Report Builder | Module complémentaire Excel qui permet de créer des requêtes personnalisées à partir de données Adobe Analytics et de les visualiser à l’aide de Microsoft Excel. | [Accueil de Report Builder](/help/analyze/report-builder/home.md) |
| Ad Hoc Analysis (anciennement Discover) | Outil Java pour les analyses digitales avancées. | [Accueil d’Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md) |
| Data Workbench (anciennement Insight) | Permet de collecter, de traiter, d’analyser et de visualiser des données issues d’interactions d’utilisateurs en ligne et hors ligne sur plusieurs canaux. | [Client Data Workbench](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/client/t-open-ins.html) |
| Data Warehouse | Données brutes non traitées pour le stockage et les rapports personnalisés, que vous pouvez traiter en filtrant les données. Aucun niveau d’accès. | [Accueil de Data Warehouse](/help/export/data-warehouse/data-warehouse.md) |
| Adobe Mobile Services | Réunit l’ensemble des fonctionnalités de marketing mobile pour les applications mobiles d’Adobe Experience Cloud, ce qui vous permet d’analyser et d’améliorer l’engagement des utilisateurs de vos applications. | [Accueil de Mobile Services](https://docs.adobe.com/content/help/fr-FR/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors (anciennement Genesis) | Importe dans Analytics des données de suivi issues d’applications tierces, permettant ainsi de bénéficier d’une visibilité de bout en bout au même endroit. | [Aide de Data Connectors](/help/import/data-connectors/data-connectors-eol.md) |
| Dynamic Tag Management (DTM) | Permet de gérer les balises Analytics, Target et autres sur tous vos sites, quel que soit le nombre de domaines. | [Accueil de DTM](/help/implement/other/dtm/dtm-implementation-overview.md) |
| Adobe Launch | Nouvelle génération de fonctionnalités de gestion de SDK mobile et de balises de sites web. | [Accueil d’Adobe Launch](https://docs.adobe.com/content/help/fr-FR/launch/using/overview.html) |

## Terminologie clé {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Cliquez [ici](/help/technotes/terms.md) pour consulter un glossaire complet des termes d’Adobe Analytics.

| Terme | Description | Lien vers la documentation |
| --- | --- | --- |
| Props (trafic personnalisé) | Dimensions utilisées pour effectuer un suivi page par page de l’activité du trafic sur le site. Les props ne persistent pas entre les pages. Applications clés des variables de trafic : <ul> <li>Comptage simple pour rechercher la valeur « la plus appréciée »</li> <li>Visibilité sur le chemin emprunté par les utilisateurs pour accéder à votre site</li> </ul> <br> Exemples de variables de trafic : nom de page, sections du site, navigateurs. | [Props](/help/admin/admin/c-traffic-variables/traffic-var.md) |
| eVar (conversion personnalisée) | Dimensions qui persistent pendant la période de votre choix. Options d’expiration : expiration de l’événement, expiration de la visite ou expiration après X jours ; dépendent du type d’analyse qui sera exécuté sur cette variable. <br> Principales différences entre eVars et props : <ul> <li>Les props sont souvent utilisées pour l’analyse du cheminement, car la persistance est supprimée.</li> <li>Les eVars sont souvent utilisées pour les analyses de conversion.</li> </ul> <br> Exemples de variables de conversion : termes de recherche interne, promotions internes, campagnes externes (s.campaign). | [eVars](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) |
| Événements/Mesures (s.events) | Mesures qui observent les principales actions souhaitées de la part des visiteurs sur le site. Il existe trois types d’événements : compteur, numérique et devise. Les événements sont plus utiles s’ils sont ajoutés aux rapports de variable de conversion (eVar). L’eVar fournit des informations qualitatives sur ce qui s’est produit, tandis que l’événement fournit des informations quantitatives. <br> Principales différences entre les eVars et les événements : <ul> <li>Les eVars indiquent qui, quoi, ou ce qui a affecté la conversion.</li> <li>Les événements mesurent le nombre de conversions qui ont eu lieu</li> </ul> <br> Exemples d’événements de conversion : commandes, débuts d’application, pistes et recettes. | [Événements](/help/admin/admin/c-success-events/success-event.md) |
| Composants | Dimensions, mesures, segments et granularités temporelles (périodes) que vous pouvez faire glisser sur un projet. | [Composants](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| Dimensions | Collection d’eVars, de props, de classifications et de valeurs Adobe standard collectées. | [Dimensions](/help/components/dimensions/overview.md) |
| Mesures | Collection d’événements implémentés et de mesures calculées. | [Mesures](/help/analyze/analysis-workspace/components/apply-create-metrics.md) |
| Mesures calculées | Possibilité de dériver des mesures personnalisées des mesures existantes capturées via votre mise en œuvre. | [Mesures calculées](/help/components/c-calcmetrics/cm-overview.md) |
| Segments | Capacité de compiler, de gérer, de partager et d’appliquer des segments d’audience puissants et cadrés pour vos rapports Analytics. Les segments sont partagés à l’échelle des produits Analytics et peuvent aussi l’être à l’échelle d’Experience Cloud. | [Segmentation](/help/components/segmentation/seg-home.md) |
| Heure (périodes) | Possibilité de filtrer la date à n’importe quelle période et de créer des périodes personnalisées qui peuvent être réutilisées dans votre analyse. | [Périodes](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) |
| Visualisations | Des visuels riches qui peuvent donner vie aux données dans vos projets. | [Visualisations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| Traitement | Possibilité de limiter les composants accessibles dans un projet ou une suite de rapports virtuelle. | [Traitement des suites de rapports virtuelles](/help/components/vrs/vrs-components.md) <br> [Traitement du projet](/help/analyze/analysis-workspace/curate-share/curate.md) |

## Rapports clés

| Rapport | Description | Lien vers la documentation |
| --- | --- | --- |
| Liste complète des dimensions / rapports | Définition de toutes les dimensions et rapports dans Adobe Analytics. | [Dimensions](/help/components/dimensions/overview.md) |
| Advertising Analytics | Analysez côte à côte toutes vos données de référencement payant Google et Bing dans Adobe Analytics. Les dimensions créées par le biais de l’intégration incluent la plateforme d’annonces publicitaires, le mot-clé, le type de correspondance, etc. Les mesures créées sont les suivantes : impressions AMO, clics AMO, coût AMO, position moyenne et note de qualité moyenne. | [Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) |
| Audience Analytics | Enrichissez les accès Analytics entrants avec l’appartenance d’un utilisateur à l’audience dans AAM. Vous pouvez incorporer des données d’audience AAM telles que des données démographiques (par exemple, le sexe ou le niveau de revenu), des données psychographiques (par exemple, les centres d’intérêt et les loisirs), des données de gestion de la relation client ou des données d’impression publicitaire dans n’importe quel workflow d’Analytics. Les dimensions créées à l’aide de cette intégration sont l’ID et le nom de l’audience. | [Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md) |
| Attribution IQ | Vous permet de comprendre comment un engagement significatif se manifeste tout au long du parcours client, en identifiant intelligemment les points d’inflexion qui amènent les clients à cibler les résultats et en optimisant efficacement les initiatives marketing. Les modèles comprennent : premiers, derniers, linéaires, participation, formes j, formes j inversées, formes u, même touche, personnalisations et atténuation temporelle. | [Attribution IQ](/help/analyze/analysis-workspace/c-panels/attribution.md) |
| Détection des anomalies | Méthode statistique pour déterminer la modification d’une mesure donnée par rapport à des données antérieures. La détection des anomalies est activée par défaut pour toutes les visualisations de tendances dans Analysis Workspace. | [Détection des anomalies](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Analyse des contributions | Cherche à trouver le « pourquoi » des anomalies qui se produisent en exécutant une analyse automatisée de chaque mesure et dimension auxquelles vous avez accès. | [Analyse des contributions](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Analyse des cohortes | Une cohorte est un groupe de personnes partageant des caractéristiques communes au cours d’une période spécifique. L’analyse des cohortes aide à analyser la rétention et la perte d’utilisateurs. | [Analyse des cohortes](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |
| Rapports sur les parcours clients | Affiche des informations sur le chemin suivi par vos utilisateurs sur votre site ou application. Les variables prop, eVar et les événements peuvent être utilisés dans cette analyse dans Analysis Workspace. | [Abandon dans Analysis Workspace](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) <br> [Flux dans Analysis Workspace](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) <br> [Cheminement dans Reports and Analytics](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
| Canaux marketing | Ces rapports permettent de comprendre quels canaux externes orientent les utilisateurs vers votre site et lesquels sont plus efficaces pour engendrer une conversion. Les vues d’attribution Première touche et Dernière touche sont fournies. C’est le rapport de source de trafic externe privilégié dans Adobe Analytics (plutôt que les campagnes ou les sources de trafic), car il fournit la présentation la plus complète au niveau des canaux payants et organiques. | [Canaux marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) |
| Mobile | Présente des informations au sujet des sites web accessibles sur un appareil mobile ou une tablette. | [Rapport Mobile](/help/components/dimensions/mobile-dimensions.md) |
| Application mobile | Présentent des informations d’utilisation de base liées à vos applications mobiles. Ces rapports sont disponibles une fois notre SDK mis en œuvre et la création de rapports activée.  En outre, Adobe Mobile Services a créé une interface distincte d’application mobile qui fournit des données d’application plus complètes, ce qui vous permet de comprendre et d’améliorer l’interaction des utilisateurs avec vos applications.  Vous pouvez accéder à l’interface [ici](https://mobilemarketing.adobe.com). | [Adobe Mobile Services](https://docs.adobe.com/content/help/fr-FR/mobile-services/using/home.html) |
| Produits | Identifient la manière dont les produits individuels et groupes de produits (catégories) influencent vos différentes mesures de conversion, comme les recettes ou les passages en caisse. | [Rapport Produits](/help/components/dimensions/product.md) |
| Comparaison de segments | Détecte les différences les plus importantes sur le plan statistique entre deux segments au moyen d’une analyse automatisée de chaque mesure et dimension auxquelles vous avez accès. | [Comparaison de segments](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) |
| Rapport Contenu du site | Présente des informations sur les pages et les sections les plus actives de votre site et sur les serveurs les plus sollicités. | [Rapport Contenu du site](/help/components/dimensions/page.md) |
| Rapport Mesures du site | Présentent les informations quantitatives au sujet de votre site web : visiteurs uniques, commandes, recettes, etc. Chaque mesure peut être placée dans d’autres rapports dépendant des éléments. | [Rapport Mesures du site](/help/components/metrics/overview.md) |
| Profil du visiteur | Ces rapports vous aident à identifier des modèles d’achat de clients à partir de catégories variées de profils ; par exemple, des pays, états, codes postaux et domaines. | [Profil du visiteur](/help/components/dimensions/language.md) |
| Rétention des visiteurs | Présente des informations liées à la fidélité de vos clients, par exemple combien de visiteurs sont revenus sur votre site et à quelle fréquence. | [Rétention des visiteurs](/help/components/dimensions/customer-loyalty.md) |
| Lien, partage et planification de projet | Méthodes permettant d’enregistrer ou de partager votre projet avec d’autres personnes dans l’interface Analytics. | [Envoi et planification de fichiers](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md) |

## Mesures clés {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Nom de la mesure | Définition | Lien vers la documentation |
| --- | --- | --- |
| Liste complète des mesures | Définition de toutes les mesures dans Adobe Analytics. | [Mesures - Aperçu](/help/components/metrics/overview.md) |
| Visiteurs uniques | Nombre de visiteurs dédupliqués sur le site web au cours d’une période donnée. | [Visiteurs uniques](/help/components/metrics/unique-visitors.md) |
| Visites | Séquence de pages vues lors d’une session unique. La visite commence quand une personne voit une page pour la première fois sur le site et se termine après 30 minutes d’inactivité. | [Visites](/help/components/metrics/visits.md) |
| Pages vues | Une page vue survient lorsqu’un visiteur accède à une page de votre site web. | [Pages vues](/help/components/metrics/page-views.md) |
| Instances | Nombre de fois où la variable a été définie. Chaque fois qu’Adobe Analytics voit une valeur dans une variable, les instances sont incrémentées de 1 dans le rapport concerné. | [Instances](/help/components/metrics/instances.md) |
| Occurrences | Nombre de fois où la variable a été définie ou a persisté. | [Occurrences](/help/components/metrics/occurrences.md) |

## Options d’importation {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Option | Description | Lien vers la documentation |
| --- | --- | --- |
| Importateur de classifications | Importez par navigateur ou transfert FTP des métadonnées par rapport aux dimensions capturées. Méthode manuelle comparée au créateur de règles. | [Importateur de classifications](/help/components/classifications/importer/c-working-with-saint.md) |
| Créateur de règles | Créez automatiquement des classifications de métadonnées des dimensions d’après les règles définies par l’utilisateur. | [Créateur de règles de classification](/help/components/classifications/crb/classification-rule-builder.md) |
| Attributs du client | Données de gestion de la relation client transférées vers Experience Cloud pour une utilisation dans Adobe Analytics et Adobe Target. | [Attributs du client](https://docs.adobe.com/content/help/fr-FR/core-services/interface/customer-attributes/attributes.html) |
| Sources de données | Importez des mesures hors ligne dans Analytics en fonction des dimensions ou simplement en fonction du jour. | [Sources de données](/help/import/c-data-sources/datasrc-home.md) |
| Adobe Exchange Data Connectors | Voir [Outils Analytics.](/help/import/data-connectors/data-connectors-eol.md) |  |
| Intégrations natives | Audience Analytics et Advertising Analytics. | Voir la section « Rapports clés ». |

## Options d’exportation {#concept_C62B688E259141CF92C048E8110464BE}

| Option | Description | Lien vers la documentation |
| --- | --- | --- |
| Téléchargements de l’interface utilisateur et planification | Export de données d’Analysis Workspace au format CSV ou PDF. | [Téléchargement de fichiers PDF ou CSV](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Voir Outils Analytics. |  |
| API Analytics | Créez vos propres requêtes personnalisées des données Analytics. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Voir Outils Analytics. |  |
| Flux de données Analytics | Manière la plus granulaire de récupérer des données dans Analytics. Configurez un flux au niveau des accès en dehors d’Analytics. | [Flux de données Analytics](/help/export/analytics-data-feed/data-feed-overview.md) |

## Collecte de données et validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Méthode/ressource | Description | Lien vers la documentation |
| --- | --- | --- |
| Ressources pour les développeurs | Documentation qui décrit les bibliothèques accessibles pour la collecte de données Analytics sur toutes les plateformes disponibles (web, application mobile, vidéo, flash, etc.). | [Documentation pour les développeurs](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Guide de mise en œuvre | Description des variables de collecte de données et informations détaillées sur l’implémentation du code de collecte de données dans JavaScript. | [Guide de mise en œuvre](/help/implement/home.md) |
| AppMeasurement (s_code) | Gestion globale des variables. | [AppMeasurement](/help/implement/js/migrate-from-hcode.md) |
| SDK d’application | Package personnalisé qui comprend une version prérenseignée du fichier de configuration pour les applications. | <ul><li>[iOS](https://docs.adobe.com/content/help/fr-FR/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/fr-FR/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM et Adobe Launch | Voir Outils Analytics. |  |
| VISTA | Permet d’appliquer une logique côté serveur pour modifier ou segmenter les données au fur et à mesure de leur collecte. | [Règles VISTA](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md) |
| Règles de traitement | Permet de définir, modifier et copier des variables dans l’interface utilisateur d’Analytics afin de modifier les données collectées. | [Règles de traitement](/help/admin/admin/c-processing-rules/processing-rules.md) |
| Options de débogage | Plusieurs débogueurs et renifleurs de paquets peuvent vous aider à valider votre mise en œuvre, notamment le débogueur Adobe Experience Cloud. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=fr) |
| API d’insertion de données | L’API d’insertion de données fournit aux serveurs Experience Cloud un mécanisme de collecte et d’envoi de données côté serveur. Plutôt que d’utiliser des balises JavaScript sur chaque page web pour transmettre aux serveurs Experience Cloud les données des visiteurs, la collecte de données côté serveur récupère les données uniquement en fonction des demandes du navigateur et des réponses du serveur. | [Procédure de mise en œuvre de l’API d’insertion de données d’Adobe Analytics à l’aide de POST](https://helpx.adobe.com/fr/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
