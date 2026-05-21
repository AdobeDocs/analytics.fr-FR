---
description: Découvrez comment les dimensions de répartition temporelle répartissent l’horodatage des événements collectés et répartissent ces événements en dimensions plus significatives telles que l’heure du jour ou le jour de la semaine.
title: Dimensions de répartition du temps
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
TQID: https://experienceleague.adobe.com/bQVBmv3KhaDZtmUXSOY3UsustpCZKAwJ8rH9Qv49Rfw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 266
ht-degree: 68%

---

# Dimensions de répartition du temps

La répartition temporelle utilise l’horodatage des accès collectés et les ventile en dimensions plus significatives telles que **Heure du jour** ou **Jour de la semaine**.


>[!BEGINSHADEBOX]

Consultez la section ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensions de répartition du temps](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/time-parting-dimensions-in-analysis-workspace){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


Les dimensions de répartition du temps sont basées sur le fuseau horaire de la suite de rapports ou de la suite de rapports virtuelle. Ces dimensions sont disponibles dans Analysis Workspace et peuvent aider à répondre aux questions suivantes :

* Sur une période relativement étendue, quelle est l’heure la plus prisée pour accéder à mon site ou mon application ?
* La conversion est-elle supérieure sur mon site ou mon application certains jours de la semaine ou à certaines heures de la journée ?
* Les ventes enregistrées sur mon site sont-elles plus élevées la semaine ou le week-end ?
* Une campagne marketing donnée génère-t-elle davantage de conversions le matin ou l’après-midi ?

>[!NOTE]
>
>Les dimensions de répartition du temps ne sont disponibles que dans Analysis Workspace. Pour utiliser les dimensions de répartition du temps dans d’autres solutions d’Analytics, vous pouvez installer le [module externe getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

Les dimensions de répartition du temps dans Analysis Workspace incluent :

| Dimension | Exemples de valeur |
| --- | --- |
| Heure de la journée | 0-23 |
| Matin/après-midi | AM, PM |
| Jour de la semaine | Lundi, mardi, mercredi, jeudi, vendredi, samedi, dimanche |
| Week-end/Jour de semaine | Week-end/Jour ouvrable |
| Jour du mois | 1-31 |
| Mois de l’année | Janvier-Décembre |
| Jour de l’année | 1-366 |
| Trimestre de l’année | T1, T2, T3, T4 |
