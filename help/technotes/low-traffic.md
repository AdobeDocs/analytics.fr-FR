---
description: Lorsqu'un rapport comporte un grand nombre de valeurs uniques, Adobe offre une fonctionnalité garantissant que les valeurs les plus importantes apparaissent dans le rapport.
seo-description: Lorsqu'un rapport comporte un grand nombre de valeurs uniques, Adobe offre une fonctionnalité garantissant que les valeurs les plus importantes apparaissent dans le rapport.
seo-title: Valeur faible trafic dans Adobe Analytics
solution: Analytics
title: Valeur faible trafic dans Adobe Analytics
topic: Mesures
uuid: 56 f 723 f 8-94 e 8-478 f -8 ea 3-16 dad 21 dfa 1 f
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Valeur faible trafic dans Adobe Analytics

Lorsqu'un rapport comporte un grand nombre de valeurs uniques, Adobe offre une fonctionnalité garantissant que les valeurs les plus importantes apparaissent dans le rapport. Unique variable values collected after approximately 500,000 existing values are listed under a line item titled **(Low-Traffic)**.

## Fonctionnement du trafic faible

* La création de rapports n'est pas affectée si la variable n'atteint pas 500 000 valeurs uniques au cours d'un mois donné.
* Lorsqu'une variable atteint ce premier seuil de 500 000, les données commencent à être regroupées sous faible trafic. Chaque valeur dépassant ce seuil passe par la logique suivante :
   * Si une valeur figure déjà dans les rapports, ajoutez-la comme d'habitude.
   * Si une valeur ne figure pas encore dans les rapports, vérifiez si cette valeur a été vue plus de dix fois aujourd'hui. Si tel est le cas, ajoutez cette valeur à la création de rapports. S'il n'a pas été comptabilisé plus de dix fois, laissez-le sous faible trafic.
* Si une suite de rapports atteint plus de 1 000 000 valeurs uniques, un filtrage plus agressif est appliqué :
   * Si une valeur figure déjà dans les rapports, ajoutez-la comme d'habitude.
   * Si une valeur ne figure pas encore dans les rapports, vérifiez si cette valeur a été vue plus de 100 fois aujourd'hui. Si tel est le cas, ajoutez la valeur à la création de rapports. Dans le cas contraire, laissez-le sous faible trafic.

> [!NOTE] Si une valeur de variable reçoit suffisamment de trafic pour quitter le compartiment de trafic modéré, les premières valeurs collectées ne se déplacent pas vers la ligne correspondante. Ces 10-100 premières instances restent sous faible trafic.

## Modification des seuils limite uniques

Par défaut, les limites correspondent à 500 000 et à 1 million de valeurs uniques. Ces limites peuvent être modifiées par variable. Contactez le gestionnaire de compte de votre entreprise pour demander cette modification. Lorsque vous demandez une modification, incluez :

* Identifiant de la suite de rapports
* La variable que vous souhaitez augmenter pour le seuil
* Le premier et le second seuil souhaités

Cette modification peut s'accompagner d'un coût supplémentaire et dépend du contrat. Les modifications apportées aux seuils peuvent également affecter les performances des rapports. Adobe recommande vivement d'utiliser un bon jugement lorsque vous demandez une augmentation des valeurs uniques d'une variable.

Les seuils de faible trafic ne sont pas visibles dans l'interface utilisateur d'Analytics. Demandez à un utilisateur pris en charge de votre organisation de contacter le service d'assistance clientèle si vous souhaitez plus d'informations sur les seuils existants.

## Faible trafic à l'aide de composants et d'autres fonctionnalités

Différentes fonctionnalités traitent les valeurs de faible trafic de différentes manières.

* **Entrepôt de données :** Le nombre de valeurs uniques dans les rapports Entrepôt de données n'est pas limité. Son architecture unique permet de créer des rapports sur n'importe quel nombre de valeurs uniques.
   * Dans certains scénarios limités, les valeurs de faible trafic peuvent toujours apparaître. Les exemples incluent les variables de liste, les props de liste, les evars de marchandisage et les portées détaillées de canal marketing.
* **Segmentation :** Si les critères de segment comprennent une variable avec un nombre élevé de valeurs uniques, les valeurs capturées sous faible trafic ne sont pas incluses.
* **Classifications :** Les rapports de classification sont également soumis à des limites uniques. Si la valeur de variable parente d'une classification est incluse sous faible trafic, la valeur n'est pas classée.
   * Si vous classez les valeurs avant qu'elles ne soient visibles dans les données, elles sont comptabilisées dans le seuil unique de ce mois.
