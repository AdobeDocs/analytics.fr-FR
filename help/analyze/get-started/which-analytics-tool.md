---
description: Cette page d’aide comporte des cas d’utilisation recommandés pour chaque outil Adobe Analytics. Les outils doivent être pris en considération dans l’ordre dans lequel ils sont répertoriés. Si un outil n’est pas adapté, passez au suivant qui doit être pris en compte.
title: Quel outil Adobe Analytics dois-je utiliser ?
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
TQID: https://experienceleague.adobe.com/xk485fKU7Q2DeZIYaTtN-a4JKnyVamAygW03z7ffAOk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: a421fb65-2c82-457a-921c-28c46b697a39id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 1175
ht-degree: 98%

---

# Quel outil Adobe Analytics dois-je utiliser ?

Cette page d’aide comporte des cas d’utilisation recommandés pour chaque outil Adobe Analytics. Les outils doivent être pris en considération dans l’ordre dans lequel ils sont répertoriés. Si un outil n’est pas adapté, passez au suivant qui doit être pris en compte.

Pour plus de comparaisons de produits Adobe Analytics, voir [Comparaison des produits Analytics](/help/analyze/get-started/analytics-product-comparison.md).


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Comparaison d’outils](https://video.tv.adobe.com/v/27220?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Interfaces d’utilisation de la création de rapports Adobe Analytics {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** devrait être l’interface utilisateur de référence pour tous vos besoins en matière de création de rapports et d’analyse. Adobe continue d’investir dans ce produit et publie des mises à jour mensuelles. S’il y a une tâche que vous ne pouvez pas faire dans Analysis Workspace, considérez les autres interfaces ci-dessous.**

Les **[tableaux de bord Adobe Analytics](/help/analyze/mobile-app/home.md)** permettent aux utilisateurs et utilisatrices mobiles d’accéder à des fiches d’évaluation intuitives. Les Fiches d’évaluation sont un ensemble de mesures clés et d’autres composants présentés sous la forme d’une mise en page de type mosaïque sur laquelle vous pouvez appuyer pour obtenir des répartitions plus détaillées ainsi que des rapports de tendances. L’application mobile est prise en charge aussi bien sur les systèmes d’exploitation iOS qu’Android.

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** est un module complémentaire de Microsoft Excel qui s’exécute sur Mac, Windows et sur les navigateurs web. Il vous permet de créer des requêtes personnalisées à partir de données Adobe Analytics que vous pouvez ensuite insérer dans des feuilles de calcul Excel. Ces demandes peuvent référencer des cellules de manière dynamique dans votre feuille de calcul. Vous pouvez, en outre, mettre à jour et personnaliser la manière dont le Report Builder présente les données.

Le **[Report Builder hérité](/help/analyze/legacy-report-builder/home.md)** est un module complémentaire de Microsoft Excel qui s’exécute uniquement sous Windows. Il vous permet de créer des requêtes personnalisées à partir de données Adobe Analytics que vous pouvez ensuite insérer dans des feuilles de calcul Excel. Ces demandes peuvent référencer des cellules de manière dynamique dans votre feuille de calcul. Vous pouvez, en outre, mettre à jour et personnaliser la manière dont le Report Builder présente les données.

**[Activity Map](/help/analyze/activity-map/overview.md)** est une fonctionnalité d’Adobe Analytics qui fournit une représentation visuelle de l’engagement des utilisateurs et utilisatrices sur les pages web et les applications mobiles. Il permet aux personnes spécialisées dans le marketing et dans l’analyse de suivre et d’analyser les interactions utilisateur, telles que les clics, les survols et le comportement de défilement.

## Import de données dans Adobe Analytics {#import}

**[Les classifications](/help/components/classifications/classifications-overview.md)** doivent être utilisées :

* En présence de métadonnées que vous souhaitez associer à une valeur de collecte (eVar, prop, canal marketing). Adobe recommande d’utiliser les [jeux de classifications](/help/components/classifications/sets/overview.md). Le créateur de règles de classification et l’importateur de classifications sont des méthodes héritées permettant d’importer des données de classification dans Adobe Analytics.

Les **[sources de données](/help/import/data-sources/overview.md)** doivent être utilisées :

* En présence de données hors ligne que vous souhaitez écrire de manière permanente dans Adobe Analytics.
* Options :
   * Résumé : simples téléchargements des données, par jour ou dimensions limitées.
   * ID de transaction : téléchargements de données qui connectent un point d’entrée en ligne à des données hors ligne et associent complètement des données importées à un instantané de visiteur capturé en ligne (par exemple, des commandes effectuées en ligne et retournées hors ligne).

Les **[intégrations Adobe Exchange](https://www.adobeexchange.com/experiencecloud.html)** doivent être utilisées :

* Lorsque vous collaborez avec un fournisseur tiers qui a établi une connexion prise en charge par Adobe Analytics. En général, les applications dʼintégration intègrent périodiquement des données récapitulatives dans Adobe Analytics, de façon permanente et automatique.

**[API Bulk Data Insertion](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* L’API Bulk Data Insertion accepte les fichiers au format CSV contenant des données d’événement, un événement par ligne. Adobe recommande d’utiliser l’API Bulk Insertion pour toute implémentation nécessitant du code côté serveur ou ne pouvant pas utiliser AppMeasurement ou le SDK Web pour la collecte de données.

L’**[API Data Insertion (héritée)](/help/import/c-data-insertion-api/c-data-insertion-api.md)** doit être utilisée :

* Lorsque vous devez importer des données dans Adobe Analytics et que vous ne pouvez pas utiliser AppMeasurement, le SDK Web ou l’API Bulk Data Insertion.

**[Les attributs client](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=fr)** doivent être utilisés :

* Si vous capturez des données client d’entreprise dans une base de données de gestion de la relation client (GRC) et que vous souhaitez charger les données vers l’expérience client Entreprise.
* Si vous souhaitez utiliser les données de gestion de la relation client pour une analyse plus approfondie dans Analytics ou comme critère de ciblage dans Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** doit être utilisé :

* Si vous souhaitez incorporer des données d’audience Adobe Audience Manager telles que des données démographiques (par exemple, le genre ou le niveau de revenu), des données psychographiques (par exemple, les centres d’intérêt et les loisirs), des données de gestion de la relation client ou des données d’impression publicitaire dans n’importe quel workflow Analytics.
* Si vous souhaitez que les données de gestion de la relation client téléchargées soient basées sur le temps, car cette intégration envoie de nouvelles informations à Analytics après chaque accès.

## Exportation de données depuis Adobe Analytics {#export}

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** doit être utilisé :

* Si les options de disposition personnalisées de Workspace sont limitées (tout est possible dans le Report Builder, dans les limites d’Excel).
* Pour lier vaguement des entrées utilisateur ou des sources de données hors ligne (impressions, coût) à des données Adobe. L’option Sources de données constitue une solution plus permanente pour lier les données (voir Import de données dans Analytics).
* Pour fusionner des données depuis différents rapports dimensionnels (par exemple, un rapport d’impressions promo joint à un rapport clic jusqu’à la conversion promo).
* Pour fusionner les données provenant de différentes suites de rapports, soit en les additionnant, soit en les affichant côte à côte dans le même tableau.
* Si l’automatisation par l’intermédiaire de la planification est souhaitée (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** doit être utilisé :

* Pour accéder à des variables qui autrement seraient masquées dans l’interface utilisateur (adresse IP, Experience Cloud ID, identifiant visiteur Analytics, URL de page)
* Pour accéder à des données plus granulaires que l’interface utilisateur (affichage de tableau dénormalisé)
* Pour télécharger des données dans un format approprié à une entrée de tableau croisé dynamique (pivot)
* Si le client souhaite saisir des données Adobe dans un outil de visualisation de données tiers (légèrement résumées et pas au niveau de l’accès)
* Pour accéder à tous les éléments de dimension uniques si vous rencontrez un « faible trafic » dans Adobe Analytics

**[Le flux de données Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** doit être utilisé :

* Pour utiliser les flux de données les plus granulaires que nous pouvons fournir (identifiant visiteur, accès).
* Si le client souhaite que les données Adobe soient stockées dans une base de données côté client, au niveau le plus granulaire que nous pouvons envoyer.
* Si le client souhaite développer un outil de veille stratégique ou saisir des données Adobe de niveau accès dans un outil tiers.

Les **[API de création de rapports](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** doivent être utilisées lorsque les autres options de visualisation ne répondent pas à vos besoins. Les 3 options d’API incluent :

* **Données entièrement traitées** : lorsque vous souhaitez des données riches en fonctionnalités (notamment des visites, des visiteurs et des segments). Il s’agit généralement de données résumées de l’interface utilisateur d’Analytics disponibles sous 30 à 90 minutes. Utilisation possible par l’intermédiaire du Report Builder.
* **Temps réel** : lorsque vous souhaitez voir quelques mesures et dimensions avec des secondes de latence. Il s’agit de données limitées, partiellement traitées et résumées, disponibles sous 30 secondes environ. Inclut des algorithmes uniques, des plus populaires, des gagnants et des perdants. Utilisation possible par l’intermédiaire du Report Builder.
* **[!UICONTROL Livestream]** : lorsque vous souhaitez un flux de données Analytics de niveau accès traitées partiellement, dans les secondes suivant la collecte. Il s’agit de données partiellement traitées, disponibles sous 30 secondes environ. Disponible pour Analytics Premium uniquement. Nécessite une méthode de visualisation des données, généralement par l’intermédiaire d’un engagement des services d’ingénierie.

## Solutions personnalisées {#custom-solutions}

Les services d’ingénierie doivent être utilisés lorsque :

* Les autres outils Adobe ne répondent pas à vos besoins.
* Vous voulez une expérience personnalisée.
* Vous voulez une solution entièrement automatisée.
* Vous voulez atteindre plusieurs appareils.
* Vous disposez de plusieurs sources de données.
* Vous êtes contraint par des exigences ETL (Extract-Transform-Load) de données complexes.
* Vous voulez une valorisation de marque personnalisée.
* Vous voulez visualiser [!UICONTROL Analytics Live Stream].
