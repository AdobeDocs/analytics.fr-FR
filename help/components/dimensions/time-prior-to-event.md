---
title: Heure avant le événement
description: Durée entre la mesure et le premier accès de la visite.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# Heure avant le événement

La dimension &quot;Durée avant le événement&quot; indique la durée écoulée entre le premier accès de la visite et la mesure souhaitée. Cette dimension est utile pour déterminer le temps nécessaire pour atteindre un événement de réussite, tel qu’un envoi de formulaire ou un achat.

## Renseigner cette dimension avec des données

Bien que cette dimension soit techniquement prête à l’emploi pour toutes les implémentations, elle fonctionne mieux avec les événements personnalisés et d’achat. Adobe recommande la mise en oeuvre de événements personnalisés sur votre site. Si vous implémentez des événements personnalisés, aucune implémentation supplémentaire n’est requise pour cette dimension.

## Valeurs de dimension

Les valeurs de dimension comprennent des intervalles temporels allant de `"Less than 1 minute"` à `"More than 15 hours"`. Par exemple, si un visiteur a mis 23 minutes entre son premier accès et un achat, il appartenait sous la valeur de la `"10 to 30 minutes"` dimension.
