---
title: Commandes
description: Nombre d’achats effectués.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 80%

---


# Commandes

La mesure « Commandes » indique le nombre total d’événements d’achat effectués sur votre site. Cette mesure est essentielle pour les sites d’e-commerce, car elle permet de mesurer la conversion. Vous pouvez associer cette mesure à n’importe quelle dimension pour identifier les éléments de dimension qui ont contribué à une commande. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension [Code de suivi](../dimensions/tracking-code.md)) ou les principaux termes de recherche interne (avec [eVar](../dimensions/evar.md)) ayant contribué aux achats.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès dans lesquels `purchase` se trouve dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
