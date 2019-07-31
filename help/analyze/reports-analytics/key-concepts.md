---
description: Cette section présente des concepts clés liés à Adobe Analytics, une brève description du concept et un lien vers une documentation spécifique comprenant des détails supplémentaires sur le sujet.
seo-description: Cette section présente des concepts clés liés à Adobe Analytics, une brève description du concept et un lien vers une documentation spécifique comprenant des détails supplémentaires sur le sujet.
seo-title: Adobe Analytics - concepts clés
title: Adobe Analytics - concepts clés
uuid: ef 5701 c 5-2 d 3 e -4847-851 f -9312 d 55 db 1 a 8
translation-type: tm+mt
source-git-commit: 9140868f7ccf1f7d8ead45fd0c3db6c9b4133538

---


# Adobe Analytics - concepts clés

Cette section présente des concepts clés liés à Adobe Analytics, une brève description du concept et un lien vers une documentation spécifique comprenant des détails supplémentaires sur le sujet.

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Produit | Description | Lien vers la documentation |
|--- |--- |--- |
| Analysis Workspace | Solution de navigateur pour créer des projets d'analyse personnalisés et fiables et démocratiser les statistiques. Offre plus de flexibilité que les rapports et analyses | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Rapports et analyses (anciennement SiteCatalyst) | Solution de navigateur pour la création de rapports et l'analyse. Outil de démarrage de la solution Analytics. | [https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | Module complémentaire Excel qui vous permet de créer des requêtes personnalisées à partir de données Adobe Analytics et de les visualiser à l'aide de Microsoft Excel. | [https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Analyses ad hoc (anciennement Discover) | Outil Java pour une analyse numérique avancée. Slated for end-of-life au 3 2019. | [https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Outils de données (anciennement Insight) | Permettent de collecter, de traiter, d’analyser et de visualiser des données issues d’interactions d’utilisateurs en ligne et hors ligne sur plusieurs canaux. | [https://marketing.adobe.com/resources/help/en_US/insight/client/](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Entrepôt de données | Données brutes non traitées pour le stockage et les rapports personnalisés, que vous pouvez traiter en filtrant les données. Aucun niveau d’accès. | [https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | Réunit l’ensemble des fonctionnalités de marketing mobile pour les applications mobiles d’Adobe Experience Cloud, ce qui vous permet d’analyser et d’améliorer l’engagement des utilisateurs de vos applications.  Accessible à l’adresse : https://mobilemarketing.adobe.com/ | [https://docs.adobe.com/content/help/en/mobile-services/using/home.html](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Connecteurs de données Adobe Exchange (anciennement Genesis) | Importez des données de suivi à partir d'applications tierces dans Analytics pour donner une visibilité de bout en bout aux performances dans un seul et même emplacement. | [https://marketing.adobe.com/developer/fr/documentation/genesis/c-overview-how-it-works](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| Gestion dynamique des balises | Permet de gérer les balises Analytics, Target et autres sur tous vos sites, quel que soit le nombre de domaines. | [https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | Génération suivante de balises de site Web et de fonctionnalités de gestion du SDK mobile d'Adobe. | [https://docs.adobe.com/content/help/en/launch/using/overview.html](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Cliquez [ici](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html) pour consulter un glossaire complet des termes d’Adobe Analytics.

| Terme | Description | Lien vers la documentation |
|--- |--- |--- |
| Props (trafic personnalisé) | Dimensions utilisées pour effectuer le suivi de l'activité page par page du trafic. Les props ne persistent pas entre les pages. Applications clés des variables de trafic : <ul><li>Comptage simple pour trouver « le plus populaire » d'une valeur spécifique</li><li>Visibilité de la cheminement des utilisateurs sur votre site </li></ul><br>Exemples de variables de trafic : nom de page, sections du site, navigateurs</br> | [https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| Evar (Conversion personnalisée) | Dimensions qui persistent pendant une période que vous personnalisez. Options d’expiration : expiration de l’événement, expiration de la visite ou expiration après x jours ; dépendent du type d’analyse qui sera exécuté sur cette variable.<br>Différences clés entre les evars et les props :</br><ul><li>Les props sont souvent utilisées pour l'analyse du cheminement, car la persistance est supprimée.</li><li>Les evars sont souvent utilisées pour l'analyse de conversion.</li></ul><br>Exemples de variables de conversion : termes de recherche interne, promotions internes, campagnes externes (s.campaign)</br> | [https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Événements/mesures (s. events) | Mesures mesurant les principales actions que les visiteurs doivent entreprendre sur notre site. Il existe trois types d’événements : compteur, numérique et devise. Les événements sont plus utiles s’ils sont ajoutés aux rapports de variable de conversion (eVar). L’eVar fournit des informations qualitatives sur ce qui s’est produit, tandis que l’événement fournit des informations quantitatives. <br>Différences clés entre evars et événements :</br><ul><li>Les evars indiquent qui, quoi ou qui a affecté la conversion</li><li>Les événements mesurent le nombre de conversions ayant eu lieu</li></ul><br>Exemples d’événements de conversion : commandes, débuts d’application, pistes et recettes.</br> | [https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| Composants | Dimensions, mesures, segments et granularités temporelles (plages de dates) que vous pouvez faire glisser sur un projet. | [https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| Dimensions | Collecte des evars, props, classifications et valeurs collectées par Adobe standard. | [https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| Mesures | Collection d'événements implémentés et de mesures calculées. | [https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| Mesures calculées | Capacité à dériver des mesures personnalisées provenant de mesures existantes capturées par l'intermédiaire de votre implémentation. | [https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| Segments | Capacité de compiler, de gérer, de partager et d’appliquer des segments d’audience puissants et cadrés pour vos rapports Analytics. Les segments sont partagés à l’échelle des produits Analytics et peuvent aussi l’être à l’échelle d’Experience Cloud. | [https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| Heure (plages de dates) | Capacité à filtrer la date à une période donnée et à créer des plages de dates personnalisées qui peuvent être réutilisées dans votre analyse. | [https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| Visualisations | Des visuels riches qui peuvent vous aider à donner vie à vos projets. | [https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| Traitement | Possibilité de limiter les composants accessibles dans un projet ou une suite de rapports virtuelle. | [Curationcomparaison des courbes de projet](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |



## Key features {#concept_216E78AD39DD453D940AE857F4C7D4DF}

<table id="table_5CD38BD3BE854E69B6925EA3F02AFC92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rapport </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Lien vers la documentation </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Liste complète des rapports </td> 
   <td colname="col2"> Définition de tous les rapports disponibles dans Adobe Analytics. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/reports_descriptions.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trafic personnalisé (prop) </td> 
   <td colname="col2">Permet d’effectuer un suivi page par page de l’activité du trafic du site. Les props ne persistent pas entre les pages. Applications clés des variables de trafic : 
    <ul id="ul_A935EC5271684B9599F683C7B31400ED"> 
     <li id="li_58E0596050A34ACC821916EA61E946EF">Capturer une valeur qui peut être associée aux pages vues, aux visites, aux visiteurs ou aux instances. </li> 
     <li id="li_2B4C557AAD0544BE8204C0D7CE587175">Rechercher l’élément le plus populaire d’une valeur spécifique. </li> 
     <li id="li_7FA62BE657F047459DF439BFB9F332F5">Déterminer quel est le chemin emprunté par les utilisateurs pour accéder à votre site. </li> 
    </ul> <p>Exemples de variables de trafic : nom de page, sections du site, navigateurs. </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/traffic_var.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversion personnalisée (eVar) </td> 
   <td colname="col2">Sert principalement à créer un rapport sur les événements de conversion et persiste pendant une période que vous personnalisez. Options d’expiration : expiration de l’événement, expiration de la visite ou expiration après x jours ; dépendent du type d’analyse qui sera exécuté sur cette variable. <p>Principales différences entre les variables de conversion et de trafic : </p> 
    <ul id="ul_B0A7482A81B94C5F86C06E5507DB393D"> 
     <li id="li_272E414520AA4603AE5EC397B0F93630"> Les variables de trafic personnalisées dépendent des mesures de trafic, et non de conversion. Elles sont souvent utilisées pour l’analyse du cheminement. </li> 
     <li id="li_EBBF9A35C64845FE9683540DFA89E7E9">Les variables de conversion personnalisées peuvent dépendre du trafic et de la conversion, et sont souvent utilisées pour l’analyse de conversion. </li> 
    </ul> <p>Exemples de variables de conversion : termes de recherche interne, promotions internes, campagnes externes (s.campaign). </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/conversion_var_admin.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événements de succès (s.events) </td> 
   <td colname="col2"> <p>Mesure des principales actions que nous souhaitons voir adopter par les visiteurs sur notre site. </p> <p>Il existe trois types d’événements : compteur, numérique et devise. Les événements sont plus utiles s’ils sont ajoutés aux rapports de variable de conversion (eVar). L’eVar fournit des informations qualitatives sur ce qui s’est produit, tandis que l’événement fournit des informations quantitatives. </p> <p>Principales différences entre les variables de conversion et les événements personnalisés : </p> 
    <ul id="ul_2B95D7437DE444DD9618DBFE6A8612D1"> 
     <li id="li_5951858853334EFA931A5BC57E5C933F">Les variables de conversion indiquent qui ou quoi ou ce qui a affecté la conversion. </li> 
     <li id="li_339755C842714E0DB8DB4DFAA43AB4F7"> Les événements personnalisés mesurent le nombre de conversions ayant eu lieu. </li> 
    </ul> <p>Exemples d’événements de conversion : commandes, débuts d’application, pistes et recettes. </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/success_event.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/success_event.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesures du site </td> 
   <td colname="col2"> Présentent les informations quantitatives au sujet de votre site web : visiteurs uniques, commandes, recettes, etc. Chaque mesure peut être placée dans d’autres rapports dépendant des éléments. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_site_metrics.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/reports_site_metrics.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contenu du site </td> 
   <td colname="col2"> Affiche des informations sur les pages et les sections de votre site qui sont les plus actives et sur les serveurs les plus sollicités. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_site_content.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/reports_site_content.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile </td> 
   <td colname="col2"> Présente des informations au sujet des sites web accessibles sur un appareil mobile ou une tablette. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_mobile.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/reports_mobile.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Applications mobiles </td> 
   <td colname="col2"> <p>Présentent des informations d’utilisation de base liées à vos applications mobiles. Ces rapports sont disponibles une fois notre SDK mis en œuvre et la création de rapports activée. </p> <p>En outre, Adobe Mobile Services a créé une interface distincte d’application mobile qui fournit des données d’application plus complètes, ce qui vous permet de comprendre et d’améliorer l’interaction des utilisateurs avec vos applications. </p> <p>L’interface est accessible à l’adresse suivante : </p> <p><a href="https://mobilemarketing.adobe.com" format="https" scope="external"> https://mobilemarketing.adobe.com</a> </p> </td> 
   <td colname="col3"> <p>Adobe Mobile Services : </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/mobile/</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rapports Chemin </td> 
   <td colname="col2"> Affichent des informations sur l’ordre de consultation des pages de votre site web. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_paths.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/reports_paths.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Produits </td> 
   <td colname="col2"> Identifient la manière dont les produits individuels et groupes de produits (catégories) influencent vos différentes mesures de conversion, comme les recettes ou les passages en caisse. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_products.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/reports_products.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rétention des visiteurs </td> 
   <td colname="col2"> Présente des informations liées à la fidélité de vos clients, par exemple combien de visiteurs sont revenus sur votre site et à quelle fréquence. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_retention.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/reports_visitor_retention.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profil du visiteur </td> 
   <td colname="col2"> Ces rapports vous aident à identifier des modèles d’achat de clients à partir de catégories variées de profils ; par exemple, des pays, états, codes postaux et domaines. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_profile.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/reports_visitor_profile.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Canaux marketing </td> 
   <td colname="col2">Ces rapports permettent de comprendre quels canaux externes orientent les utilisateurs vers votre site et lesquels sont plus efficaces pour engendrer une conversion. Les vues d’attribution Première touche et Dernière touche sont fournies. <p>C’est le rapport de source de trafic externe privilégié dans Adobe Analytics (plutôt que les campagnes ou les sources de trafic), car il fournit la présentation la plus complète au niveau des canaux payants et organiques. </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/mchannel/index.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/mchannel/index.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rapports personnalisés, lien vers les rapports, signets et tableaux de bord </td> 
   <td colname="col2"> Méthodes permettant d’enregistrer ou de partager votre projet avec d’autres personnes dans l’interface Analytics. </td> 
   <td colname="col3">Rapports personnalisés : <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_custom.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/reports_custom.html</a> </p> <p>Lien vers le rapport : </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/t_reports_share_link.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/sc/user/t_reports_share_link.html</a> </p> <p>Signets </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/bookmarks.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/sc/user/bookmarks.html</a> </p> <p>Tableaux de bord </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/dashboard.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/sc/user/dashboard.html</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

<!-- 

key_metrics.xml

 -->

| Nom de la mesure | Définition | Lien vers la documentation |
|---|---|---|
| Liste complète des mesures | Définition de toutes les mesures dans Adobe Analytics. | [https://marketing.adobe.com/resources/help/fr_FR/reference/metrics.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics.html) |
| Visiteurs uniques | Nombre de visiteurs dédupliqués sur le site web au cours d’une période donnée. | [https://marketing.adobe.com/resources/help/fr_FR/reference/metrics_unique_visitors.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_unique_visitors.html) |
| Visites | Séquence de pages vues lors d’une session unique. La visite commence quand une personne voit une page pour la première fois sur le site et se termine après 30 minutes d’inactivité. | [https://marketing.adobe.com/resources/help/fr_FR/reference/metrics_visit.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html) |
| Pages vues | Une page vue survient lorsqu’un visiteur accède à une page de votre site web. | [https://marketing.adobe.com/resources/help/fr_FR/reference/metrics_page_view.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_page_view.html) |
| Instances | Nombre de fois où la variable a été définie. Chaque fois qu’Adobe Analytics voit une valeur dans une variable, les instances sont incrémentées de 1 dans le rapport concerné. | [https://marketing.adobe.com/resources/help/fr_FR/reference/metrics_instance.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_instance.html) |
| Mesures calculées | Mesures personnalisées que vous pouvez créer à partir de mesures existantes. Si, par exemple, vous connaissez les recettes et le nombre de visites, vous pouvez créer une mesure personnalisée pour calculer les recettes moyennes par visite ou les recettes divisées par le nombre de visites (recettes/visites). | [https://marketing.adobe.com/resources/help/fr_FR/analytics/calcmetrics/](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) |

## Options d'importation {#concept_7C6DF03B5F9149E2A77F36C739432059}

<!-- 

import_options.xml

 -->

| Option | Description | Lien vers la documentation |
|---|---|---|
| Importateur de classifications | Importez par navigateur ou transfert FTP des métadonnées par rapport aux dimensions capturées. Méthode manuelle comparée au créateur de règles. | [https://marketing.adobe.com/resources/help/fr_FR/reference/c_working_with_saint.html](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| Créateur de règles | Créez automatiquement des classifications de métadonnées des dimensions d’après les règles définies par l’utilisateur. | [https://marketing.adobe.com/resources/help/fr_FR/reference/classification_rule_builder.html](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| Sources de données | Importez des mesures hors ligne dans Analytics par rapport aux dimensions ou simplement par jour. | [https://marketing.adobe.com/resources/help/en_US/sc/datasources/datasrc_home.html](https://marketing.adobe.com/resources/help/en_US/sc/datasources/datasrc_home.html) |
| Connecteurs de données | Voir [Produits](../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B). |  |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

<!-- 

export_options.xml

 -->

<table id="table_99867D82082D4756872FC3ABD83A33A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Options </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Interface de téléchargements de rapports </td> 
   <td colname="col2"> Manière la plus simple d’exporter des données à partir d’Analytics. </td> 
   <td colname="col3">https://microsite.omniture.com/t2/help/en_US/survey/index.html#Downloading_a_Report_Using_ <p>Basic_Options </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrepôt de données </td> 
   <td colname="col2">Voir <a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">Produits</a>. </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Créateur de rapports </td> 
   <td colname="col2">Voir <a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">Produits</a>. </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> API Analytics </td> 
   <td colname="col2"> Créez vos propres requêtes personnalisées des données Analytics. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/developer/documentation" format="https" scope="external"> https://marketing.adobe.com/developer/fr/documentation</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Flux de données de parcours de navigation </td> 
   <td colname="col2"> Manière la plus granulaire d’obtenir des données à partir d’Analytics. Configurez un flux au niveau de l’accès en dehors d’Analytics. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_reference.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/sc/clickstream/datafeeds_reference.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Planification des données </td> 
   <td colname="col2"> La plupart des options d’exportation d’Adobe Analytics permettent de planifier la distribution des données et des rapports par courrier électronique et FTP. </td> 
   <td colname="col3"> - </td> 
  </tr> 
 </tbody> 
</table>

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

<!-- 

data_collection_and_validation.xml

 -->

<table id="table_53039DCCAC1D47F7A1E3485609D13E4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Méthode/ressource </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Lien vers la documentation </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ressources pour les développeurs </td> 
   <td colname="col2"> Documentation qui décrit les bibliothèques accessibles pour la collecte de données Analytics sur toutes les plateformes disponibles (web, application mobile, vidéo, flash, etc.). </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/developer.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Guide de mise en œuvre </td> 
   <td colname="col2"> Description des variables de collecte de données et informations détaillées sur l’implémentation du code de collecte de données dans JavaScript. </td> 
   <td colname="col3"> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/sc/implement/index.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AppMeasurement (s_code) </td> 
   <td colname="col2"> Gestion globale des variables. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html#" format="html" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/sc/implement/appmeasure_mjs.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SDK d’application </td> 
   <td colname="col2"> Package personnalisé qui comprend une version prérenseignée du fichier de configuration pour les applications. </td> 
   <td colname="col3">iOS : <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=requirements" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/mobile/ios/?f=requirements</a> </p> <p>Android : </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamic Tag Management (DTM) </td> 
   <td colname="col2">Voir <a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">Produits</a>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VISTA </td> 
   <td colname="col2"> Approche côté serveur permettant de renseigner les variables du rapport. Cette technologie exclusive utilise des règles de segmentation des visiteurs pour segmenter, en temps réel, toutes les données en ligne. Ces règles permettent de modifier ou de segmenter les données comme vous le souhaitez, ou presque, sans qu’il faille implémenter une logique complexe sur votre site. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/VISTA.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Règles de traitement </td> 
   <td colname="col2"> Méthode permettant de simplifier la collecte de données et de gérer le contenu envoyé aux rapports par l’intermédiaire de la section Outils d’administration. Ces règles fournissent une interface permettant de définir, de modifier et de copier les variables afin de faciliter l’interaction avec les groupes informatiques et les développeurs web. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/reference/processing_rules.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Options de débogage </td> 
   <td colname="col2"> Plusieurs débogueurs et renifleurs de paquets permettent de valider votre mise en œuvre. Charles est notre outil préféré. Autres outils disponibles : Adobe Debugger, HTTPFox, Firebug, Omnibug, Fiddler et HTTPWatch. </td> 
   <td colname="col3">Adobe Debugger : <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/fr_FR/sc/implement/debugger.html</a> </p> <p>Charles : </p> <p><a href="https://www.charlesproxy.com/" format="http" scope="external"> https://www.charlesproxy.com/</a> </p> </td> 
  </tr> 
 </tbody> 
</table>
