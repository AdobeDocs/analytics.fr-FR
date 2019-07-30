---
title: Termes utilisés dans Adobe Analytics
description: Glossaire d'Adobe Analytics, définissant des termes courants utilisés.
translation-type: tm+mt
source-git-commit: 5ca51ad6b967687004d9447964ed87b29077b330

---


# Termes utilisés dans Adobe Analytics

Utilisez ce glossaire pour comprendre le contexte de nombreux termes utilisés par Adobe Analytics.

* **Console d'administration :** Peut faire référence à :
   * Outils d'administration hérités, où les paramètres d'une suite de rapports dans Adobe Analytics sont gérés. Dans les versions précédentes d'Adobe Analytics, les autorisations utilisateur étaient également gérées ici. See [Admin Tools](../admin/admin/c-admin-tools.md) in the Admin user guide.
   * La console d'administration Adobe, où l'accès aux produits est configuré et les permissions utilisateur sont gérées. See [Admin Console](../admin/admin-console/home.md) in the Admin user guide.
* **Affectation :** Si une variable de conversion rencontre plusieurs valeurs lors d'une visite, le paramètre d'attribution de la variable détermine quelle valeur est conservée. See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **Anomalie :** Détection à l'aide de la modélisation statistique pour détecter automatiquement les tendances imprévues dans les données. Le modèle analyse les mesures et détermine une limite inférieure, une limite supérieure et une plage de valeurs attendues. See [Anomaly Detection](../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) in the Analyze user guide.
* **Appmeasurement :** Bibliothèque de code utilisée pour collecter des données et les envoyer à Adobe. See the [Homepage](../implement/home.md) of the Implement user guide.
* **Emplacement ASI :** Il n'existe plus. Dans les versions précédentes d'Adobe Analytics, les emplacements ASI fournissaient un conteneur de suites de rapports temporaire pour afficher les données segmentées. Dans la version actuelle d'Adobe Analytics, les segments peuvent être appliqués instantanément à n'importe quel rapport.
* **Ventilation :** Vous permet d'afficher une dimension dans le contexte d'une autre dimension. See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Rebond :** Visite comprenant un accès unique. See [Bounces](../components/c-variables/c-metrics/metrics-bounces.md) in the Components user guide. Voir aussi Accès unique.
* **Mesure calculée :** Permet la combinaison de mesures, de fonctions statistiques et de formules existantes pour les rapports. See [Calculated metrics](../components/c-calcmetrics/cm-overview.md) in the Components user guide.
* **Campagne :** Peut faire référence à :
   * Variable Campaign qui remplit la dimension Code de suivi. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
   * Classification par défaut de la dimension Code de suivi ; créées automatiquement pour toutes les suites de rapports.
   * Adobe Campaign, composant d'Adobe Experience Cloud. More information on [Adobe.com](https://www.adobe.com/marketing/campaign.html).
* **Canal :** Peut faire référence à :
   * Variable de canal qui renseigne la dimension Sections du site. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
   * Canaux marketing, composant qui aide à comprendre comment les utilisateurs arrivent sur votre site. See [Marketing Channels](../components/c-marketing-channels/c-overview.md) in the Components user guide.
