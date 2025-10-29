---
title: Nouveaux engagements
description: Le nombre de fois qu’un canal Première touche est défini.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 83%

---

# Nouveaux engagements

La mesure « Nouveaux engagements » [nombre de fois](overview.md) indique le nombre de fois qu’un visiteur correspond à un canal marketing pour la première fois au cours de sa période d’engagement. Cette mesure est utile lorsque vous souhaitez comparer une dimension avec un visiteur correspondant pour la première fois à une règle de traitement des canaux marketing.

## Méthode de calcul de cette mesure

Pendant le traitement des données, chaque accès passe par les [règles de traitement des canaux marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). Si un accès correspond à une règle de traitement des canaux marketing et que le visiteur ne dispose pas déjà d’un canal Première touche, l’accès est un nouvel engagement. Si un accès ne correspond à aucune règle de traitement des canaux marketing ou si le visiteur dispose déjà d’un canal Première touche, l’accès n’est pas un nouvel engagement.

Les visiteurs peuvent disposer de plusieurs nouveaux engagements s’ils laissent leur période d’engagement des visiteurs expirer.
