---
title: Durée avant événement
description: Durée entre la mesure et le premier accès de la visite.
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
source-git-commit: 2c363dce63768101356a6f43ea1e45ae8dd7b139
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 94%

---

# Durée avant événement

La dimension « Durée avant événement » indique le temps écoulé entre le premier accès de la visite et la mesure souhaitée. Cette dimension permet de déterminer le temps nécessaire pour accéder à un événement de succès, tel qu’un envoi de formulaire ou un achat.

## Renseignement de cette dimension avec des données

Bien que cette dimension soit techniquement prête à l’emploi pour toutes les implémentations, elle fonctionne mieux avec les événements personnalisés et d’achat. Adobe recommande l’implémentation d’événements personnalisés sur votre site. Si vous implémentez des événements personnalisés, aucune implémentation supplémentaire n’est requise pour cette dimension.

## Éléments de dimension

Les éléments de dimension comprennent des intervalles temporels compris entre `"Less than 1 minute"` et `"More than 15 hours"`. Par exemple, si 23 minutes s’écoulent entre le premier accès d’un visiteur et un achat, l’élément de dimension serait `"10 to 30 minutes"`. Les compartiments ne peuvent pas être personnalisés pour cette mesure.
