---
title: Recettes
description: La valeur monétaire des produits achetés dans l’ensemble des commandes.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '113'
ht-degree: 100%

---

# Recettes

La mesure « Chiffre d’affaires » indique la valeur monétaire des produits achetés dans l’ensemble des commandes. Cette mesure est essentielle pour les sites d’e-commerce, car elle permet de mesurer la conversion. Vous pouvez associer cette mesure à n’importe quelle dimension pour déterminer les éléments de dimension ayant contribué au chiffre d’affaires. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension [Code de suivi](../dimensions/tracking-code.md)) ou les principaux termes de recherche interne (avec [eVar](../dimensions/evar.md)).

## Méthode de calcul de cette mesure

Chaque accès dont la variable [`events`](/help/implement/vars/page-vars/events/event-purchase.md) contient `purchase`, additionnez les champs « Prix » dans la variable [`products`](/help/implement/vars/page-vars/products.md).

Cette mesure repose sur la variable [currencyCode](/help/implement/vars/config-vars/currencycode.md) si la devise de la page est différente de la devise d’origine de la suite de rapports.
