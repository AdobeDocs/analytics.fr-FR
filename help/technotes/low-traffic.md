---
description: Lorsqu’un rapport contient de nombreuses valeurs uniques, Adobe utilise l’élément de dimension Faible trafic pour améliorer les performances du rapport.
title: Valeur de faible trafic dans Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: d3a959d128f4740fd98ff40e5b92a3ea983d3c05
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 31%

---

# Valeur de faible trafic dans Adobe Analytics

Si un rapport inclut de nombreuses valeurs uniques, Adobe fournit des fonctionnalités permettant de veiller à ce que les valeurs les plus importantes apparaissent dans ce rapport. Les valeurs de variable uniques collectées au-delà d’un certain seuil (voir ci-dessous) sont répertoriées sous un élément de dimension intitulé **[!UICONTROL Faible trafic]**.

## Fonctionnement du [!UICONTROL Faible trafic]

* Adobe Analytics utilise deux seuils pour déterminer les valeurs uniques qui s’affichent dans les rapports chaque mois : A **[!UICONTROL seuil inférieur]** et un **[!UICONTROL seuil élevé]**. Ces seuils peuvent être ajustés par Adobe de temps à autre. Les limites de seuil actuelles sont les suivantes :
   * **[!UICONTROL Seuil faible]**: plus de 500 000 valeurs uniques par mois.
   * **[!UICONTROL Seuil élevé]**: plus de 1 000 000 valeurs uniques par mois.
* La création de rapports n’est pas affectée si la variable n’atteint pas le seuil inférieur au cours d’un mois donné.
* Lorsqu’une variable atteint le seuil inférieur, les données commencent à être regroupées sous [!UICONTROL Faible trafic]. Chaque valeur dépassant ce seuil suit la logique suivante :
   * Si une valeur figure déjà dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur n’est pas encore affichée dans les rapports, elle est initialement regroupée dans la variable [!UICONTROL Faible trafic] élément de dimension.
   * Si une valeur est regroupée sous [!UICONTROL Faible trafic] reçoit un afflux de trafic (généralement des instances à deux chiffres en un seul jour), il commence à être reconnu comme son propre élément de dimension. Les instances collectées avant d’atteindre le seuil restent inférieures à [!UICONTROL Faible trafic]. Le moment exact auquel l’élément de dimension commence à s’afficher dans les rapports comporte de nombreuses dépendances, telles que le nombre de serveurs traitant les données pour la suite de rapports et la durée entre chaque instance d’élément de dimension.
* Si une variable atteint le seuil élevé, un filtrage plus agressif est appliqué. Les valeurs uniques nécessitent des instances à trois chiffres en un seul jour avant d’être reconnues comme son propre élément de dimension.

Cette logique permet à l’Adobe d’optimiser les fonctionnalités de création de rapports tout en permettant à votre entreprise de créer des rapports sur les éléments de dimension cruciaux collectés plus tard dans le mois. Par exemple, si votre entreprise exécute un site contenant des millions d’articles et qu’un nouvel article devient populaire vers la fin du mois (après avoir dépassé les deux seuils uniques), vous pouvez tout de même analyser les performances de cet article sans qu’il ne soit placé sous [!UICONTROL Faible trafic]. Cette logique n’est pas destinée à supprimer le regroupement de tout ce qui obtient un certain nombre de pages vues par jour ou par mois.

>[!NOTE]
>La variable [Page](../components/dimensions/page.md) La dimension utilise plusieurs colonnes du serveur principal qui sont toutes prises en compte pour les seuils uniques, y compris `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`, et `click_context`. Ces colonnes peuvent provoquer [!UICONTROL Faible trafic] s’appliquer bien avant que le nombre d’éléments de dimension Page uniques dans Workspace n’atteigne le seuil inférieur.

Notez que la logique de faible trafic décrite ci-dessus fonctionne mieux avec les variables qui comportent des éléments de dimension qui se reproduisent plusieurs fois au cours du mois. Si les éléments de dimension d’une variable sont presque ou entièrement uniques à chaque accès, la variable atteint rapidement le seuil inférieur et tous les nouveaux éléments de dimension pour le mois se retrouveront dans le compartiment à faible trafic.

## Modification des seuils de limite uniques

Les limites de seuil peuvent parfois être modifiées selon chaque variable. Contactez l’Assistance clientèle d’Adobe ou votre équipe de compte d’Adobe pour demander cette modification. La mesure dans laquelle les seuils peuvent être augmentés dépend de plusieurs facteurs et l’Adobe peut ne pas être en mesure de tenir compte des augmentations de seuils dans tous les cas. Lorsque vous demandez une modification, incluez :

* l’identifiant de la suite de rapports ;
* la variable pour laquelle vous souhaitez augmenter le seuil ;
* les premier et second seuils souhaités.

Les modifications de seuils peuvent avoir un impact sur les performances des rapports. Adobe recommande vivement d’utiliser un bon jugement lorsque vous demandez une augmentation des valeurs uniques dans une variable. Augmentez uniquement les limites uniques pour les variables qui sont essentielles aux besoins de création de rapports de votre entreprise.

Les seuils de faible trafic ne sont pas visibles dans l’interface utilisateur d’Analytics. Contactez l’assistance clientèle d’Adobe si vous souhaitez plus d’informations sur les seuils existants.

## Composants à faible trafic et autres fonctionnalités

Diverses fonctionnalités traitent des valeurs à faible trafic de différentes manières.

* **Data Warehouse :** il n’y a pas de limite au nombre de valeurs uniques dans les rapports d’entrepôt de données. L’architecture d’entrepôt unique permet de créer des rapports pour n’importe quel nombre de valeurs uniques.
   * Dans un nombre limité de scénarios, des valeurs à faible trafic peuvent continuer à apparaître. Il peut s’agir de variables de liste, de props de liste, d’eVars de marchandisage et de dimensions détaillées des canaux marketing.
* **Segmentation :** si les critères de segment incluent une variable avec un grand nombre de valeurs uniques, les valeurs capturées sous en trafic faible ne sont pas incluses.
* **Classifications :** les rapports de classification sont également soumis à des limites uniques. Si la valeur de variable parente d’une classification est incluse dans le compartiment à faible trafic, la valeur n’est pas classée.
   * Les valeurs de classification de faible trafic obtenues par lʼintermédiaire de lʼimportateur peuvent être affichées dans Data Warehouse. <!-- AN-115871 -->
   * Les valeurs de classification de faible trafic obtenues par lʼintermédiaire du créateur de règles *ne peuvent pas* être affichées dans Data Warehouse. <!-- AN-122872 -->
