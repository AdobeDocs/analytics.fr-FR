---
title: Jours avant le premier achat
description: Nombre de jours entre la première visite d’un visiteur et son premier achat.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 83%

---

# Jours avant le premier achat

La dimension [ Jours avant le premier achat »](overview.md) indique le nombre de jours qui s’écoulent entre la première fois qu’un visiteur accède à votre site et le moment où il effectue un achat. Par exemple, si un visiteur effectue un achat un jour après sa première visite, l’ensemble des visites ou événements ultérieurs appartiennent à l’élément de dimension « 1 jour ».

Une fois qu’un visiteur a effectué son premier achat, il appartient au même élément de dimension pour le reste de la durée de vie du cookie du visiteur.

## Renseignement de cette dimension avec des données

Adobe renseigne automatiquement cette dimension en fonction de l’événement [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de votre mise en œuvre. Si vous implémentez l’événement `purchase` sur votre site, cette dimension fonctionne toujours.

## Éléments de dimension

Les éléments de dimension comprennent le nombre de jours entre la première visite d’un visiteur sur votre site et son premier achat. Chaque nombre de jours est un élément de dimension distinct. « Même jour » survient lorsque la première visite d’un visiteur et son premier achat ont eu lieu le même jour.
