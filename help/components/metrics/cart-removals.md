---
title: Retraits du panier
description: Nombre d’accès pendant lesquels un visiteur a retiré un produit du panier.
feature: Metrics
exl-id: 74b9677e-89c7-4409-8bd3-99707436def0
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 78%

---

# Retraits du panier

Les &quot;Retraits du panier&quot; [metric](overview.md) indique le nombre de fois où un visiteur a supprimé un élément de son panier. Cette mesure s’avère utile lorsque vous souhaitez comprendre la partie de l’entonnoir de conversion dans laquelle les clients ne s’intéressent plus à un produit.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès dans lesquels `scRemove` se trouve dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
