---
description: Lorsqu’un rapport contient de nombreuses valeurs uniques, Adobe utilise l’élément de dimension Faible trafic pour améliorer les performances du rapport.
title: Valeur de faible trafic dans Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 46%

---

# Valeur de faible trafic dans Adobe Analytics

Si un rapport inclut de nombreuses valeurs uniques, Adobe fournit des fonctionnalités permettant de veiller à ce que les valeurs les plus importantes apparaissent dans ce rapport. Les valeurs de variable uniques collectées après environ 500 000 valeurs existantes sont répertoriées sous un élément de dimension intitulé **[!UICONTROL Faible trafic]**.

## Fonctionnement du [!UICONTROL Faible trafic]

* La création de rapports n’est pas affectée si la variable n’atteint pas 500 000 valeurs uniques au cours d’un mois donné.
* Lorsqu’une variable atteint 500 000 valeurs uniques, les données commencent à être regroupées sous [!UICONTROL Faible trafic]. Chaque valeur dépassant ce seuil suit la logique suivante :
   * Si une valeur figure déjà dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur n’est pas encore affichée dans les rapports, elle est initialement regroupée dans la variable [!UICONTROL Faible trafic] élément de dimension.
   * Si une valeur est regroupée sous [!UICONTROL Faible trafic] reçoit un afflux de trafic (généralement des instances à deux chiffres en un seul jour), il commence à être reconnu comme son propre élément de dimension. Les instances collectées avant d’atteindre le seuil restent inférieures à [!UICONTROL Faible trafic]. Le seuil exact comporte de nombreuses dépendances, telles que le nombre de serveurs qui traitent les données pour la suite de rapports et la durée entre chaque instance d’élément de dimension.
* Si une suite de rapports atteint plus de 1 000 000 valeurs uniques, un filtrage plus agressif est appliqué. Les valeurs uniques nécessitent des instances à trois chiffres en un seul jour avant d’être reconnues comme son propre élément de dimension.

Cette logique permet à l’Adobe d’optimiser les fonctionnalités de création de rapports tout en permettant à votre entreprise de créer des rapports sur les éléments de dimension cruciaux collectés plus tard dans le mois. Par exemple, votre entreprise gère un site contenant des millions d’articles. Un nouvel article est devenu populaire à la fin du mois (après avoir dépassé les deux seuils uniques). Vous pouvez toujours analyser les performances de cet article sans qu’il soit regroupé sous [!UICONTROL Faible trafic]. Cette logique n’est pas destinée à supprimer le regroupement de tout ce qui obtient un certain nombre de pages vues par jour ou par mois.

>[!NOTE]
>Le [Page](../components/dimensions/page.md) La dimension utilise plusieurs colonnes du serveur principal qui sont toutes prises en compte pour les seuils uniques, y compris `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`, et `click_context`. Ces colonnes peuvent provoquer [!UICONTROL Faible trafic] s’appliquer bien avant que le nombre d’éléments de dimension Page uniques dans Workspace n’atteigne 500 000.

## Modification des seuils de limite uniques

Par défaut, les limites correspondent à 500 000 et à 1 million de valeurs uniques. Ces limites peuvent être modifiées selon chaque variable. Contactez l’Assistance clientèle d’Adobe ou votre équipe de compte d’Adobe pour demander cette modification. Lorsque vous demandez une modification, incluez :

* l’identifiant de la suite de rapports ;
* la variable pour laquelle vous souhaitez augmenter le seuil ;
* les premier et second seuils souhaités.

Les modifications de seuils peuvent avoir un impact sur les performances des rapports. Adobe conseille de faire preuve de prudence avant de demander une augmentation de valeurs uniques dans une variable. Augmentez uniquement les limites uniques pour les variables qui sont essentielles aux besoins de création de rapports de votre entreprise.

Les seuils de faible trafic ne sont pas visibles dans l’interface utilisateur d’Analytics. Contactez l’assistance clientèle d’Adobe si vous souhaitez plus d’informations sur les seuils existants.

## Composants à faible trafic et autres fonctionnalités

Diverses fonctionnalités traitent des valeurs à faible trafic de différentes manières.

* **Data Warehouse :** il n’y a pas de limite au nombre de valeurs uniques dans les rapports d’entrepôt de données. L’architecture d’entrepôt unique permet de créer des rapports pour n’importe quel nombre de valeurs uniques.
   * Dans un nombre limité de scénarios, des valeurs à faible trafic peuvent continuer à apparaître. Il peut s’agir de variables de liste, de props de liste, d’eVars de marchandisage et de dimensions détaillées des canaux marketing.
* **Segmentation :** si les critères de segment incluent une variable avec un grand nombre de valeurs uniques, les valeurs capturées sous en trafic faible ne sont pas incluses.
* **Classifications :** les rapports de classification sont également soumis à des limites uniques. Si la valeur de variable parente d’une classification est incluse dans le compartiment à faible trafic, la valeur n’est pas classée.
   * Les valeurs de classification de faible trafic obtenues par lʼintermédiaire de lʼimportateur peuvent être affichées dans Data Warehouse. <!-- AN-115871 -->
   * Les valeurs de classification de faible trafic obtenues par lʼintermédiaire du créateur de règles *ne peuvent pas* être affichées dans Data Warehouse. <!-- AN-122872 -->
