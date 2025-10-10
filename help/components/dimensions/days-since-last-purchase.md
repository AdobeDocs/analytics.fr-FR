---
title: Jours depuis le dernier achat
description: Le nombre de jours entre l’accès actif et le dernier achat.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 84%

---

# Jours depuis le dernier achat

La dimension « Jours depuis le dernier achat »[Days from last purchase](overview.md) mesure le temps écoulé entre l’accès actuel du visiteur et son dernier achat à ce moment-là. Cette dimension vous aide à comprendre le comportement des visiteurs après avoir effectué un achat sur votre site.

Les visiteurs qui n’ont jamais effectué d’achat ne sont pas inclus dans cette dimension. De plus, les accès déclenchés avant le premier achat d’un visiteur ne sont pas inclus non plus. Seuls les accès après le premier achat d’un visiteur sont inclus.

## Renseignement de cette dimension avec des données

Adobe renseigne automatiquement cette dimension en fonction de l’événement [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de votre mise en œuvre. Si vous implémentez l’événement `purchase` sur votre site, cette dimension fonctionne toujours.

## Éléments de dimension

Les éléments de dimension comprennent le nombre de jours entre le dernier achat d’un visiteur et l’accès actif. Chaque nombre de jours est un élément de dimension distinct. « Même jour » survient lorsque le dernier achat d’un visiteur et l’accès actif ont lieu le même jour.
