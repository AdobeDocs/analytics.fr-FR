---
title: FAQ sur l’Attribution
description: Obtenez des réponses aux questions les plus fréquentes au sujet de l’attribution.
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# FAQ sur l’Attribution

**Qu’est-ce que l’élément de ligne « Aucun » lors de l’utilisation de l’attribution ?**

L’élément de ligne « Aucun » est un fourre-tout qui représente toutes les conversions survenues sans points de contact dans l’intervalle de recherche en amont. Essayez d’inclure une période plus longue dans votre créneau de rapport.

**Pourquoi est-ce que je vois parfois des dates hors de mon créneau de rapport lors de l’utilisation de modèles d’attribution ?**

Ces dates supplémentaires sont dues à l’intervalle de recherche en amont de rapport de visiteurs. Pour plus d’informations, voir [Données apparaissant hors du créneau de rapport](https://helpx.adobe.com/fr/analytics/kb/data-appearing-outside-reporting-window.html) dans la base de connaissances d’Analytics. Adobe prévoit de filtrer ces rangées supplémentaires dans une prochaine version.

**Puis-je utiliser un intervalle de recherche en amont personnalisé avec mes modèles d’attribution ?**

Les modèles d’attribution reposent actuellement sur un intervalle de recherche en amont des visiteurs ou des visites. Ces intervalles de recherche peuvent être ajustés en modifiant la période de rapport (pour la recherche en amont des visiteurs) ou en utilisant une définition de visite personnalisée dans les suites de rapports virtuelles. Pour plus d’informations, reportez-vous à la section [Traitement de la période de rapport](../../../../components/vrs/vrs-report-time-processing.md).

**Quand dois-je utiliser une recherche en amont de l’attribution de visites ou de visiteurs ?**

Le choix d’une recherche en amont de l’attribution dépend de votre cas d’utilisation. Si les conversions prennent généralement plus longtemps qu’une visite unique, une recherche en amont des visiteurs est recommandée. La création d’une suite de rapports virtuelle avec une définition de visite plus longue est également une solution potentielle.

**Comment les props et les eVars se comparent-ils lors de l’utilisation de l’attribution ?**

L’attribution est recalculée au moment de l’exécution du rapport. Il n’y a donc aucune différence entre prop et eVar (ou toute autre dimension) pour la modélisation d’attribution. Les props peuvent persister à l’aide de n’importe quel intervalle de recherche en amont ou modèle d’attribution, et les paramètres d’attribution/expiration des eVars sont ignorés.

**Les modèles d’attribution sont-ils disponibles dans d’autres fonctionnalités d’Analytics, telles que les flux de données ou l’Data Warehouse ?**

Non. Les modèles d’attribution utilisent le traitement de la période de rapport, disponible uniquement dans Analysis Workspace. Pour plus d’informations, reportez-vous à la section [Traitement de la période de rapport](../../../../components/vrs/vrs-report-time-processing.md).

**Les modèles d’attribution ne sont-ils disponibles que si j’utilise une suite de rapports virtuelle avec le traitement de la période de rapport activé ?**

Les modèles d’attribution sont disponibles en dehors des suites de rapports virtuelles. Bien qu’ils utilisent le traitement de la période de rapport sur le serveur principal, les modèles d’attribution sont disponibles pour les suites de rapports standard et les suites de rapports virtuelles.

**Quelles sont les dimensions et les mesures non prises en charge ?**

Le panneau d’attribution prend en charge toutes les dimensions. Voici les mesures non prises en charge :

* Visiteurs uniques
* Visites
* Occurrences
* Pages vues
* Mesures d’A4T
* Mesures de durée de la visite
* Rebonds
* Taux de rebond
* Entrées
* Sorties
* Pages introuvables
* Recherches
* Visites sur une seule page
* Accès unique

**En quoi l’attribution dans Analysis Workspace diffère-t-elle de l’attribution dans Data Workbench ?**

Data Workbench offre progressivement ce qui suit :

* La possibilité d’attribuer plus de sources de données au niveau des visiteurs, comme les impressions publicitaires et les points de vente.
* La modélisation algorithmique. L’attribution dans Analysis Workspace inclut uniquement des modèles basés sur des règles. Reportez-vous à la section [Modélisation la mieux adaptée](https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html) dans le guide de l’utilisateur de Data Workbench.
* Des visualisations supplémentaires, telles que les tables de latence. Voir [Tables de latence](https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html) dans le guide de l’utilisateur de Data Workbench.

**L’attribution fonctionne-t-elle avec des classifications ?**

Oui, les classifications sont entièrement prises en charge.

**L’attribution fonctionne-t-elle avec des sources de données ?**

Oui, la plupart des sources de données sont prises en charge. L’attribution n’est pas possible avec les sources de données de niveau résumé, car elles ne sont pas liées à un identifiant de visiteur Analytics. Les sources de données ID de transaction sont également prises en charge, sauf si elles sont utilisées dans une suite de rapports virtuelle où le traitement du temps est activé.

**L’attribution fonctionne-t-elle avec l’intégration d’Advertising Analytics ?**

Les dimensions des métadonnées, telles que le type de correspondance et le mot-clé, fonctionnent avec l’attribution. Cependant, les mesures (y compris les impressions, le coût, les clics, la position moyenne et la note de qualité moyenne) utilisent des sources de données de niveau résumé et sont donc incompatibles.
