---
title: Commandes
description: Nombre d’achats effectués.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 84%

---

# Commandes

Les &quot;Commandes&quot; [metric](overview.md) indique le nombre total d’événements d’achat effectués sur votre site. Cette mesure est essentielle pour les sites d’e-commerce, car elle permet de mesurer la conversion. Vous pouvez associer cette mesure à n’importe quelle dimension pour déterminer les éléments de dimension ayant contribué à une commande. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension [Code de suivi](../dimensions/tracking-code.md)) ou les principaux termes de recherche interne (avec [eVar](../dimensions/evar.md)) ayant contribué aux achats.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès dans lesquels `purchase` se trouve dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
