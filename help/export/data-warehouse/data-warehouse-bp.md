---
description: Découvrez les instructions qui permettent de réduire le temps nécessaire à la récupération des données de Data Warehouse.
keywords: bonnes pratiques;échec;délai d’expiration;dépannage
title: Bonnes pratiques relatives à Data Warehouse
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
TQID: https://experienceleague.adobe.com/fWshdRnbrh11kLLT3DiW0a-qMJ13o8v4EMH-t-ceWC8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 78%

---

# Bonnes pratiques relatives à Data Warehouse

Data Warehouse s’accompagne d’une interface souple permettant d’exécuter des rapports personnalisés. Suivez les instructions suivantes pour réduire le temps nécessaire à la récupération des données :

| Instruction | Description |
|--- |--- |
| Bien comprendre le volume des données demandées | Un rapport pluriannuel portant sur une vaste suite de rapports peut contenir des dizaines de milliards de lignes de données. Le traitement et l’évaluation de ces données peuvent prendre des jours, voire des semaines. Évaluez l’utilisation du rapport afin de déterminer si certaines des données pluriannuelles sont disponibles ou si vous pouvez fractionner le rapport en plusieurs requêtes. |
| Faire correspondre la période du rapport à la granularité | Les rapports de granularité nécessitent une durée de traitement plus longue. Dans le cas d’une granularité mensuelle pour une année complète, les rapports sont traités beaucoup plus rapidement si vous envoyez une demande de rapport pour chaque mois. |
| Exécuter des rapports sur des périodes terminées | Les rapports Data Warehouse sont générés lorsque la période qui fait l’objet de la demande est terminée. Si vous demandez, par exemple, un rapport pour la semaine en cours le mercredi, il ne sera pas généré avant le dimanche de la semaine suivante. |
| Générer des rapports de cheminement dans Data Warehouse | Mesures de cheminement (entrées, sorties, bounces, etc.) ne sont pas disponibles dans l’entrepôt de données. |
| Suites de rapports virtuelles | Dans Data Warehouse, la création de rapports sur les suites de rapports virtuelles prend en charge le fuseau horaire alternatif configuré dans la suite de rapports virtuelle. |

