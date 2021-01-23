---
title: FAQ sur l’Attribution
description: Obtenez des réponses aux questions les plus fréquentes au sujet de l’attribution.
translation-type: tm+mt
source-git-commit: 14ec79335ff0b37e3072a0a1b04b0727100cad76
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 71%

---


# FAQ sur l’Attribution

## Qu’est-ce que l’élément de ligne « Aucun » lors de l’utilisation de l’attribution ?

L’élément de ligne « Aucun » est un élement fourre-tout qui représente toutes les conversions survenues sans points de contact dans l’intervalle de recherche en amont. Pour réduire le nombre de conversions attribuées à l’élément de ligne « Aucun », essayez d’utiliser un intervalle de recherche en amont personnalisé avec une période de recherche en amont plus longue.

## Pourquoi est-ce que je vois parfois des dates hors de mon créneau de rapport lors de l’utilisation de modèles d’attribution ?

Certaines mesures basées sur les visites, telles que [Entrées](/help/components/metrics/entries.md) ou [Taux de rebonds](/help/components/metrics/bounce-rate.md), peuvent attribuer des données à une période antérieure à la plage de débuts de la fenêtre de rapports. Cette situation est due aux modèles d’attribution qui utilisent une fenêtre de recherche en amont, ce qui détermine à quel point l’attribution en aval doit être créditée pour les mesures. Le scénario le plus courant est lorsque les visites s’étendent sur minuit. Par exemple :

1. Un utilisateur visite votre page d&#39;accueil à 23h55 le 7 septembre.
1. Ils visitent plusieurs pages, dont la dernière s&#39;est produite à 12h05 le 8 septembre.
1. Une semaine plus tard, vous lancez un rapport de tendance quotidien avec une plage de dates comprise entre le 8 et le 14 septembre.

Les mesures basées sur les accès, telles que [vues de page](/help/components/metrics/page-views.md), produiraient la sortie attendue ; données de tendances chaque jour, du 8 septembre au 14 septembre. Cependant, les mesures basées sur les visites présenteraient également la visite ci-dessus le 7 septembre. L’entrée attribuée à la visite s’est produite le 7 septembre et la fenêtre de recherche en amont est, par défaut, comprise entre le 1er et le 31 septembre.

Dans cet exemple, le taux de rebonds affiche toujours 0 % le 7 septembre. Cette mesure est définie sous la forme `Bounces divided by Entries`, une mesure basée sur les accès divisée par une mesure basée sur les visites. Les rebonds se composent d’une seule demande d’image, de sorte qu’ils ne peuvent pas s’étendre sur plusieurs jours. Les rebonds du 7 septembre se sont produits en dehors de la fenêtre du rapports, provoquant ainsi le taux de rebonds garanti de 0 % pour cette journée. D’autres mesures basées sur les accès présenteraient également 0 pour le 7 septembre dans ce rapport, puisque ces accès ne se trouvent pas non plus dans la fenêtre de rapports.

Prenons un autre exemple similaire. La seule différence entre l’exemple suivant et l’exemple ci-dessus est les dates :

1. Un utilisateur visite votre page d&#39;accueil à 23h55 le 31 août.
1. Ils visitent plusieurs pages, dont la dernière s&#39;est produite à 12h05 le 1er septembre.
1. Une semaine plus tard, vous lancez un rapport de tendance quotidien avec une plage de dates comprise entre le 1er septembre et le 7 septembre.

Dans cet exemple, les entrées et le taux de rebonds n’affichaient pas les données du 31 août. La fenêtre de recherche et la fenêtre de rapports sont toutes les deux débuts le 1er septembre, de sorte que les données ne peuvent pas être attribuées à partir du 31 août.

## Quand dois-je utiliser une recherche en amont de l’attribution de visites, de visiteurs ou personnalisée ?

Le choix d’une recherche en amont de l’attribution dépend de votre cas d’utilisation. Si les conversions prennent généralement plus longtemps qu’une visite unique, une recherche en amont des visiteurs ou personnalisée est recommandée. Pour les cycles de conversion plus longs, il est préférable d’utiliser des intervalles de recherche en amont personnalisés, car ce sont les seuls types qui permettent d’extraire des données avant le créneau de rapport.

## Comment les props et les eVars se comparent-ils lors de l’utilisation de l’attribution ?

L’attribution est recalculée au moment de l’exécution du rapport. Il n’y a donc aucune différence entre prop et eVar (ou toute autre dimension) pour la modélisation d’attribution. Les props peuvent persister à l’aide de n’importe quel intervalle de recherche en amont ou modèle d’attribution, et les paramètres d’attribution/expiration des eVars sont ignorés.

