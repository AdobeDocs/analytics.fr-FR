---
title: Nouveaux engagements
description: Le nombre de fois qu’un canal Première touche est défini.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 83%

---

# Nouveaux engagements

Les &quot;nouveaux engagements&quot; [metric](overview.md) indique le nombre de fois où un visiteur correspond à un canal marketing pour la première fois au cours de la période d’engagement de ce visiteur. Cette mesure est utile lorsque vous souhaitez comparer une dimension avec un visiteur correspondant pour la première fois à une règle de traitement des canaux marketing.

## Méthode de calcul de cette mesure

Pendant le traitement des données, chaque accès passe par les [règles de traitement des canaux marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md). Si un accès correspond à une règle de traitement des canaux marketing et que le visiteur ne dispose pas déjà d’un canal Première touche, l’accès est un nouvel engagement. Si un accès ne correspond à aucune règle de traitement des canaux marketing ou si le visiteur dispose déjà d’un canal Première touche, l’accès n’est pas un nouvel engagement.

Les visiteurs peuvent disposer de plusieurs nouveaux engagements s’ils laissent leur période d’engagement des visiteurs expirer.
