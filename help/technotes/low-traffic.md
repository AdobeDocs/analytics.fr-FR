---
description: Lorsqu’un rapport comporte un grand nombre de valeurs uniques, Adobe propose une fonctionnalité qui permet de s’assurer que les valeurs les plus importantes apparaissent dans votre rapport.
title: Valeur de faible trafic dans Adobe Analytics
topic: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Valeur de faible trafic dans Adobe Analytics

Lorsqu’un rapport comporte un grand nombre de valeurs uniques, Adobe propose une fonctionnalité qui permet de s’assurer que les valeurs les plus importantes apparaissent dans votre rapport. Les valeurs de variable unique collectées après environ 500 000 valeurs existantes sont répertoriées sous un élément de ligne intitulé **(Faible trafic)**.

## Fonctionnement du faible trafic

* La création de rapports n’est pas affectée si la variable n’atteint pas 500 000 valeurs uniques au cours d’un mois donné.
* Lorsqu’une variable atteint ce premier seuil de 500 000, les données commencent à être regroupées sous un trafic faible. Chaque valeur au-delà de ce seuil suit la logique suivante :
   * Si une valeur figure déjà dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur n’est pas encore dans la création de rapports, vérifiez si elle a été vue plus de dix fois environ aujourd’hui. Si tel est le cas, ajoutez cette valeur à la création de rapports. S'il n'a pas été compté plus de dix fois, laissez-le sous faible trafic.
* Si une suite de rapports atteint plus de 1 000 000 valeurs uniques, un filtrage plus agressif est appliqué :
   * Si une valeur figure déjà dans les rapports, ajoutez-la comme d’habitude.
   * Si une valeur n’est pas encore incluse dans le rapport, vérifiez si elle a été vue plus de 100 fois aujourd’hui environ. Si tel est le cas, ajoutez la valeur à la création de rapports. Si ce n'est pas le cas, laissez-le sous faible trafic.

> [!NOTE] Si une valeur de variable reçoit suffisamment de trafic pour quitter le compartiment à faible trafic, les premières valeurs collectées ne passent pas à l’élément de ligne correspondant. Ces 10 à 100 premières instances restent sous faible trafic.

## Modification des seuils de limite uniques

Par défaut, les limites correspondent à 500 000 et à 1 million de valeurs uniques. Ces limites peuvent être modifiées par variable. Contactez le gestionnaire de compte de votre organisation pour demander cette modification. Lorsque vous demandez une modification, incluez :

* Identifiant de la suite de rapports
* La variable pour laquelle vous souhaitez augmenter le seuil
* Le premier et le second seuil sont souhaités

Les modifications apportées aux seuils peuvent avoir un impact sur les performances des rapports. Adobe recommande vivement de faire preuve de jugement lorsque vous demandez une augmentation des valeurs uniques dans une variable.

Les seuils de faible trafic ne sont pas visibles dans l’interface utilisateur d’Analytics. Si vous souhaitez plus d’informations sur les seuils existants, demandez à un utilisateur ayant souscrit un plan d’assistance dédié de contacter le service d’assistance clientèle d’Adobe.

## Faible trafic à l’aide de composants et d’autres fonctionnalités

Les différentes fonctionnalités traitent les valeurs à faible trafic de différentes manières.

* **** Entrepôt de données : Le nombre de valeurs uniques dans les rapports Entrepôt de données n’est pas limité. Son architecture unique permet la création de rapports sur n’importe quel nombre de valeurs uniques.
   * Dans certains scénarios limités, des valeurs de faible trafic peuvent toujours apparaître. Par exemple, les variables de liste, les props de liste, les eVars de marchandisage et les dimensions détaillées des canaux marketing.
* **** Segmentation : Si les critères de segment incluent une variable avec un grand nombre de valeurs uniques, les valeurs capturées sous le trafic faible ne sont pas incluses.
* **** Classifications : Les rapports de classification sont également soumis à des limites uniques. Si la valeur de variable parente d’une classification est incluse sous Faible trafic, la valeur n’est pas classée.
   * Si vous classifiez les valeurs avant qu’elles ne soient affichées dans les données, elles sont comptabilisées dans le seuil unique pour ce mois.
