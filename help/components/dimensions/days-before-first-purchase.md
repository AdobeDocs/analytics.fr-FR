---
title: Jours avant le premier achat
description: Nombre de jours entre la première visite d’un visiteur et son premier achat.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Jours avant le premier achat

La dimension &quot;Jours avant le premier achat&quot; indique le nombre de jours qui s’écoulent entre la première fois qu’un visiteur arrive sur votre site et le moment où il effectue un achat. Par exemple, si un visiteur effectue un achat un jour après sa première visite, toute visite ou événement ultérieure appartient à la valeur de dimension &quot;1 jour&quot;.

Une fois qu’un visiteur a effectué son premier achat, il appartient à la même valeur de dimension pour le reste de la durée de vie du cookie visiteur.

## Renseigner cette dimension avec des données

Adobe remplit automatiquement cette dimension en fonction du [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) événement de votre mise en oeuvre. Si vous implémentez le `purchase` événement sur votre site, cette dimension fonctionne toujours.

## Valeurs de dimension

Les valeurs de dimension comprennent le nombre de jours entre la première visite d’un visiteur sur votre site et son premier achat. Chaque nombre de jours est une valeur de dimension distincte, &quot;Même jour&quot; survenant lorsqu’un visiteur visite pour la première fois et que son premier achat a eu lieu le même jour.
