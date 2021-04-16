---
description: Si un rapport inclut de nombreuses valeurs uniques, Adobe fournit des fonctionnalités permettant de veiller à ce que les valeurs les plus importantes apparaissent dans ce rapport.
title: Valeur de faible trafic dans Adobe Analytics
feature: Mesures
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 94%

---

# Valeur de faible trafic dans Adobe Analytics

Si un rapport inclut de nombreuses valeurs uniques, Adobe fournit des fonctionnalités permettant de veiller à ce que les valeurs les plus importantes apparaissent dans ce rapport. Les valeurs de variable uniques collectées après environ 500 000 valeurs existantes sont répertoriées sous l’élément de ligne **(Faible trafic)**.

## Fonctionnement du faible trafic

* La création de rapports n’est pas affectée si la variable n’atteint pas 500 000 valeurs uniques au cours d’un mois donné.
* Lorsqu’une variable atteint ce premier seuil de 500 000 valeurs, les données commencent à être groupées dans un compartiment à trafic faible. Chaque valeur dépassant ce seuil suit la logique suivante :
   * Si une valeur est déjà incluse dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur n’est pas encore incluse dans les rapports, vérifiez si elle a été consultée plus de dix fois environ aujourd’hui. Si tel est le cas, ajoutez cette valeur aux rapports. Si elle n’a pas été comptée plus de dix fois environ, laissez-la en faible trafic.
* Si une suite de rapports atteint plus de 1 000 000 de valeurs uniques, un filtrage plus agressif est appliqué :
   * Si une valeur est déjà incluse dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur n’est pas encore incluse dans les rapports, vérifiez si elle a été consultée plus d’environ 100 fois aujourd’hui. Si c’est le cas, ajoutez la valeur aux rapports. Si ce n’est pas le cas, laissez-la en faible trafic.

>[!NOTE]
>
>Si une valeur de variable reçoit suffisamment de trafic pour quitter le compartiment à faible trafic, les premières valeurs collectées ne sont pas transmises à l’élément de ligne correspondant. Ces 10 à 100 premières instances restent en faible trafic.

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
