---
title: Recettes
description: Montant monétaire des produits achetés dans toutes les commandes.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---


# Recettes

La mesure Recettes indique le montant monétaire des produits achetés au cours de toutes les commandes. Cette mesure est essentielle pour les sites de commerce électronique pour mesurer la conversion. Vous pouvez associer cette mesure à n’importe quelle dimension pour déterminer les valeurs de dimension qui ont contribué aux recettes. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension Code [de](../dimensions/tracking-code.md) suivi) ou les principaux termes de recherche interne (à l’aide d’une [eVar](../dimensions/evar.md)).

## Méthode de calcul de cette mesure

Pour chaque accès où `purchase` se trouve la [`events`](/help/implement/vars/page-vars/events/event-purchase.md) variable, additionnez le champ Prix dans la [`products`](/help/implement/vars/page-vars/products.md) variable.

Cette mesure repose sur la variable [currencyCode](/help/implement/vars/config-vars/currencycode.md) si la devise de la page est différente de la devise native de la suite de rapports.
