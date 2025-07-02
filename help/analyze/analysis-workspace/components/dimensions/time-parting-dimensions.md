---
description: Découvrez comment les dimensions de répartition temporelle prennent l’horodatage des événements collectés et les divisent en dimensions plus significatives telles que l’heure du jour ou le jour de la semaine.
title: Dimensions de répartition du temps
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 84%

---

# Dimensions de répartition du temps

La répartition du temps utilise l’horodatage des accès collectés et les ventile en dimensions plus significatives telles que « Heure du jour » ou « Jour de la semaine ».


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Time=parting dimensions](https://video.tv.adobe.com/v/41456?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


Les dimensions de répartition du temps sont basées sur le fuseau horaire de la suite de rapports ou de la suite de rapports virtuelle. Ces dimensions sont disponibles dans Analysis Workspace et peuvent aider à répondre aux questions suivantes :

* Sur une période relativement étendue, quelle est l’heure la plus prisée pour accéder à mon site ou mon application ?
* La conversion est-elle supérieure sur mon site ou mon application certains jours de la semaine ou à certaines heures de la journée ?
* Les ventes enregistrées sur mon site sont-elles plus élevées la semaine ou le week-end ?
* Une campagne marketing donnée génère-t-elle davantage de conversions le matin ou l’après-midi ?

>[!NOTE]
>
>Les dimensions de répartition du temps ne sont disponibles que dans Analysis Workspace. Pour utiliser les dimensions de répartition du temps dans d’autres solutions d’Analytics, vous pouvez installer le [module externe getTimeParting](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/gettimeparting.html?lang=fr).

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
