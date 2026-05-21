---
title: Jours depuis le dernier achat
description: Le nombre de jours entre l’accès actif et le dernier achat.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 84%

---

# Jours depuis le dernier achat

La dimension « Jours depuis le dernier achat »[Days from last purchase](overview.md) mesure le temps écoulé entre l’accès actuel du visiteur et son dernier achat à ce moment-là. Cette dimension vous aide à comprendre le comportement des visiteurs après avoir effectué un achat sur votre site.

Les visiteurs qui n’ont jamais effectué d’achat ne sont pas inclus dans cette dimension. De plus, les accès déclenchés avant le premier achat d’un visiteur ne sont pas inclus non plus. Seuls les accès après le premier achat d’un visiteur sont inclus.

## Renseignement de cette dimension avec des données

Adobe renseigne automatiquement cette dimension en fonction de l’événement [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de votre mise en œuvre. Si vous implémentez l’événement `purchase` sur votre site, cette dimension fonctionne toujours.

## Éléments de dimension

Les éléments de dimension comprennent le nombre de jours entre le dernier achat d’un visiteur et l’accès actif. Chaque nombre de jours est un élément de dimension distinct. « Même jour » survient lorsque le dernier achat d’un visiteur et l’accès actif ont lieu le même jour.
