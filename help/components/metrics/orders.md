---
title: Commandes
description: Nombre d’achats effectués.
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '91'
ht-degree: 100%

---

# Commandes

La mesure « Commandes » indique le nombre total d’événements d’achat effectués sur votre site. Cette mesure est essentielle pour les sites d’e-commerce, car elle permet de mesurer la conversion. Vous pouvez associer cette mesure à n’importe quelle dimension pour déterminer les éléments de dimension ayant contribué à une commande. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension [Code de suivi](../dimensions/tracking-code.md)) ou les principaux termes de recherche interne (avec [eVar](../dimensions/evar.md)) ayant contribué aux achats.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès dans lesquels `purchase` se trouve dans la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
