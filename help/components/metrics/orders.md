---
title: Commandes
description: Nombre d’achats effectués.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 2%

---


# Commandes

La mesure Commandes indique le nombre total de événements d’achat effectués sur votre site. Cette mesure est essentielle pour les sites de commerce électronique pour mesurer la conversion. Vous pouvez associer cette mesure à n’importe quelle dimension pour déterminer les valeurs de dimension qui ont contribué à une commande. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension Code [de](../dimensions/tracking-code.md) suivi) ou les principaux termes de recherche interne (à l’aide d’une [eVar](../dimensions/evar.md)) qui ont contribué aux achats.

## Méthode de calcul de cette mesure

Cette mesure compte le nombre d’accès où `purchase` se trouve la [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.
