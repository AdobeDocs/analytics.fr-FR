---
description: Data Warehouse s’accompagne d’une interface souple permettant d’exécuter des rapports personnalisés. Ces pratiques permettent d’accélérer la récupération des données.
keywords: bonnes pratiques ; échec ; timeout ; dépannage
seo-description: Data Warehouse s’accompagne d’une interface souple permettant d’exécuter des rapports personnalisés. Ces pratiques permettent d’accélérer la récupération des données.
seo-title: Bonnes pratiques relatives à l'entrepôt de données
solution: Analytics
title: Bonnes pratiques relatives à l'entrepôt de données
topic: Data Warehouse
uuid: d 71 c 9138-22 d 9-4 f 92-885 e -593 f 83 f 2 bb 59
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Bonnes pratiques relatives à l'entrepôt de données

L'entrepôt de données fournit une interface souple permettant d'exécuter des rapports personnalisés. Ces pratiques permettent d’accélérer la récupération des données.



| Instruction | Description |
|--- |--- |
| Exécuter les pages vues, les visites, les visiteurs et d'autres rapports standard dans les rapports et analyses | Avant de créer un rapport Entrepôt de données, vérifiez si les informations recherchées sont déjà disponibles dans les rapports. Si tel est le cas, le rapport est généré beaucoup plus rapidement en raison du prétraitement effectué par les rapports et analyses pour les mesures courantes. |
| Bien comprendre le volume des données demandées | Un rapport pluriannuel portant sur une vaste suite de rapports peut contenir des dizaines de milliards de lignes de données. Le traitement et l’évaluation de ces données peut prendre des jours, voire des semaines. Évaluez l’utilisation du rapport afin de déterminer si certaines des données pluriannuelles sont disponibles ou si vous pouvez fractionner le rapport en plusieurs requêtes. |
| Faire correspondre la période du rapport à la granularité | Les rapports de granularité nécessitent une durée de traitement plus longue. Dans le cas d’une granularité mensuelle pour une année complète, les rapports sont traités beaucoup plus rapidement si vous envoyez une demande de rapport pour chaque mois. |
| Exécuter des rapports sur des périodes terminées | Les rapports Entrepôt de données sont générés lorsque la plage de dates demandée est terminée. Si vous demandez, par exemple, un rapport pour la semaine en cours le mercredi, il ne sera pas généré avant le dimanche de la semaine suivante. |
| Générer des rapports de cheminement dans Data Warehouse | Les mesures de cheminement (entrées, sorties, rebonds, etc.) ne sont pas disponibles dans Data Warehouse. |
| Suites de rapports virtuelles | Dans Data Warehouse, la création de rapports sur les suites de rapports virtuelles prend en charge le fuseau horaire alternatif configuré dans la suite de rapports virtuelle. |