* **Classification :** Fonctionnalité d'Adobe Analytics qui permet le regroupement des valeurs de dimension. See [Classifications](../components/c-classifications2/c-classifications.md) in the Components user guide.
* **Flux de données Parcours de navigation :** Voir Flux de données.
* **Variable de conversion :** Evars connues sous le nom d'evars. Stocke une valeur personnalisée et conserve la valeur de la variable jusqu'à son expiration. See [Conversion variables](../components/c-variables/dimensionslist/reports-conversion.md) in the Components user guide.
* **Corrélation :** Plus utilisé comme terme ; remplacé par des ventilations de dimension. Dans les versions précédentes d'Adobe Analytics, les corrélations permettaient de ventiler les variables de trafic. See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Données actives :** Option de certains rapports qui permet l'inclusion de données récemment collectées qui n'ont pas encore été entièrement traitées. See [Current data](../analyze/reports-analytics/current-data.md) in the Analyze user guide.
* **Lien personnalisé :** Type d'accès contenant des données non vues. See the [s.tl() function](../implement/js-implementation/function-tl.md) in the Implement user guide. Voir aussi Accès.
* **Attributs du client :** Fonctionnalité Experience Cloud qui permet le transfert de données d'attributs. See [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the Core Services user guide.
* **Délégué du service clientèle :** Un utilisateur désigné autorisé à interagir directement avec le service à la clientèle Adobe. See [Customer support delegates](https://helpx.adobe.com/experience-cloud/supported-users.html) in the Experience Cloud Knowledgebase.
* **Connecteurs de données :** Solution de développement complète qui permet à un tiers d'automatiser le transfert des données dans Adobe Analytics. Les clients de ce tiers peuvent utiliser un connecteur de données pour enrichir leurs données dans Adobe Analytics. La plupart des connecteurs de données utilisent un processus similaire utilisé dans les sources de données. Reportez-vous à la section Connecteurs de données dans le guide de l'utilisateur Importer.
* **Flux de données :** Exportation de données brutes qui répertorie chaque accès comme une ligne et des variables comme des colonnes distinctes. Le plus souvent utilisé pour exporter des données Adobe Analytics vers une base de données tierce. See [Data feeds](../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.
* **Sources de données :** Permet à un utilisateur de télécharger des données à partir d'un fichier dans Adobe Analytics. Le fichier est généralement extrait d'un site FTP. See [Data Sources](../import/c-data-sources/datasrc-home.md) in the Import user guide.
* **Entrepôt de données :** Fonctionnalité d'Adobe Analytics qui vous permet de demander des rapports plus volumineux. See [Data Warehouse](../export/data-warehouse/data-warehouse.md) in the Export user guide.
* **Dimension :** Type de composant contenant des valeurs de variable, comme le texte. notamment le Nom de page, le Code de suivi ou le Domaine référent. Une mesure est généralement son équivalent.
* **Gestion dynamique des balises :** Ancienne solution de gestion des balises d'Adobe. See [DTM implementation overview](../implement/c-implement-with-dtm/dtm-implementation-overview.md) in the Implement user guide. Adobe recommande d'utiliser plutôt Adobe Experience Platform Launch.
* **Sérialisation d'événements :** Processus consistant à implémenter des mesures pour empêcher la collecte d'événements en double. See [Event serialization](../implement/js-implementation/event-serialization.md) in the Implement user guide.
* **Evar :** Voir Variable de conversion.
* **Événement :** Voir Evénement de réussite.
* **Excelclient :** Plus utilisé comme terme. Nom du prédécesseur du créateur de rapports.
* **Expiration :** Dans le contexte d'une variable de conversion, durée pendant laquelle la valeur persiste sur le serveur principal. Cette persistance permet d'associer les événements aux valeurs de variable avant l'accès de l'événement. See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **Flux :** Type de visualisation dans Analysis Workspace qui montre les chemins empruntés par les utilisateurs sur votre site. See [Flow visualization](../analyze/analysis-workspace/visualizations/c-flow/flow.md) in the Analyze user guide.
* **Genesis :** Plus utilisé comme terme. Ancien nom des connecteurs de données.
* **Suite de rapports globale :** Terme informel désigné pour une suite de rapports qui collecte les accès à partir de plusieurs sites.
* **Code H :** Prédécesseur d'appmeasurement. Dans les versions précédentes d'Adobe Analytics, les versions de code étaient mesurées par « version H », comme H 24, H 23.1, etc.
* **Accès :** Une demande d'image unique envoyée aux serveurs de collecte de données Adobe. Les pages vues et les liens personnalisés peuvent être appelés accès.
* **Demande d'image :** Image transparente de 1 x 1 pixel utilisée pour communiquer avec les serveurs de collecte de données Adobe. Un site Web demande cette image invisible avec une longue chaîne de requête contenant des données ; Adobe renvoie l'image invisible et analyse la chaîne de requête reçue.
* **Insight :** Peut faire référence à :
   * Ancien nom de Data Workbench.
   * Custom Insight, un nom historique pour la variable de trafic personnalisée.
* **IPC :** Abréviation pour l'indicateur de performance clé. Mesures qui aident une entreprise à comprendre les performances de son site. Chaque organisation possède des indicateurs clés de performance différents qui mesurent différents aspects de son activité. See [Create a solution design document](../implement/prepare/solution-design.md) in the Implement user guide.
* **Latence :** délai entre la collecte des données et le moment où elles sont disponibles dans les rapports. La latence type d'une suite de rapports est de 30-90 minutes. See [Latency](../technotes/latency.md) in the Technotes user guide.
* **Lancement :** Short for Adobe Experience Platform Launch, Adobe's Current Implementation Solution. See [Overview](https://docs.adobe.com/content/help/en/launch/using/overview.html) in the Adobe Experience Platform Launch user guide.
* **Prop de liste :** Paramètre qui convertit une variable de trafic type en prise en charge de plusieurs valeurs dans le même accès. Toute variable de trafic personnalisée peut devenir une propriété de liste si le paramètre est activé. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
* **List var :** Variable distincte distincte des variables de conversion. Les variables de liste prennent en charge plusieurs valeurs dans le même accès et les valeurs de variable sont conservées lors d'une visite, comme dans le cas des variables de conversion. Seuls trois variables de liste sont disponibles pour une organisation. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
* **Connexion à la société :** Collection de suites de rapports utilisées par votre organisation. Certaines organisations sont dotées de plusieurs sociétés de connexion qui s'appliquent à différentes parties de leur organisation.
* **Mesure :** Type de composant contenant des données quantitatives. Les valeurs de mesure contiennent généralement des nombres, tels que Pages vues, Visites et Recettes. Une dimension est généralement son équivalent.
* **Balisage multi-suite :** Pratique d'envoi du même accès à plusieurs suites de rapports. Avec l'introduction aux suites de rapports virtuelles, cette pratique n'est plus nécessaire. La plupart des actions de balisage multi-suite permettent d'intégrer une suite de rapports globale.
* **Normalisation :** Moyen d'organiser une visualisation qui prend toutes les mesures et les force à des proportions égales, ce qui permet une comparaison plus facile des tendances.
* **Omniture :** Plus utilisé comme terme. organisation détentrice d'Adobe Analytics avant d'être acquise par Adobe en 2009.
* **Cheminement :** Voir Flux.
* **Rapport classé :** Format de rapport qui suit généralement une dimension avec une mesure. Ce type de rapport vous permet de voir les principaux éléments, tels que les pages les plus vues de votre site. Voir aussi Rapport de tendance.
* **Temps réel :** Affiche les variables configurées dès qu'elles sont collectées avec peu de latence. See [Real-time reports](../admin/admin/realtime/realtime.md) in the Admin user guide.
* **Suite de rapports :** Conteneur principal auquel vous envoyez des données. Tous les rapports d'Adobe Analytics référencent une suite de rapports.
* **RSID :** Abréviation de l'identifiant de suite de rapports. Une suite de rapports présente un nom convivial et un identifiant de suite de rapports.
* **Page vue :** Type d'accès qui incrémente les pages vues. See [Page views](../components/c-variables/c-metrics/metrics-page-view.md) in the Components user guide. Voir aussi Accès.
* **Règles de traitement :** Peut faire référence à :
   * Règles de traitement, moyen de modifier la collecte de données à l'aide de certaines règles dans la Console d'administration. See [Processing rules](../admin/admin/c-processing-rules/processing-rules.md) in the Admin user guide.
   * Règles de traitement des canaux marketing, ensemble de règles qui déterminent le canal marketing auquel un accès appartient. See [Marketing channel processing rules](../admin/admin/marketing-channels-admin.md) in the Admin user guide.
* **Prop :** Voir Variable de trafic.
* **s. t () :** Nom de la fonction dans une bibliothèque appmeasurement qui envoie une demande d'image de page vue. Some AppMeasurement libraries use `s.track()` instead. See [s.t()](../implement/js-implementation/function-t.md) in the Implement user guide.
* **s<span>.</span>tl () :** Nom de la fonction dans une bibliothèque appmeasurement qui envoie une demande d'image de suivi de lien. Some AppMeasurement libraries use `s.trackLink()` instead. See [s.tl()](../implement/js-implementation/function-tl.md) in the Implement user guide.
* **Satellite :** Plus utilisé comme terme. Ancien nom du produit pour la gestion dynamique des balises.
* **Segment :** Vous permet de vous concentrer sur un sous-ensemble spécifique de données. See [Segmentation](../components/c-segmentation/seg-overview.md) in the Components user guide.
* **Conteneur de segments :** Partie d'un segment qui détermine le volume de données à placer. Les conteneurs peuvent être basés sur la page vue, la visite ou le visiteur. See [Segmentation](../components/c-segmentation/seg-overview.md) in the Components user guide.
* **Sérialisation :** Voir Sérialisation d'événements.
* **Appel serveur :** Nom alternatif d'une demande d'image ou d'un accès, utilisé principalement dans le contexte de facturation.
* **Accès unique :** Visite où une dimension n'avait qu'une valeur unique. La visite peut avoir plusieurs accès, à condition qu'il n'y ait pas plusieurs valeurs uniques. See [Single access](../components/c-variables/c-metrics/metrics-single-access.md) in the Components user guide. Voir aussi Rebond.
* **Sitecatalyst :** Plus utilisé comme terme. Ancien nom du produit pour Adobe Analytics.
* **Sous-relation :** Plus utilisé comme terme ; remplacé par des ventilations de dimension. Dans les versions précédentes d'Adobe Analytics, les sous-subrelations permettaient de ventiler les variables de conversion. See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Evénement de réussite :** Action suivie par un utilisateur. Votre organisation détermine les événements à suivre et les variables d'événement de réussite que vous utilisez pour le suivre. See [Custom events](../components/c-variables/c-metrics/metrics-custom.md) in the Components user guide.
* **Utilisateur pris en charge :** Voir Délégation du service clientèle.
* **Variable de trafic :** Connu sous le nom de props. Stocke une valeur personnalisée pour un accès unique. Les versions précédentes d'Adobe Analytics attribuaient une valeur unique aux props, mais les améliorations apportées à la plate-forme rendaient largement inutile les variables de trafic personnalisées. Adobe recommande généralement d'utiliser des variables de conversion (evars) dans la plupart des cas. See [Custom traffic variables](../components/c-variables/dimensionslist/reports-custom-traffic.md) in the Components user guide.
* **Rapport de tendance :** Format de rapport qui montre généralement plusieurs plages de dates avec une mesure. Ce type de rapport vous permet de voir comment une mesure fonctionne au fil du temps. Voir aussi Rapport Classement.
* **Visiteur unique**: Représente le nombre de personnes uniques qui ont visité votre site. Un visiteur unique unique peut avoir plusieurs visites. See [Unique visitor](../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide.
* **Suite de rapports virtuelle :** Conteneur virtuel de données qui référence une suite de rapports normale et permet d'affiner les données. Les données n'ont pas été envoyées à une suite de rapports virtuelle ; à la place, les données sont envoyées à une suite de rapports normale et une suite de rapports virtuelle est générée en dehors de ces données collectées. See [Virtual report suites](../components/vrs/vrs-about.md) in the Components user guide.
* **Visite :** Représente le nombre de sessions uniques qui ont eu lieu sur votre site. See [Visits](../components/c-variables/c-metrics/metrics-visit.md) in the Components user guide.
* **Règle VISTA :** Logique personnalisée créée par Adobe à la demande d'un client pour copier, analyser ou filtrer les données côté serveur. Les règles VISTA envoient généralement des coûts supplémentaires. Voir aussi Règles de traitement.
* **Balise Web :** Voir Demande d'image.
