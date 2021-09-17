---
description: Si un rapport inclut de nombreuses valeurs uniques, Adobe fournit des fonctionnalités permettant de veiller à ce que les valeurs les plus importantes apparaissent dans ce rapport.
title: Valeur de faible trafic dans Adobe Analytics
feature: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 7036c6d3bc15c2cb7bd62af79229052cd772f8f8
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 93%

---

# Valeur de faible trafic dans Adobe Analytics

Si un rapport inclut de nombreuses valeurs uniques, Adobe fournit des fonctionnalités permettant de veiller à ce que les valeurs les plus importantes apparaissent dans ce rapport. Les valeurs de variable uniques collectées après environ 500 000 valeurs existantes sont répertoriées sous l’élément de ligne **[!UICONTROL Faible trafic]**.

## Fonctionnement du [!UICONTROL Faible trafic]

* La création de rapports n’est pas affectée si la variable n’atteint pas 500 000 valeurs uniques au cours d’un mois donné.
* Lorsqu’une variable atteint ce premier seuil de 500 000 valeurs, les données commencent à être groupées dans un compartiment à trafic faible. Chaque valeur dépassant ce seuil suit la logique suivante :
   * Si une valeur figure déjà dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur ne figure pas encore dans les rapports, elle apparaîtra sur l’élément de ligne [!UICONTROL Faible trafic]. Si une valeur qui a été incluse dans l’élément de ligne [!UICONTROL Faible trafic] est vue un nombre important de fois en peu de temps, elle commence à être reconnue comme son propre élément de ligne Le nombre significatif de fois où un élément doit apparaître comporte de nombreuses dépendances, telles que le nombre de serveurs de traitement et de daemons qui traitent les données pour cette suite de rapports spécifique.
* Si une suite de rapports atteint plus de 1 000 000 de valeurs uniques, un filtrage plus agressif est appliqué :
   * Si une valeur figure déjà dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur ne figure pas encore dans les rapports, elle apparaîtra sur l’élément de ligne [!UICONTROL Faible trafic]. Si une valeur qui a été incluse dans l’élément de ligne [!UICONTROL Faible trafic] est vue un nombre important de fois en peu de temps, elle commence à être reconnue comme son propre élément de ligne Le nombre significatif de fois où un élément doit apparaître comporte de nombreuses dépendances, telles que le nombre de serveurs de traitement et de daemons qui traitent les données pour cette suite de rapports spécifique.

Pourquoi Adobe déplace-t-il un élément de la ligne [!UICONTROL Faible trafic] vers son propre élément de ligne ? Par exemple, ce déplacement peut être dû à la reconnaissance d’une nouvelle page ou d’un nouvel élément populaire qui a été ajouté plus tard dans le mois (après le dépassement des valeurs uniques) et qui obtient de nombreux accès/vues. Le déplacement n’est pas destiné à capturer tout ce qui reçoit un certain nombre d’accès/vues par jour ou par mois.

>[!NOTE]
>Le nombre de recherche de page n’inclut pas uniquement les valeurs du [!UICONTROL pagename]/[!UICONTROL page_url]. Le tableau de recherche de page comprend plusieurs colonnes/champs tels que [!UICONTROL pagename], [!UICONTROL first_hit_pagename]/[!UICONTROL page_url], [!UICONTROL visit_pagename]/[!UICONTROL page_url] et le clic (l’ancien contexte) données de mappage).

## Modification des seuils de limite uniques

Par défaut, les limites correspondent à 500 000 et à 1 million de valeurs uniques. Ces limites peuvent être modifiées selon chaque variable. Contactez le gestionnaire de compte de votre organisation pour demander cette modification. Lorsque vous demandez une modification, incluez :

* l’identifiant de la suite de rapports ;
* la variable pour laquelle vous souhaitez augmenter le seuil ;
* les premier et second seuils souhaités.

Les modifications de seuils peuvent avoir un impact sur les performances des rapports. Adobe conseille de faire preuve de prudence avant de demander une augmentation de valeurs uniques dans une variable.

Les seuils de faible trafic ne sont pas visibles dans l’interface utilisateur d’Analytics. Si vous souhaitez plus d’informations sur les seuils existants, demandez à un utilisateur habilité de votre organisation de contacter l’assistance clientèle d’Adobe.

## Composants à faible trafic et autres fonctionnalités

Diverses fonctionnalités traitent des valeurs à faible trafic de différentes manières.

* **Data Warehouse :** il n’y a pas de limite au nombre de valeurs uniques dans les rapports d’entrepôt de données. L’architecture d’entrepôt unique permet de créer des rapports pour n’importe quel nombre de valeurs uniques.
   * Dans un nombre limité de scénarios, des valeurs à faible trafic peuvent continuer à apparaître. Il peut s’agir de variables de liste, de props de liste, d’eVars de marchandisage et de dimensions détaillées des canaux marketing.
* **Segmentation :** si les critères de segment incluent une variable avec un grand nombre de valeurs uniques, les valeurs capturées sous en trafic faible ne sont pas incluses.
* **Classifications :** les rapports de classification sont également soumis à des limites uniques. Si la valeur de variable parente d’une classification est incluse dans le compartiment à faible trafic, la valeur n’est pas classée.
   * Les valeurs de classification de faible trafic obtenues par lʼintermédiaire de lʼimportateur peuvent être affichées dans Data Warehouse. <!-- AN-115871 -->
   * Les valeurs de classification de faible trafic obtenues par lʼintermédiaire du créateur de règles *ne peuvent pas* être affichées dans Data Warehouse. <!-- AN-122872 -->
