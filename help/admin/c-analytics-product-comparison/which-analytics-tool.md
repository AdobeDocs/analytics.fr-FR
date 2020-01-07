---
description: Cette page d’aide comporte des cas d’utilisation recommandés pour chaque outil Adobe Analytics. Les outils doivent être pris en considération dans l’ordre dans lequel ils sont répertoriés. Si un outil n’est pas adapté, passez au suivant qui doit être pris en compte.
title: Quel outil Adobe Analytics dois-je utiliser ?
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: b4e17f7aad73af250c89cb8117f741f7eed89b7e

---


# Quel outil Adobe Analytics dois-je utiliser ?

Cette page d’aide comporte des cas d’utilisation recommandés pour chaque outil Adobe Analytics. Les outils doivent être pris en considération dans l’ordre dans lequel ils sont répertoriés. Si un outil n’est pas adapté, passez au suivant qui doit être pris en compte.

Pour en savoir plus sur la comparaison des produits Adobe Analytics, [ici](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md).

## Interfaces utilisateurs de la création de rapports Adobe Analytics {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)**devrait être l’interface utilisateur de référence pour tous vos besoins en matière de création de rapports et d’analyse. Adobe continue d’investir dans ce produit et publie des mises à jour mensuelles. S’il y a une tâche que vous ne pouvez pas faire dans Analysis Workspace, considérez les autres interfaces ci-dessous.**

