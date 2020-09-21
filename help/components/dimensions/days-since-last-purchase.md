---
title: Jours depuis le dernier achat
description: Le nombre de jours entre l’accès actif et le dernier achat.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '173'
ht-degree: 100%

---


# Jours depuis le dernier achat

La dimension « Jours depuis le dernier achat » mesure le temps écoulé entre l’accès actif du visiteur et son dernier achat. Cette dimension vous aide à comprendre le comportement des visiteurs après avoir effectué un achat sur votre site.

Les visiteurs qui n’ont jamais effectué d’achat ne sont pas inclus dans cette dimension. De plus, les accès déclenchés avant le premier achat d’un visiteur ne sont pas inclus non plus. Seuls les accès après le premier achat d’un visiteur sont inclus.

## Renseignement de cette dimension avec des données

Adobe renseigne automatiquement cette dimension en fonction de l’événement [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de votre mise en œuvre. Si vous implémentez l’événement `purchase` sur votre site, cette dimension fonctionne toujours.

## Éléments de dimension

Les éléments de dimension comprennent le nombre de jours entre le dernier achat d’un visiteur et l’accès actif. Chaque nombre de jours est un élément de dimension distinct. « Même jour » survient lorsque le dernier achat d’un visiteur et l’accès actif ont lieu le même jour.
