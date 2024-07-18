---
description: Lorsqu’un rapport contient de nombreuses valeurs uniques, Adobe utilise l’élément de dimension Faible trafic pour améliorer les performances du rapport.
title: Valeur de faible trafic dans Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: ba0d4c0897ab50ab40cdfdfbffe50f6cf3bd8c7b
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 100%

---

# Valeur de faible trafic dans Adobe Analytics

Si un rapport inclut de nombreuses valeurs uniques, Adobe fournit des fonctionnalités permettant de veiller à ce que les valeurs les plus importantes apparaissent dans ce rapport. Les valeurs de variable uniques collectées au-delà d’un certain seuil (voir ci-dessous) sont répertoriées sous un élément de dimension intitulé **[!UICONTROL Faible trafic]**.

## Fonctionnement du [!UICONTROL Faible trafic]

* Adobe Analytics utilise deux seuils pour déterminer les valeurs uniques qui s’affichent dans les rapports chaque mois : un **[!UICONTROL seuil bas]** et un **[!UICONTROL seuil élevé]**. Ces seuils peuvent être ajustés par Adobe de temps à autre. Les limites de seuil actuelles sont les suivantes :
   * **[!UICONTROL Seuil bas]** : plus de 2 000 000 valeurs uniques par mois.
   * **[!UICONTROL Seuil élevé]** : plus de 2 100 000 valeurs uniques par mois.
* La création de rapports n’est pas affectée si la variable n’atteint pas le seuil bas au cours d’un mois donné.
* Lorsqu’une variable atteint le seuil bas, les données commencent à être groupées dans un compartiment, sous [!UICONTROL Faible trafic]. Chaque valeur dépassant ce seuil suit la logique suivante :
   * Si une valeur figure déjà dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur ne figure pas encore dans les rapports, elle sera, au départ, intégrée dans un compartiment, dans l’élément de dimension [!UICONTROL Faible trafic].
   * Si une valeur intégrée à un compartiment sous [!UICONTROL Faible trafic] reçoit un afflux de trafic (généralement un nombre d’instances à deux chiffres en un seul jour), elle commence à être admise comme constituant son propre élément de dimension. Les instances collectées et n’ayant pas atteint le seuil restent sous [!UICONTROL Faible trafic]. Le moment exact auquel l’élément de dimension commence à s’afficher dans les rapports dépend de nombreux facteurs, tels que le nombre de serveurs traitant les données pour la suite de rapports et la durée entre chaque instance d’élément de dimension.
* Si une variable atteint le seuil élevé, un filtrage plus agressif est appliqué. Avant de pouvoir être admises comme constituant leur propre élément de dimension, les valeurs uniques nécessitent des instances à trois chiffres sur une seule journée.

Cette logique permet à Adobe d’optimiser les capacités de création de rapports, tout en permettant à votre organisation de créer des rapports sur les éléments de dimension cruciaux collectés plus tard dans le mois. Par exemple, si votre organisation gère un site contenant des millions d’articles et qu’un nouvel article devient populaire vers la fin du mois (après avoir dépassé les deux seuils uniques), vous pouvez tout de même analyser ses performances sans qu’il ne soit intégré dans un compartiment, sous [!UICONTROL Faible trafic]. Cette logique ne cherche pas à distinguer tous les articles qui reçoivent un certain nombre de vues de page par jour ou par mois.

>[!NOTE]
>La dimension [Page](../components/dimensions/page.md) utilise plusieurs colonnes de serveur principal qui sont toutes prises en compte pour les seuils uniques, y compris `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url` et `click_context`. Ces colonnes peuvent entraîner l’application d’une logique de [!UICONTROL Faible trafic] bien avant que le nombre d’éléments de dimension Page unique n’atteigne le seuil bas dans Workspace.

Notez que la logique de faible trafic décrite ci-dessus est optimisée avec des variables qui comportent des éléments de dimension qui se reproduisent plusieurs fois au cours du mois. Si les éléments de dimension d’une variable sont presque ou entièrement uniques à chaque accès, la variable atteint rapidement le seuil bas et tous les nouveaux éléments de dimension pour le mois se retrouveront dans le compartiment à faible trafic.

## Modification des seuils de limite uniques

Ces limites de seuil peuvent parfois être modifiées pour chaque variable. Contactez l’assistance clientèle d’Adobe ou votre équipe Adobe en charge des comptes pour demander ce changement. L’augmentation pouvant être appliquée aux seuils dépend de plusieurs facteurs et Adobe peut ne pas être en mesure de réaliser ces augmentations de seuil dans tous les cas. Lorsque vous demandez une modification, incluez :

* l’identifiant de la suite de rapports ;
* la variable pour laquelle vous souhaitez augmenter le seuil ;
* les premier et second seuils souhaités.

Les modifications de seuils peuvent avoir un impact sur les performances des rapports. Adobe conseille de faire preuve de prudence avant de demander une augmentation de valeurs uniques dans une variable. Augmentez uniquement les limites uniques pour les variables qui sont essentielles aux besoins de création de rapports de votre organisation.

Les seuils de faible trafic ne sont pas visibles dans l’interface utilisateur d’Analytics. Contactez l’assistance clientèle d’Adobe si vous souhaitez plus d’informations sur les seuils existants.

## Composants à faible trafic et autres fonctionnalités

Diverses fonctionnalités traitent des valeurs à faible trafic de différentes manières.

* **Data Warehouse :** il n’y a pas de limite au nombre de valeurs uniques dans les rapports d’entrepôt de données. L’architecture d’entrepôt unique permet de créer des rapports pour n’importe quel nombre de valeurs uniques.
   * Dans un nombre limité de scénarios, des valeurs à faible trafic peuvent continuer à apparaître. Il peut s’agir de variables de liste, de props de liste, d’eVars de marchandisage et de dimensions détaillées des canaux marketing.
* **Segmentation :** si les critères de segment incluent une variable avec un grand nombre de valeurs uniques, les valeurs capturées sous en trafic faible ne sont pas incluses.
* **Classifications :** les rapports de classification sont également soumis à des limites uniques. Si la valeur de variable parente d’une classification est incluse dans le compartiment à faible trafic, la valeur n’est pas classée.
   * Les valeurs de classification de faible trafic obtenues par lʼintermédiaire de lʼimportateur peuvent être affichées dans Data Warehouse. <!-- AN-115871 -->
   * Les valeurs de classification de faible trafic obtenues par lʼintermédiaire du créateur de règles *ne peuvent pas* être affichées dans Data Warehouse. <!-- AN-122872 -->
