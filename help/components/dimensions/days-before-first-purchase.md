---
title: Jours avant le premier achat
description: Nombre de jours entre la première visite d’un visiteur et son premier achat.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 100%

---


# Jours avant le premier achat

La dimension « Jours avant le premier achat » indique le nombre de jours qui s’écoulent entre la première visite d’un visiteur sur votre site et le moment où il effectue un achat. Par exemple, si un visiteur effectue un achat un jour après sa première visite, l’ensemble des visites ou événements ultérieurs appartiennent à l’élément de dimension « 1 jour ».

Une fois qu’un visiteur a effectué son premier achat, il appartient au même élément de dimension pour le reste de la durée de vie du cookie du visiteur.

## Renseignement de cette dimension avec des données

Adobe renseigne automatiquement cette dimension en fonction de l’événement [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de votre mise en œuvre. Si vous implémentez l’événement `purchase` sur votre site, cette dimension fonctionne toujours.

## Éléments de dimension

Les éléments de dimension comprennent le nombre de jours entre la première visite d’un visiteur sur votre site et son premier achat. Chaque nombre de jours est un élément de dimension distinct. « Même jour » survient lorsque la première visite d’un visiteur et son premier achat ont eu lieu le même jour.
