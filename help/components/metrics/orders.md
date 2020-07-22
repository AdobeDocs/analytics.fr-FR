---
title: Commandes
description: Nombre d’achats effectués.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 2%

---


# Commandes

La mesure Commandes indique le nombre total de événements d’achat effectués sur votre site. Cette mesure est essentielle pour les sites de commerce électronique pour mesurer la conversion. Vous pouvez associer cette mesure à n’importe quelle dimension pour identifier les éléments de dimension qui ont contribué à une commande. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension Code [de](../dimensions/tracking-code.md) suivi) ou les principaux termes de recherche interne (à l’aide d’une [eVar](../dimensions/evar.md)) qui ont contribué aux achats.

## Méthode de calcul de cette mesure

Cette mesure compte le nombre d’accès où `purchase` se trouve la [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.
