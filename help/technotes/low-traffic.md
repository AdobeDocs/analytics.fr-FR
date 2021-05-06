---
description: Si un rapport inclut de nombreuses valeurs uniques, Adobe fournit des fonctionnalités permettant de veiller à ce que les valeurs les plus importantes apparaissent dans ce rapport.
title: Valeur de faible trafic dans Adobe Analytics
feature: Mesures
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
translation-type: tm+mt
source-git-commit: 65190776da25437e854e0226cd349e3ba13fc8c9
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 48%

---

# Valeur de faible trafic dans Adobe Analytics

Lorsqu&#39;un rapport comporte de nombreuses valeurs uniques, l&#39;Adobe permet de s&#39;assurer que les valeurs les plus importantes apparaissent dans le rapport. Les valeurs de variable unique collectées après environ 500 000 valeurs existantes sont répertoriées sous une ligne intitulée **[!UICONTROL Faible trafic]**.

## Fonctionnement de [!UICONTROL Faible trafic]

* La création de rapports n’est pas affectée si la variable n’atteint pas 500 000 valeurs uniques au cours d’un mois donné.
* Lorsqu’une variable atteint ce premier seuil de 500 000 valeurs, les données commencent à être groupées dans un compartiment à trafic faible. Chaque valeur dépassant ce seuil suit la logique suivante :
   * Si une valeur est déjà vue dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur n’est pas encore affichée dans les rapports, elle apparaîtra dans la ligne [!UICONTROL Faible trafic]. Si une valeur incluse dans l’élément de ligne [!UICONTROL Faible trafic] est vue un nombre important de fois en peu de temps, elle début être reconnue comme son propre élément de ligne. Le nombre significatif de fois où un élément doit être vu a de nombreuses dépendances, telles que le nombre de serveurs de traitement et de démons qui traitent les données pour cette suite de rapports particulière.
* Si une suite de rapports atteint plus de 1 000 000 de valeurs uniques, un filtrage plus agressif est appliqué :
   * Si une valeur est déjà vue dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur n’est pas encore affichée dans les rapports, elle apparaîtra dans la ligne [!UICONTROL Faible trafic]. Si une valeur incluse dans l’élément de ligne [!UICONTROL Faible trafic] est vue un nombre important de fois en peu de temps, elle début être reconnue comme son propre élément de ligne. Le nombre significatif de fois où un élément doit être vu a de nombreuses dépendances, telles que le nombre de serveurs de traitement et de démons qui traitent les données pour cette suite de rapports particulière.

Pourquoi l’Adobe déplace-t-il un élément de la ligne [!UICONTROL Faible trafic] vers sa propre ligne ? Par exemple, ce déplacement peut reconnaître une nouvelle page ou un nouvel élément populaire qui a été ajouté plus tard dans le mois (après dépassement des valeurs uniques) et qui obtient de nombreux accès/vues. Le déplacement n&#39;est pas destiné à capturer tout ce qui reçoit un certain nombre de visites/vues par jour ou par mois.

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
   * Les valeurs de classification à faible trafic obtenues par l’intermédiaire de l’importateur peuvent être affichées en Data Warehouse. <!-- AN-115871 -->
   * Les valeurs de classification à faible trafic obtenues par l’intermédiaire du créateur de règles *ne peuvent pas* être affichées en Data Warehouse. <!-- AN-122872 -->
