---
title: FAQ sur l’Attribution
description: Obtenez des réponses aux questions les plus fréquentes au sujet de l’attribution.
translation-type: tm+mt
source-git-commit: 0dfab8e0b48b6a3be40bd1e2b39636b53b71113f
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 76%

---


# FAQ sur l’Attribution

**Qu’est-ce que l’élément de ligne « Aucun » lors de l’utilisation de l’attribution ?**

L’élément de ligne « Aucun » est un élement fourre-tout qui représente toutes les conversions survenues sans points de contact dans l’intervalle de recherche en amont. Pour réduire le nombre de conversions attribuées à l’élément de ligne &quot;Aucun&quot;, essayez d’utiliser une fenêtre de recherche personnalisée avec une période de recherche plus longue.

**Pourquoi est-ce que je vois parfois des dates hors de mon créneau de rapport lors de l’utilisation de modèles d’attribution ?**

Ces dates supplémentaires sont dues à l’intervalle de recherche en amont de rapport de visiteurs. Pour plus d’informations, voir [Données apparaissant hors du créneau de rapport](https://helpx.adobe.com/fr/analytics/kb/data-appearing-outside-reporting-window.html) dans la base de connaissances d’Analytics.

**Quand dois-je utiliser une recherche d’attribution personnalisée, de visite ou de visiteur ?**

Le choix d’une recherche en amont de l’attribution dépend de votre cas d’utilisation. Si les conversions prennent généralement plus d’une visite unique, il est recommandé d’effectuer une recherche en amont visiteur ou personnalisée. Pour les cycles de conversion plus longs, les fenêtres de recherche en amont personnalisées sont plus efficaces car elles sont le seul type capable d&#39;extraire des données avant la fenêtre de rapports.

**Comment les props et les eVars se comparent-ils lors de l’utilisation de l’attribution ?**

L’attribution est recalculée au moment de l’exécution du rapport. Il n’y a donc aucune différence entre prop et eVar (ou toute autre dimension) pour la modélisation d’attribution. Les props peuvent persister à l’aide de n’importe quel intervalle de recherche en amont ou modèle d’attribution, et les paramètres d’attribution/expiration des eVars sont ignorés.

**Les modèles d’attribution sont-ils disponibles dans d’autres fonctionnalités d’Analytics, telles que les flux de données ou l’Data Warehouse ?**

Non. Les modèles d’attribution utilisent le traitement de la période de rapport, disponible uniquement dans Analysis Workspace. Pour plus d’informations, reportez-vous à la section [Traitement de la période de rapport](/help/components/vrs/vrs-report-time-processing.md).

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

**L’attribution fonctionne-t-elle avec des classifications ?**

Oui, les classifications sont entièrement prises en charge.

**L’attribution fonctionne-t-elle avec des sources de données ?**

Oui, la plupart des sources de données sont prises en charge. L’attribution n’est pas possible avec les sources de données de niveau résumé, car elles ne sont pas liées à un identifiant de visiteur Analytics. Les sources de données ID de transaction sont également prises en charge, sauf si elles sont utilisées dans une suite de rapports virtuelle où le traitement du temps est activé.

**L’attribution fonctionne-t-elle avec l’intégration d’Advertising Analytics ?**

Les dimensions des métadonnées, telles que le type de correspondance et le mot-clé, fonctionnent avec l’attribution. Cependant, les mesures (y compris les impressions, le coût, les clics, la position moyenne et la note de qualité moyenne) utilisent des sources de données de niveau résumé et sont donc incompatibles.

**Comment l’attribution fonctionne-t-elle avec les canaux marketing ?**

Lorsque les canaux marketing ont été introduits pour la première fois, ils ne disposaient que des dimensions Première touche et Dernière touche. Les dimensions Première touche/Dernière touche explicites ne sont plus nécessaires avec la version actuelle de l’attribution. Adobe fournit des dimensions génériques &quot;Canal marketing&quot; et &quot;Détails du Canal marketing&quot; afin que vous puissiez les utiliser avec le modèle d’attribution de votre choix. Ces dimensions génériques se comportent de la même manière que les dimensions du Canal Dernière touche, mais sont étiquetées différemment afin d’éviter toute confusion lors de l’utilisation de canaux marketing avec un modèle d’attribution différent.

Étant donné que les dimensions Canal marketing dépendent d’une définition de visite traditionnelle (définie par leurs règles de traitement), la définition de visite ne peut pas être modifiée à l’aide de suites de rapports virtuelles.

**Comment l’attribution fonctionne-t-elle avec les variables à plusieurs valeurs, telles que les variables de liste ?**

Certaines dimensions d’Analytics peuvent contenir plusieurs valeurs sur un seul accès. Les variables de liste et la variable Products sont des exemples courants.

Lorsque l’attribution est appliquée à des accès à plusieurs valeurs, toutes les valeurs d’un même accès reçoivent le même crédit. Comme plusieurs valeurs peuvent recevoir ce crédit, le total du rapport peut être différent de celui de chaque élément de ligne. Le total du rapport est dédupliqué, tandis que chaque valeur de dimension individuelle reçoit un crédit approprié.

**Comment l’attribution fonctionne-t-elle avec la segmentation ?**

L’attribution s’exécute toujours avant la segmentation et la segmentation s’exécute avant l’application des filtres de rapport. Ce concept s’applique également aux suites de rapports virtuelles utilisant des segments.

Par exemple, si vous créez une suite de rapports virtuelle avec un segment « Accès à l’affichage » appliqué, vous pouvez voir d’autres canaux dans un tableau à l’aide de certains modèles d’attribution.

![Suite de rapports virtuelle, affichage uniquement](assets/vrs-aiq-example.png)

>[!NOTE] Si un segment supprime les accès contenant votre mesure, ces instances de mesure ne sont attribuées à aucune dimension. Cependant, un filtre de rapport similaire masquera simplement certaines valeurs de dimension, sans aucun impact sur les mesures traitées par le modèle d’attribution. Par conséquent, un segment peut renvoyer des valeurs inférieures à un filtre avec une définition comparable.
