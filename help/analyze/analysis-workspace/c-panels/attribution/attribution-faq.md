---
title: FAQ sur l’attribution
seo-title: FAQ sur l’attribution
description: Obtenez des réponses aux questions les plus fréquentes sur l’attribution.
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# FAQ sur l’attribution

**Quel est l’élément de ligne "Aucun" lors de l’utilisation de l’attribution ?**

La ligne "Aucun" est un fourre-tout qui représente toutes les conversions survenues sans points de contact dans la fenêtre de recherche. Essayez d'inclure une période plus longue dans la fenêtre de création de rapports.

**Pourquoi est-ce que je vois parfois des dates en dehors de ma fenêtre de rapport lors de l’utilisation de modèles d’attribution ?**

Ces dates supplémentaires sont dues à la fenêtre de recherche des rapports des visiteurs. Pour plus d’informations, voir [Données apparaissant en dehors de la fenêtre](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) de création de rapports dans le Ko Analytics. Adobe prévoit de filtrer ces lignes supplémentaires dans une prochaine version.

**Puis-je utiliser une fenêtre de recherche personnalisée avec mes modèles d’attribution ?**

Les modèles d’attribution reposent actuellement sur une fenêtre de recherche de visiteurs ou de visites. Ces fenêtres de recherche peuvent être ajustées en modifiant la plage de dates des rapports (pour la recherche de visiteurs) ou en utilisant une définition de visite personnalisée dans les suites de rapports virtuelles. Pour plus d’informations, reportez-vous à la section [Traitement](../../../../components/vrs/vrs-report-time-processing.md) du temps des rapports.

**Quand dois-je utiliser une recherche d’attribution de visite ou de visiteur ?**

Le choix de la recherche d’attribution dépend du cas d’utilisation. Si les conversions prennent généralement plus d’une visite unique, il est recommandé de rechercher un visiteur. La création d’une suite de rapports virtuelle avec une définition de visite plus longue est également une solution potentielle.

**Comment les props et les eVars se comparent-ils lors de l’utilisation de l’attribution ?**

L’attribution est recalculée au moment de l’exécution du rapport. Il n’y a donc aucune différence entre une prop ou une eVar (ou toute autre dimension) pour la modélisation de l’attribution. Les props peuvent persister à l’aide de n’importe quelle fenêtre de recherche ou modèle d’attribution, et les paramètres d’attribution/expiration des eVars sont ignorés.

**Les modèles d’attribution sont-ils disponibles dans d’autres fonctionnalités Analytics, telles que les flux de données ou l’entrepôt de données ?**

Non. Les modèles d’attribution utilisent le traitement de l’heure des rapports, disponible uniquement dans Analysis Workspace. Pour plus d’informations, reportez-vous à la section [Traitement](../../../../components/vrs/vrs-report-time-processing.md) du temps des rapports.

**Les modèles d’attribution sont-ils disponibles uniquement si j’utilise une suite de rapports virtuelle avec le traitement de l’heure des rapports activé ?**

Les modèles d’attribution sont disponibles en dehors des suites de rapports virtuelles. Bien qu’ils utilisent le traitement du temps des rapports sur le serveur principal, les modèles d’attribution sont disponibles pour les suites de rapports standard et les suites de rapports virtuelles.

**Quelles dimensions et mesures ne sont pas prises en charge ?**

Le panneau d’attribution prend en charge toutes les dimensions. Les mesures non prises en charge sont les suivantes :

* Visiteurs uniques
* Visites
* Occurrences
* Pages vues
* Mesures d’A4T
* Mesures de durée de la visite
* Retours
* Taux de rebond
* Entrées
* Sorties
* Pages introuvables
* Recherches
* Visites sur une seule page
* Accès unique

**En quoi l’attribution dans Analysis Workspace diffère-t-elle de l’attribution dans les outils de données ?**

Outils de données propose des offres incrémentielles :

* la possibilité d’attribuer plus de sources de données au niveau des visiteurs, comme les impressions publicitaires et les points de vente ;
* Modélisation algorithmique. L’attribution dans Analysis Workspace inclut uniquement les modèles basés sur des règles. Reportez-vous à la section [Meilleure modélisation](https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html) dans le guide de l’utilisateur des outils de données.
* des visualisations supplémentaires, telles que les tables de latence. Voir Tableaux [de](https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html) latence dans le guide de l’utilisateur des outils de données.

**L’attribution fonctionne-t-elle avec les classifications ?**

Oui, les classifications sont entièrement prises en charge.

**L’attribution fonctionne-t-elle avec les sources de données ?**

Oui, la plupart des sources de données sont prises en charge. L’attribution n’est pas possible avec les sources de données de niveau résumé, car elles ne sont pas liées à un identifiant de visiteur Analytics. Les sources de données d’ID de transaction sont également prises en charge, sauf si elles sont utilisées dans une suite de rapports virtuelle avec le traitement de l’heure des rapports activé.

**L’attribution fonctionne-t-elle avec l’intégration d’Analytics de publicité ?**

Les dimensions des métadonnées, telles que le type de correspondance et le mot-clé, fonctionnent avec l’attribution. Cependant, les mesures (y compris les impressions, le coût, les clics, la position moyenne et le score de qualité moyen) utilisent des sources de données de niveau résumé et sont donc incompatibles.
