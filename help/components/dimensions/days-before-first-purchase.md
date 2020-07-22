---
title: Jours avant le premier achat
description: Nombre de jours entre la première visite d’un visiteur et son premier achat.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Jours avant le premier achat

La dimension &quot;Jours avant le premier achat&quot; indique le nombre de jours qui s’écoulent entre la première fois qu’un visiteur arrive sur votre site et le moment où il effectue un achat. Par exemple, si un visiteur effectue un achat un jour après sa première visite, toute visite ou événement ultérieure appartient à l’élément de dimension &quot;1 jour&quot;.

Une fois qu’un visiteur a effectué son premier achat, il appartient au même élément de dimension pour le reste de la durée de vie du cookie visiteur.

## Renseigner cette dimension avec des données

Adobe remplit automatiquement cette dimension en fonction du [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) événement de votre mise en oeuvre. Si vous implémentez le `purchase` événement sur votre site, cette dimension fonctionne toujours.

## Éléments de dimension

Les éléments de dimension comprennent le nombre de jours entre la première visite d’un visiteur sur votre site et son premier achat. Chaque nombre de jours est un élément de dimension distinct, &quot;Même jour&quot; survenant lorsqu’un visiteur visite pour la première fois et que son premier achat a eu lieu le même jour.
