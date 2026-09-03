---
title: Nouveaux engagements
description: Le nombre de fois qu’un canal Première touche est défini.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
TQID: https://experienceleague.adobe.com/UsPu31wUqpoDYQy5aT9wnzSUgJ6i9mHVZ8pAtFQgzGo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 83%

---

# Nouveaux engagements

La mesure « Nouveaux engagements » [nombre de fois](overview.md) indique le nombre de fois qu’un visiteur correspond à un canal marketing pour la première fois au cours de sa période d’engagement. Cette mesure est utile lorsque vous souhaitez comparer une dimension avec un visiteur correspondant pour la première fois à une règle de traitement des canaux marketing.

## Méthode de calcul de cette mesure

Pendant le traitement des données, chaque accès passe par les [règles de traitement des canaux marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). Si un accès correspond à une règle de traitement des canaux marketing et que le visiteur ne dispose pas déjà d’un canal Première touche, l’accès est un nouvel engagement. Si un accès ne correspond à aucune règle de traitement des canaux marketing ou si le visiteur dispose déjà d’un canal Première touche, l’accès n’est pas un nouvel engagement.

Les visiteurs peuvent disposer de plusieurs nouveaux engagements s’ils laissent leur période d’engagement des visiteurs expirer.
