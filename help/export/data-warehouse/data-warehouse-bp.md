---
description: Data Warehouse s’accompagne d’une interface souple permettant d’exécuter des rapports personnalisés. Ces pratiques permettent d’accélérer la récupération des données.
keywords: best practices;failure;timeout;troubleshooting
title: Bonnes pratiques relatives à l’Data Warehouse
topic: Data warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Bonnes pratiques relatives à l’Data Warehouse

L’entrepôt de données offre une interface souple pour exécuter des rapports personnalisés. Ces pratiques permettent d’accélérer la récupération des données.



| Instruction | Description |
|--- |--- |
| Exécution de rapports Pages vues, Visites, Visiteurs et autres rapports standard dans les rapports et analyses | Avant de créer un rapport Entrepôt de données, vérifiez si les informations recherchées sont déjà disponibles dans les rapports. Si tel est le cas, le rapport sera diffusé beaucoup plus rapidement en raison du prétraitement effectué par les rapports et analyses pour les mesures courantes. |
| Bien comprendre le volume des données demandées | Un rapport pluriannuel portant sur une vaste suite de rapports peut contenir des dizaines de milliards de lignes de données. Le traitement et l’évaluation de ces données peut prendre des jours, voire des semaines. Évaluez l’utilisation du rapport afin de déterminer si certaines des données pluriannuelles sont disponibles ou si vous pouvez fractionner le rapport en plusieurs requêtes. |
| Faire correspondre la période du rapport à la granularité | Les rapports de granularité nécessitent une durée de traitement plus longue. Dans le cas d’une granularité mensuelle pour une année complète, les rapports sont traités beaucoup plus rapidement si vous envoyez une demande de rapport pour chaque mois. |
| Exécuter des rapports sur des périodes terminées | Les rapports Entrepôt de données sont générés lorsque la période demandée est terminée. Si vous demandez, par exemple, un rapport pour la semaine en cours le mercredi, il ne sera pas généré avant le dimanche de la semaine suivante. |
| Générer des rapports de cheminement dans Data Warehouse | Les mesures de cheminement (entrées, sorties, rebonds, etc.) ne sont pas disponibles dans Data Warehouse. |
| Suites de rapports virtuelles | Dans Data Warehouse, la création de rapports sur les suites de rapports virtuelles prend en charge le fuseau horaire alternatif configuré dans la suite de rapports virtuelle. |
