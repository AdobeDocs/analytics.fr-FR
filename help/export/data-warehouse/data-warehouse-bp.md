---
description: Data Warehouse s’accompagne d’une interface souple permettant d’exécuter des rapports personnalisés. Ces pratiques permettent d’accélérer la récupération des données.
keywords: bonnes pratiques;échec;délai d’expiration;dépannage
title: Bonnes pratiques relatives à Data Warehouse
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
source-git-commit: 2ed0627efe50c000c9fe440fccafd12739b09554
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 89%

---

# Bonnes pratiques relatives à Data Warehouse

Data Warehouse s’accompagne d’une interface souple permettant d’exécuter des rapports personnalisés. Suivez les instructions ci-dessous pour réduire le temps nécessaire à la récupération des données :

| Instruction | Description |
|--- |--- |
| Exécuter des rapports Pages vues, Visites, Visiteurs et d’autres rapports standard dans Reports &amp; Analytics | Avant de créer un rapport Data Warehouse, vérifiez si les informations recherchées sont déjà disponibles dans les rapports. Si tel est le cas, le rapport est généré bien plus rapidement compte tenu du prétraitement effectué par les Reports &amp; Analytics pour les mesures communes. |
| Bien comprendre le volume des données demandées | Un rapport pluriannuel portant sur une vaste suite de rapports peut contenir des dizaines de milliards de lignes de données. Le traitement et l’évaluation de ces données peuvent prendre des jours, voire des semaines. Évaluez l’utilisation du rapport afin de déterminer si certaines des données pluriannuelles sont disponibles ou si vous pouvez fractionner le rapport en plusieurs requêtes. |
| Faire correspondre la période du rapport à la granularité | Les rapports de granularité nécessitent une durée de traitement plus longue. Dans le cas d’une granularité mensuelle pour une année complète, les rapports sont traités beaucoup plus rapidement si vous envoyez une demande de rapport pour chaque mois. |
| Exécuter des rapports sur des périodes terminées | Les rapports Data Warehouse sont générés lorsque la période qui fait l’objet de la demande est terminée. Si vous demandez, par exemple, un rapport pour la semaine en cours le mercredi, il ne sera pas généré avant le dimanche de la semaine suivante. |
| Générer des rapports de cheminement dans Data Warehouse | Les mesures de cheminement (entrées, sorties, rebonds, etc.) ne sont pas disponibles dans l’entrepôt de données. |
| Suites de rapports virtuelles | Dans Data Warehouse, la création de rapports sur les suites de rapports virtuelles prend en charge le fuseau horaire alternatif configuré dans la suite de rapports virtuelle. |