## Les modèles d’attribution sont-ils disponibles dans d’autres fonctionnalités d’Analytics, telles que les flux de données ou l’Data Warehouse ?

Non. Les modèles d’attribution utilisent le traitement de la période de rapport, disponible uniquement dans Analysis Workspace. Pour plus d’informations, reportez-vous à la section [Traitement de la période de rapport](/help/components/vrs/vrs-report-time-processing.md).

## Les modèles d’attribution ne sont-ils disponibles que si j’utilise une suite de rapports virtuelle avec le traitement de la période de rapport activé ?

Les modèles d’attribution sont disponibles en dehors des suites de rapports virtuelles. Bien qu’ils utilisent le traitement de la période de rapport sur le serveur principal, les modèles d’attribution sont disponibles pour les suites de rapports standard et les suites de rapports virtuelles.

## Quelles sont les dimensions et les mesures non prises en charge ?

Le panneau d’attribution prend en charge toutes les dimensions. Voici les mesures non prises en charge :

* Toutes les mesures calculées
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

## L’attribution fonctionne-t-elle avec des classifications ?

Oui, les classifications sont entièrement prises en charge.

## L’attribution fonctionne-t-elle avec des sources de données ?

Oui, la plupart des sources de données sont prises en charge. L’attribution n’est pas possible avec les sources de données de niveau résumé, car elles ne sont pas liées à un identifiant de visiteur Analytics. Les sources de données ID de transaction sont également prises en charge, sauf si elles sont utilisées dans une suite de rapports virtuelle où le traitement du temps est activé.

## L’attribution fonctionne-t-elle avec l’intégration d’Advertising Analytics ?

Les dimensions des métadonnées, telles que le type de correspondance et le mot-clé, fonctionnent avec l’attribution. Cependant, les mesures (y compris les impressions, le coût, les clics, la position moyenne et la note de qualité moyenne) utilisent des sources de données de niveau résumé et sont donc incompatibles.

## Comment l’attribution fonctionne-t-elle avec les canaux marketing ?

Lorsque les canaux marketing ont été introduits pour la première fois, ils ne disposaient que des dimensions Première touche et Dernière touche. Les dimensions Première touche/Dernière touche explicites ne sont plus nécessaires avec la version actuelle de l’attribution. Adobe fournit des dimensions « Canal marketing » et « Détails sur les canaux marketing » génériques afin que vous puissiez les utiliser avec le modèle d’attribution de votre choix. Ces dimensions génériques se comportent de la même manière que les dimensions Canal Dernière touche, mais sont étiquetées différemment pour éviter toute confusion lors de l’utilisation de canaux marketing avec un modèle d’attribution différent.

Étant donné que les dimensions Canal marketing dépendent d’une définition de visite traditionnelle (définie par leurs règles de traitement), la définition de visite ne peut pas être modifiée à l’aide de suites de rapports virtuelles.

## Comment l’attribution fonctionne-t-elle avec les variables à plusieurs valeurs, telles que les variables de liste ?

Certaines dimensions d’Analytics peuvent contenir plusieurs valeurs sur un seul accès. Les variables de liste et la variable Products sont des exemples courants.

Lorsque l’attribution est appliquée à des accès à plusieurs valeurs, toutes les valeurs d’un même accès reçoivent le même crédit. Comme plusieurs valeurs peuvent recevoir ce crédit, le total du rapport peut être différent de celui de chaque élément de ligne. Le total du rapport est dédupliqué, tandis que chaque élément de dimension individuel reçoit un crédit approprié.

## Comment l’attribution fonctionne-t-elle avec la segmentation ?

L’attribution s’exécute toujours avant la segmentation et la segmentation s’exécute avant l’application des filtres de rapport. Ce concept s’applique également aux suites de rapports virtuelles utilisant des segments.

Par exemple, si vous créez une suite de rapports virtuelle avec un segment « Accès à l’affichage » appliqué, vous pouvez voir d’autres canaux dans un tableau à l’aide de certains modèles d’attribution.

![Suite de rapports virtuelle, affichage uniquement](assets/vrs-aiq-example.png)

>[!NOTE]
>
>Si un segment supprime les accès contenant votre mesure, ces instances de mesure ne sont attribuées à aucune dimension. Cependant, un filtre de rapport similaire masquera simplement certains éléments de dimension, sans aucun impact sur les mesures traitées par le modèle d’attribution. Par conséquent, un segment peut renvoyer des valeurs inférieures à celles d’un filtre avec une définition comparable.
