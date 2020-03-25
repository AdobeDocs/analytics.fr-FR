---
description: Cette page d’aide contient les cas d’utilisation recommandés pour chaque outil Adobe Analytics. Les outils doivent être considérés dans l’ordre dans lequel ils sont répertoriés. Si un certain outil ne répond pas aux besoins, passez au suivant pour examen.
title: Quel outil Adobe Analytics dois-je utiliser ?
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: f7125e6845a653ca3d4dd3f1313d1b39f564459c

---


# Quel outil Adobe Analytics dois-je utiliser ?

Cette page d’aide contient les cas d’utilisation recommandés pour chaque outil Adobe Analytics. Les outils doivent être considérés dans l’ordre dans lequel ils sont répertoriés. Si un certain outil ne répond pas aux besoins, passez au suivant pour examen.

Pour en savoir plus sur la comparaison des produits Adobe Analytics, [ici](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md).

## Interfaces utilisateurs de la création de rapports Adobe Analytics {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)** devrait être l’interface utilisateur de référence pour tous vos besoins en matière de création de rapports et d’analyse. Adobe continue d’investir dans ce produit et publie des mises à jour mensuelles. S’il y a une tâche que vous ne pouvez pas faire dans Analysis Workspace, considérez les autres interfaces ci-dessous.**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**doit être utilisé :

* Pour les utilisateurs débutants qui ont besoin d’accéder à des rapports pré-créés plus faciles à parcourir.
* Pour comprendre l’effet élévateur et la confiance    (Analytics pour l’effet élévateur et le degré de confiance de l’effetA4T).
* Pour accéder aux données en temps réel dans l’interface utilisateur.
* Configuration du de calendrier
* Configuration des  de.
* Pour .
* Pour accéder à des visualisations vidéo uniques de la visionneuse simultanée, de la partie horaire de la vidéo et de la liste déroulante de la visionneuse.
* Pour tirer parti des  de publication dans les  planifiées du.

L’**[interface utilisateur de Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)**doit être utilisée :

* Si un fermé de données d’application mobile est souhaité.
* Pour gérer l’implémentation de votre SDK d’application mobile.
* Pour configurer la publicité mobile, telle que la messagerie in-app, la messagerie push et le ciblage d’emplacement.
* Si des visualisations plus interactives sont souhaitées pour les données d’application (radial).
* Visualiser les points d&#39;intérêt sur une carte.
* Pour les mesures de valeur de durée de vie.

**[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)**doit être utilisé :

* Pour exporter 50 000 lignes de données
* Si vous souhaitez organiser les onglets du travail du projet.
* Pour utiliser le rapport  du site  (rapport de cheminement 3D).

**[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**doit être utilisé :

* En tant qu’option d’outil Analytics la plus souple (jusqu’au  de niveau, au niveau de l’accès ).
* Pour créer un jeu de données  à plusieurs d’interactions en ligne et hors ligne, de la gestion de la relation client à la publication d’informations vers le Web.
* Pour une attribution avancée (modèles algorithmiques et basés sur des règles).
* Pour la modélisation statistique prédictive (score de propension, mise en grappe, corrélations, etc.).
* Pour la latence   (temps avant / depuis un ).
* Pour l’identification et l’exportation de segments complexes dans Adobe Experience Cloud.

## Importation de données dans Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[Les classifications](/help/components/c-classifications2/c-classifications.md)**doivent être utilisées :

* Lorsqu’il existe des métadonnées que vous souhaitez associer à une valeur de collecte (eVar, prop, marketing)
* Options :

   * Créateur de règles : est utilisée lorsque des valeurs formatées prévisibles sont collectées pour une variable, par exemple des valeurs délimitées. Cette approche permet de définir les règles une fois pour toutes et de ne plus y penser.
   * Importateur de navigateur : à utiliser en cas d’absence de valeurs prévisibles ou dans le cas d’une liste de valeurs finie qui requiert une mise à jour unique. Cette approche nécessite une surveillance constante des classifications des nouvelles valeurs.

Les **[sources de données](/help/import/c-data-sources/datasrc-home.md)**doivent être utilisées :

* En présence de données hors ligne que vous souhaitez écrire de manière permanente dans Adobe Analytics
* Options :

   * Résumé : téléchargements de données simples, par jour ou dimensions limitées
   * ID de transaction : téléchargements de données qui connectent un point de terminaison en ligne aux données hors ligne et associent entièrement les données importées à un instantané de capturé en ligne (par exemple, les commandes sont terminées en ligne et sont renvoyées hors ligne)
   * Traitement complet : sources de données horodatées, traitées comme s’il s’agissait d’un accès collecté par les serveurs Adobe. C&#39;est-à-dire que les données sont insérées directement dans le parcours du.

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)(anciennement connus sous le nom de Genesis)**doit être utilisé :

