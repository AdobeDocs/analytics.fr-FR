---
title: Jours depuis le dernier achat
description: Nombre de jours entre l’accès en cours et le dernier achat effectué.
translation-type: tm+mt
source-git-commit: c9e696201d0e9ec97dcdd6ff797ca72244dcf366
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Jours depuis le dernier achat

La dimension &quot;Jours depuis le dernier achat&quot; mesure la durée écoulée entre l’accès actuel du visiteur et son achat le plus récent à ce moment. Cette dimension vous aide à comprendre le comportement des visiteurs après avoir acheté sur votre site quelque chose.

Les Visiteurs qui n’ont jamais acheté quelque chose ne sont pas inclus dans cette dimension. De plus, les accès déclenchés avant l’achat d’un premier visiteur ne sont pas non plus inclus. Seuls les accès après l’achat du premier visiteur sont inclus.

## Renseigner cette dimension avec des données

Adobe remplit automatiquement cette dimension en fonction du [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) événement de votre mise en oeuvre. Si vous implémentez le `purchase` événement sur votre site, cette dimension fonctionne toujours.

## Valeurs de dimension

Les valeurs de dimension comprennent le nombre de jours entre un visiteur qui a effectué le plus d’achat récemment et l’accès actuel. Chaque nombre de jours est une valeur de dimension distincte, &quot;Même jour&quot; se produisant lorsqu’un visiteur a effectué le plus d’achats récents et que l’accès en cours s’est produit le même jour.