Les **[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**doivent être utilisés :

* Pour les utilisateurs débutants qui ont besoin d’accéder à des rapports pré-créés plus faciles à parcourir.
* Pour comprendre l’effet élévateur et le degré de confiance de l’activité Target (Analytics pour Target/A4T).
* Pour accéder aux données en temps réel dans l’interface utilisateur.
* Pour configurer les événements du calendrier.
* Pour configurer les cibles.
* Pour afficher les rapports des robots.
* Pour visualiser plusieurs suites de rapports dans un seul tableau de bord de l’interface utilisateur.
* Pour accéder à des visualisations vidéo uniques en fonction de la Visionneuse simultanée, de la Tranche horaire de la vidéo et de l’Abandon du visionnage.
* Pour tirer parti des Listes de publication dans les rapports programmés.

L’**[interface utilisateur de Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)**doit être utilisée :

* Si un affichage cloisonné des données des applications mobiles est souhaité.
* Gérer l’implémentation de votre SDK d’applications mobiles.
* Configurer la publicité mobile, comme la messagerie in-app, la messagerie Push et le ciblage géographique.
* Si des visualisations interactives supplémentaires sont souhaitées pour les données des applications (rayons).
* Visualiser des points ciblés sur une carte.
* Pour les mesures de valeur de durée de vie.

Les **[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)**doivent être utilisées :

* Pour exporter 50 000 lignes de données
* Si une organisation des onglets du projet est requise.
* Pour utiliser le rapport Analyse de site (rapport de cheminement 3D).

Les **[outils de données](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**doivent être utilisés :

* En tant qu’option d’outil Analytics la plus souple (jusqu’à l’analyse au niveau des visiteurs et des accès).
* Pour créer un jeu de données multicanal d’interactions en ligne et hors ligne, depuis la gestion de la relation client vers le POS jusqu’au Web.
* Pour une attribution avancée (modèles algorithmiques et basés sur des règles).
* Pour la modélisation statistique de prédiction (score de propension, mise en cluster, corrélations, etc.).
* Pour l’analyse de latence (durée avant/depuis un événement).
* Pour l’identification et l’exportation de segments complexes par l’intermédiaire d’Adobe Experience Cloud.

## Importation de données dans Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[Les classifications](/help/components/c-classifications2/c-classifications.md)**doivent être utilisées :

* En présence de métadonnées que vous souhaitez associer à une valeur de collecte (eVar, prop, canal marketing)
* Options:

   * Créateur de règles : à utiliser en cas de valeurs formatées prévisibles collectées pour une variable ; des valeurs délimitées, par exemple. Cette approche permet de définir les règles une fois pour toutes et de ne plus y penser.
   * Importateur de navigateur : à utiliser en cas d’absence de valeurs prévisibles ou dans le cas d’une liste de valeurs finie qui requiert une mise à jour unique. Cette approche nécessite une surveillance constante des classifications des nouvelles valeurs.

Les **[sources de données](/help/import/c-data-sources/datasrc-home.md)**doivent être utilisées :

* En présence de données hors ligne que vous souhaitez écrire de manière permanente dans Adobe Analytics
* Options:

   * Résumé : simples téléchargements des données, par jour ou dimensions limitées
   * ID de transaction : téléchargements de données qui connectent un point de terminaison en ligne à des données hors ligne et associent complètement des données importées à un instantané de visiteur capturé en ligne (par exemple, des commandes effectuées en ligne et retournées hors ligne)
   * Traitement complet : sources de données horodatées traitées comme s’il s’agissait d’un accès collecté par les serveurs Adobe. En d’autres termes, les données sont insérées directement dans le parcours du visiteur.

**[Les Data Connectors](https://www.adobeexchange.com/experiencecloud.html)(anciennement connus sous le nom de Genesis)** doivent être utilisés :

* Lorsque vous collaborez avec un fournisseur tiers qui a établi une connexion prise en charge par Adobe Analytics. En général, les Data Connectors intègrent périodiquement des données sommaires dans Adobe Analytics de façon permanente et automatique.

L’**[API d’insertion de données](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)**doit être utilisée :

* Lorsque vous devez transférer des données dans Adobe Analytics et que vous ne pouvez pas utiliser le code Adobe AppMeasurement ou SDK mobile.

**[Les attributs du client](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**doivent être utilisés :

* Si vous capturez les données des clients d’une entreprise dans une base de données de gestion de la relation client et que vous souhaitez transférer ces informations dans Experience Cloud.
* Si vous souhaitez utiliser les données de gestion de la relation client pour une analyse plus approfondie dans Analytics ou comme critère de ciblage dans Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**doit être utilisé :

* Si vous souhaitez incorporer des données d’audience Adobe Audience Manager (AAM) telles que des données démographiques (par exemple, le sexe ou le niveau de revenu), des données psychographiques (par exemple, les centres d’intérêt et les loisirs), des données de gestion de la relation client ou des données d’impression publicitaire dans n’importe quel workflow d’Analytics.
* Si vous souhaitez que les données de gestion de la relation client téléchargées soient basées sur le temps, car cette intégration envoie de nouvelles informations à Analytics après chaque accès.

## Exportation de données depuis Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

Le **[Report Builder](/help/analyze/report-builder/home.md)**doit être utilisé :

* Si les options de disposition personnalisées de Workspace sont limitées (tout est possible dans le Report Builder, dans les limites d’Excel).
* Pour lier vaguement des entrées utilisateur ou des sources de données hors ligne (impressions, coût) à des données Adobe. L’option Sources de données constitue une solution plus permanente pour lier les données (voir Importation de données dans Analytics).
* Pour fusionner des données depuis différents rapports dimensionnels (par exemple un rapport d’impressions promo joint à un rapport clic jusqu’à la conversion promo).
* Pour les affichages de suite de rapports croisés.
* Si l’automatisation par l’intermédiaire de la planification est souhaitée (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)**doit être utilisé :

* Pour accéder à des variables qui autrement seraient masquées dans l’interface utilisateur (adresse IP, Experience Cloud ID, identifiant visiteur Analytics, URL de page)
* Pour accéder à des données plus granulaires que l’interface utilisateur (affichage de tableau dénormalisé)
* Pour télécharger des données dans un format approprié à une entrée de tableau croisé dynamique (pivot)
* Si le client souhaite saisir des données Adobe dans un outil de visualisation de données tiers (légèrement résumées et pas au niveau de l’accès)
* Pour accéder à toutes les valeurs de dimension uniques si vous rencontrez un « faible trafic » dans Adobe Analytics

**[Le flux de données Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**doit être utilisé :

* Pour utiliser les flux de données les plus granulaires que nous pouvons fournir (identifiant visiteur, accès).
* Si le client souhaite que les données Adobe soient stockées dans une base de données côté client, au niveau le plus granulaire que nous pouvons envoyer.
* Si le client souhaite développer un outil de veille stratégique ou saisir des données Adobe de niveau accès dans un outil tiers.

Les **[API de création de rapports](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)**doivent être utilisées lorsque les autres options de visualisation ne répondent pas à vos besoins. Les 3 options d’API incluent :

* **Données entièrement traitées** : lorsque vous souhaitez des données riches en fonctionnalités (notamment des visites, des visiteurs et des segments). Il s’agit généralement de données résumées de l’interface utilisateur d’Analytics disponibles sous 30 à 90 minutes. Utilisation possible par l’intermédiaire du Report Builder.
* **Temps réel** : lorsque vous souhaitez voir quelques mesures et dimensions avec des secondes de latence. Il s’agit de données limitées, partiellement traitées et résumées, disponibles sous 30 secondes environ. Inclut des algorithmes uniques, des plus populaires, des gagnants et des perdants. Utilisation possible par l’intermédiaire du Report Builder.
* **[!UICONTROL Livestream]** : lorsque vous souhaitez un flux de données Analytics de niveau accès traitées partiellement, dans les secondes suivant la collecte. Il s’agit de données partiellement traitées, disponibles sous 30 secondes environ. Disponible pour Analytics Premium uniquement. Nécessite une méthode de visualisation des données, généralement par l’intermédiaire de services d’ingénierie.

## Solutions personnalisées {#section_4A212F26A15947599DFB0399A0440CB6}

Les services d’ingénierie doivent être utilisés lorsque :

* Les autres outils Adobe ne répondent pas à vos besoins.
* Vous voulez une expérience personnalisée.
* Vous voulez une solution entièrement automatisée.
* Vous voulez atteindre plusieurs dispositifs.
* Vous disposez de plusieurs sources de données.
* Vous êtes contraint par des exigences ETL (Extract-Transform-Load) de données complexes.
* Vous voulez une valorisation de marque personnalisée.
* Vous voulez visualiser [!UICONTROL Analytics Live Stream].
