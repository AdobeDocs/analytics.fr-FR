---
description: Cette section présente des concepts clés liés à Adobe Analytics, une brève description du concept et un lien vers une documentation spécifique comprenant des détails supplémentaires sur le sujet.
seo-description: Cette section présente des concepts clés liés à Adobe Analytics, une brève description du concept et un lien vers une documentation spécifique comprenant des détails supplémentaires sur le sujet.
seo-title: Adobe Analytics - concepts clés
title: Adobe Analytics - concepts clés
uuid: ef 5701 c 5-2 d 3 e -4847-851 f -9312 d 55 db 1 a 8
translation-type: tm+mt
source-git-commit: d7553fb973d4daddc46533f76769b383966c5c7d

---


# Adobe Analytics - concepts clés

Cette section présente des concepts clés liés à Adobe Analytics, une brève description du concept et un lien vers une documentation spécifique comprenant des détails supplémentaires sur le sujet.

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Produit | Description | Lien vers la documentation |
|--- |--- |--- |
| Analysis Workspace | Solution de navigateur pour créer des projets d'analyse personnalisés et fiables et démocratiser les statistiques. Offre plus de flexibilité que les rapports et analyses | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Rapports et analyses (anciennement SiteCatalyst) | Solution de navigateur pour la création de rapports et l'analyse. Outil de démarrage de la solution Analytics. | [Accueil des rapports et analyses](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | Module complémentaire Excel qui vous permet de créer des requêtes personnalisées à partir de données Adobe Analytics et de les visualiser à l'aide de Microsoft Excel. | [Accueil du créateur de rapports](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Analyses ad hoc (anciennement Discover) | Outil Java pour une analyse numérique avancée. Slated for end-of-life au 3 2019. | [Publicité - Accueil des analyses ad hoc](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Outils de données (anciennement Insight) | Permettent de collecter, de traiter, d’analyser et de visualiser des données issues d’interactions d’utilisateurs en ligne et hors ligne sur plusieurs canaux. | [Client Outils de données](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Entrepôt de données | Données brutes non traitées pour le stockage et les rapports personnalisés, que vous pouvez traiter en filtrant les données. Aucun niveau d’accès. | [Accueil de l'entrepôt de données](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | Réunit l’ensemble des fonctionnalités de marketing mobile pour les applications mobiles d’Adobe Experience Cloud, ce qui vous permet d’analyser et d’améliorer l’engagement des utilisateurs de vos applications. | [Accueil des services mobiles](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Connecteurs de données Adobe Exchange (anciennement Genesis) | Importez des données de suivi à partir d'applications tierces dans Analytics pour donner une visibilité de bout en bout aux performances dans un seul et même emplacement. | [Accueil des connecteurs de données](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| Gestion dynamique des balises | Permet de gérer les balises Analytics, Target et autres sur tous vos sites, quel que soit le nombre de domaines. | [Accueil de la gestion dynamique des balises](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | Génération suivante de balises de site Web et de fonctionnalités de gestion du SDK mobile d'Adobe. | [Accueil d'Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Cliquez [ici](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html) pour consulter un glossaire complet des termes d’Adobe Analytics.

| Terme | Description | Lien vers la documentation |
|--- |--- |--- |
| Props (trafic personnalisé) | Dimensions utilisées pour effectuer le suivi de l'activité page par page du trafic. Les props ne persistent pas entre les pages. Applications clés des variables de trafic : <ul><li>Comptage simple pour trouver « le plus populaire » d'une valeur spécifique</li><li>Visibilité de la cheminement des utilisateurs sur votre site </li></ul><br>Exemples de variables de trafic : nom de page, sections du site, navigateurs</br> | [Props](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| Evar (Conversion personnalisée) | Dimensions qui persistent pendant une période que vous personnalisez. Options d’expiration : expiration de l’événement, expiration de la visite ou expiration après x jours ; dépendent du type d’analyse qui sera exécuté sur cette variable.<br>Différences clés entre les evars et les props :</br><ul><li>Les props sont souvent utilisées pour l'analyse du cheminement, car la persistance est supprimée.</li><li>Les evars sont souvent utilisées pour l'analyse de conversion.</li></ul><br>Exemples de variables de conversion : termes de recherche interne, promotions internes, campagnes externes (s.campaign)</br> | [eVars](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Événements/mesures (s. events) | Mesures mesurant les principales actions que les visiteurs doivent entreprendre sur notre site. Il existe trois types d’événements : compteur, numérique et devise. Les événements sont plus utiles s’ils sont ajoutés aux rapports de variable de conversion (eVar). L’eVar fournit des informations qualitatives sur ce qui s’est produit, tandis que l’événement fournit des informations quantitatives. <br>Différences clés entre evars et événements :</br><ul><li>Les evars indiquent qui, quoi ou qui a affecté la conversion</li><li>Les événements mesurent le nombre de conversions ayant eu lieu</li></ul><br>Exemples d’événements de conversion : commandes, débuts d’application, pistes et recettes.</br> | [Evénements](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| Composants | Dimensions, mesures, segments et granularités temporelles (plages de dates) que vous pouvez faire glisser sur un projet. | [Composants](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| Dimensions | Collecte des evars, props, classifications et valeurs collectées par Adobe standard. | [Dimensions](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| Mesures | Collection d'événements implémentés et de mesures calculées. | [Mesures](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| Mesures calculées | Capacité à dériver des mesures personnalisées provenant de mesures existantes capturées par l'intermédiaire de votre implémentation. | [Mesures calculées](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| Segments | Capacité de compiler, de gérer, de partager et d’appliquer des segments d’audience puissants et cadrés pour vos rapports Analytics. Les segments sont partagés à l’échelle des produits Analytics et peuvent aussi l’être à l’échelle d’Experience Cloud. | [Segmentation](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| Heure (plages de dates) | Capacité à filtrer la date à une période donnée et à créer des plages de dates personnalisées qui peuvent être réutilisées dans votre analyse. | [Plages de dates](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| Visualisations | Des visuels riches qui peuvent vous aider à donner vie à vos projets. | [Visualisations](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| Traitement | Possibilité de limiter les composants accessibles dans un projet ou une suite de rapports virtuelle. | [Curationcomparaison des courbes de projet](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## Key reports {#concept_216E78AD39DD453D940AE857F4C7D4DF}

| Rapport | Description | Lien vers la documentation |
|--- |--- |--- |
| Liste complète des dimensions / rapports | Définition de toutes les dimensions et rapports dans Adobe Analytics. | [Dimensions](https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html) |
| Advertising Analytics | Analysez l'ensemble de vos données de recherche payante Google et Bing - côté - dans Adobe Analytics. Les dimensions créées par le biais de l'intégration incluent Plate-forme publicitaire, Mot-clé, Type de correspondance, etc. Les mesures créées sont des impressions AMO, des clics AMO, des coûts AMO, Avg. Position et Moy. de qualité AMO. | [Advertising Analytics](https://docs.adobe.com/help/en/analytics/integration/advertising-analytics/overview.html) |
| Audience Analytics | Enrichir les accès Analytics entrants avec l'appartenance d'audience d'un utilisateur dans AAM. vous pouvez incorporer des données d'audience AAM telles que des données démographiques (par exemple, sexe ou niveau de revenu), des informations psychographiques (intérêts et hobbies, par exemple), des données de gestion de la relation client et des données d'impression publicitaire dans un flux de travaux Analytics. Les dimensions créées par l'intermédiaire de cette intégration sont ID d'audience et nom du public. | [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| Attribution IQ | Vous permet de comprendre à quel point l'engagement a lieu dans tout le parcours des clients, en identifiant intelligemment les points de flou qui incitent les clients à cibler les résultats et en optimisant efficacement les initiatives marketing. Les modèles incluent first, last, linear, participation, j-shape, inverse j-shape, u-shape, same touch, custom et time collapable. | [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) |
| Détection des anomalies | Méthode statistique permettant de déterminer la modification d'une mesure donnée par rapport aux données précédentes. La publicité est activée par défaut pour toutes les visualisations de tendances dans Analysis Workspace. | [Détection des anomalies](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) |
| Analyse des contributions | Explore la « raison » derrière les anomalies qui se produisent en exécutant une analyse automatisée de chaque mesure et dimension auxquelles vous avez accès. | [Analyse des contributions](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) |
| Analyse des cohortes | Une cohorte est un groupe de personnes partageant des caractéristiques communes au cours d'une période spécifiée. Aide d'analyse des cohortes dans l'analyse de la rétention et de l'attribut de vos utilisateurs. | [Analyse des cohortes](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) |
| Rapports Parcours client | Affiche des informations sur le chemin emprunté par vos utilisateurs sur votre site ou votre application. La prop, evars et événements peuvent être utilisés dans cette analyse dans Analysis Workspace. | [Cheminement Analysis Workspace Analysis](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[Workspace workflows](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[et cheminement Analytics](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-paths.html) |
| Canaux marketing | Ces rapports permettent de comprendre quels canaux externes orientent les utilisateurs vers votre site et lesquels sont plus efficaces pour engendrer une conversion. Les vues d’attribution Première touche et Dernière touche sont fournies. C’est le rapport de source de trafic externe privilégié dans Adobe Analytics (plutôt que les campagnes ou les sources de trafic), car il fournit la présentation la plus complète au niveau des canaux payants et organiques. | [Canaux marketing](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html) |
| Mobile | Présente des informations au sujet des sites web accessibles sur un appareil mobile ou une tablette. | [Rapport Mobile | (https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-mobile.html) |
| Applications mobiles | Présentent des informations d’utilisation de base liées à vos applications mobiles. Ces rapports sont disponibles une fois notre SDK mis en œuvre et la création de rapports activée.  En outre, Adobe Mobile Services a créé une interface distincte d’application mobile qui fournit des données d’application plus complètes, ce qui vous permet de comprendre et d’améliorer l’interaction des utilisateurs avec vos applications.  Access the interface [here](https://mobilemarketing.adobe.com). | [Services mobiles Adobe](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) | Produits | Identifient la manière dont les produits individuels et groupes de produits (catégories) influencent vos différentes mesures de conversion, comme les recettes ou les passages en caisse. | [Rapport Produits](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-products.html) |
| Comparaison des segments | Détecte les différences les plus importantes sur le plan statistique entre les segments grâce à une analyse automatisée de chaque mesure et dimension auxquelles vous avez accès. | [Comparaison de segments](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) |
| Rapport Contenu du site | Présente des informations sur les pages et les sections les plus actives de votre site et sur les serveurs les plus sollicités. | [Rapport Contenu du site](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-content.html) |
| Rapport Mesures du site | Présentent les informations quantitatives au sujet de votre site web : visiteurs uniques, commandes, recettes, etc. Chaque mesure peut être placée dans d’autres rapports dépendant des éléments. | [Rapport Mesures du site](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-metrics.html) |
| Profil du visiteur | Ces rapports vous aident à identifier des modèles d’achat de clients à partir de catégories variées de profils ; par exemple, des pays, états, codes postaux et domaines. | [Profil du visiteur](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-profile.html) |
| Rétention des visiteurs | Présente des informations liées à la fidélité de vos clients, par exemple combien de visiteurs sont revenus sur votre site et à quelle fréquence. | [Rétention des visiteurs](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-retention.html) |
| Lien du projet, partage et planification | Méthodes permettant d’enregistrer ou de partager votre projet avec d’autres personnes dans l’interface Analytics. | [Envoi et planification de fichiers](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) |


## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Nom de la mesure | Définition | Lien vers la documentation |
|---|---|---|
| Liste complète des mesures | Définition de toutes les mesures dans Adobe Analytics. | [Présentation des mesures](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-overview.html) |
| Visiteurs uniques | Nombre de visiteurs dédupliqués sur le site web au cours d’une période donnée. | [Visiteurs uniques](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html) |
| Visites | Séquence de pages vues lors d’une session unique. La visite commence quand une personne voit une page pour la première fois sur le site et se termine après 30 minutes d’inactivité. | [Visites](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-visit.html) |
| Pages vues | Une page vue survient lorsqu’un visiteur accède à une page de votre site web. | [Pages vues](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-page-view.html) |
| Instances | Nombre de fois où la variable a été définie. Chaque fois qu’Adobe Analytics voit une valeur dans une variable, les instances sont incrémentées de 1 dans le rapport concerné. | [Instances](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-instance.html) |
| Occurrences | Nombre de fois où une variable a été définie ou conservée. | [Occurrences](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) |

## Options d'importation {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Option | Description | Lien vers la documentation |
|---|---|---|
| Importateur de classifications | Importez par navigateur ou transfert FTP des métadonnées par rapport aux dimensions capturées. Méthode manuelle comparée au créateur de règles. | [Importateur de classifications](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| Créateur de règles | Créez automatiquement des classifications de métadonnées des dimensions d’après les règles définies par l’utilisateur. | [Créateur de règles de classification](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| Attributs du client | Données de gestion de la relation client transférées dans Experience Cloud à utiliser dans Adobe Analytics et Adobe Target. | [Attributs du client](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) |
| Sources de données | Les mesures hors ligne Impor dans Analytics par rapport aux dimensions ou simplement par jour. | [Sources de données](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html) |
| Connecteurs de données Adobe Exchange | See [Adobe Analytics Tools](../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B). |  |
| Intégrations natives | Analyses d'audience et publication Analytics. | Voir la section « Rapports clés ». |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

| Options | Description |  |
|--- |--- |--- |
| Téléchargements et planification de l'interface utilisateur | Exportation de données d'Analysis Workspace au format CSV ou PDF | [Téléchargement de fichiers PDF ou CSV](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/download-send.html) |
| Report Builder | Voir Outils Analytics. | - |
| API Analytics | Créez vos propres requêtes personnalisées des données Analytics. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Voir Outils Analytics. | - |
| Flux de données Analytics | Manière la plus granulaire de récupérer des données dans Analytics. Configurez un flux au niveau des accès en dehors d’Analytics. | [Flux de données Analytics](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/get-started/data-feed-overview.html) |


## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Méthode/ressource | Description | Lien vers la documentation |
|--- |--- |--- |
| Ressources pour les développeurs | Documentation qui décrit les bibliothèques accessibles pour la collecte de données Analytics sur toutes les plateformes disponibles (web, application mobile, vidéo, flash, etc.). | [Documentation destinée aux développeurs](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Guide de mise en œuvre | Description des variables de collecte de données et informations détaillées sur l’implémentation du code de collecte de données dans JavaScript. | [Guide de mise en œuvre](https://docs.adobe.com/content/help/en/analytics/implementation/home.html) |
| AppMeasurement (s_code) | Gestion globale des variables. | [AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) |
| SDK d’application | Package personnalisé qui comprend une version prérenseignée du fichier de configuration pour les applications. | <ul><li>[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/en/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM et Adobe Launch | Voir Outils Analytics. |  |
| VISTA | Permet d'appliquer une logique côté serveur pour modifier ou segmenter les données lors de leur collecte. | [Règles VISTA](https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html) |
| Règles de traitement | Possibilité de définir, de modifier et de copier des variables dans l'interface utilisateur d'Analytics pour modifier les données collectées. | [Règles de traitement](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| Options de débogage | Plusieurs débogueurs et renifleurs de paquets permettent de valider votre implémentation, y compris le débogueur Adobe Experience Cloud. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en) |
| API d’insertion de données | L'API d'insertion de données fournit un mécanisme de collecte et d'envoi de données côté serveur aux serveurs Experience Cloud. Au lieu d'utiliser des balises JavaScript sur chaque page Web pour transmettre des données visiteur aux serveurs Experience Cloud, la collecte de données côté serveur collecte les données uniquement en fonction des demandes de navigateur Web et des réponses du serveur Web. | [Procédure d'implémentation de l'API d'insertion de données Adobe Analytics à l'aide de POST](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