* Lorsque vous collaborez avec un fournisseur tiers qui a établi une connexion prise en charge par Adobe Analytics. En général, Data Connectors intègre périodiquement des données sommaires dans Adobe Analytics de façon permanente et automatique.

L’**[API d’insertion de données](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)**doit être utilisée :

* Lorsque vous devez transférer des données dans Adobe Analytics et que vous ne pouvez pas utiliser le code Adobe AppMeasurement ou SDK mobile.

**[Les attributs du client](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**doivent être utilisés :

* Si vous capturez des données clients d’entreprise dans une base de données de gestion de la relation client (CRM) et souhaitez transférer les données vers Experience Cloud.
* Si vous souhaitez utiliser des données de gestion de la relation client pour des   plus approfondis dans Analytics, ou comme critères de ciblage dans Adobe .

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**doit être utilisé :

* Si vous souhaitez incorporer des données de Adobe   Manager (AAM), telles que des informations démographiques (sexe ou niveau de revenu, par exemple), des informations psychographiques (intérêts et loisirs, par exemple), des données de gestion de la relation client ou des données d’impression publicitaire dans n’importe quel flux de travail Analytics.
* Si vous souhaitez que les données de gestion de la relation client téléchargées soient temporelles, car cette intégration envoie de nouvelles informations à l’accès Analytics par accès.

## Exportation de données depuis Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)**doit être utilisé :

* Si les options de mise en page personnalisée de Workspace sont limitées (tout est possible dans le créateur de rapports, dans les limites d’Excel).
* Lier de manière souple les entrées utilisateur ou les sources de données hors ligne (impressions, coût) aux données Adobe. La solution plus permanente pour lier des données est la fonctionnalité Sources de données (voir Importation de données dans Analytics).
* Pour fusionner les données à partir de différents rapports dimensionnels (rapport d’impressions de promo joint au rapport de clics publicitaires vers conversions, par exemple).
* Pour les  de suite de rapports croisés.
* Si l’automatisation par le biais de la planification est souhaitée (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)**doit être utilisé :

* Pour accéder à des variables qui autrement seraient masquées dans l’interface utilisateur (adresse IP, Experience Cloud ID, identifiant visiteur Analytics, URL de page)
* Pour accéder à des données plus granulaires que l’interface utilisateur (de tableau dénormalisé)
* Pour télécharger des données dans un format adapté à une entrée de tableau croisé dynamique
* Si le client souhaite saisir des données Adobe dans un outil tiers de visualisation des données (légèrement résumé et pas au niveau de l’accès)
* Pour accéder à toutes les valeurs de dimension uniques si vous rencontrez un « faible trafic » dans Adobe Analytics

**[Le flux de données Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**doit être utilisé :

* Pour utiliser le flux de données le plus granulaire possible (ID de, accès).
* Si le client souhaite que les données Adobe soient stockées dans une base de données côté client, au niveau le plus granulaire que nous puissions envoyer.
* Si le client souhaite développer un outil Business Intelligence (BI) ou saisir des données Adobe au niveau de l’accès dans un outil tiers.

Les **[API de création de rapports](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)**doivent être utilisées lorsque les autres options de visualisation ne répondent pas à vos besoins. Les 3 options de l’API sont les suivantes :

* **Traitement complet**: lorsque vous souhaitez des données riches en fonctionnalités (y compris les visites, les et les segments). Il s’agit généralement de données résumées de l’interface utilisateur d’Analytics, disponibles dans les 30 à 90 minutes environ. Peut être utilisé par le biais du créateur de rapports.
* **Temps** réel : lorsque vous souhaitez  quelques mesures et dimensions avec des secondes de latence. Il s’agit de données résumées, partiellement traitées et limitées, disponibles en environ 30 secondes. Inclut des algorithmes uniques des plus populaires, gagnants et perdants. Peut être utilisé par le biais du créateur de rapports.
* **[!UICONTROL Live Stream]**: lorsque vous souhaitez un flux de données Analytics au niveau de l’accès partiellement traitées dans les secondes qui suivent la collecte. Il s’agit de données partiellement traitées, disponibles en environ 30 secondes. Disponible pour Analytics Premium uniquement. Requiert une manière de visualiser les données, généralement par le biais d’un engagement des services d’ingénierie.

## Solutions personnalisées {#section_4A212F26A15947599DFB0399A0440CB6}

Les services d’ingénierie doivent être utilisés lorsque :

* Les autres outils Adobe ne répondent pas à vos besoins.
* Vous souhaitez une expérience personnalisée.
* Vous voulez une solution entièrement automatisée.
* Vous voulez atteindre de nombreux appareils.
* Vous disposez de plusieurs sources de données.
* Vous avez des besoins complexes en ETL de données (Extract-Transform-Load).
* Vous voulez une marque personnalisée.
* Vous voulez visualiser [!UICONTROL Analytics Live Stream].
