---
title: Occurrences du robot
description: Nombre d’accès correspondant aux règles de robots.
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# Occurrences du robot

La [mesure](overview.md) « Occurrences de robots » indique le nombre d’accès correspondant à [Règles de robots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Comme les rapports sur les robots sont séparés du reste des données de votre suite de rapports, cette mesure ne fonctionne qu’avec les dimensions suivantes :

* [Nom du robot](../dimensions/bot-name.md)
* [Page](../dimensions/page.md)
* Dimensions temporelles (par exemple, [Jour](../dimensions/day.md), [Semaine](../dimensions/week.md) ou [Mois](../dimensions/month.md))

L’utilisation d’une autre dimension avec cette mesure ne renvoie pas de données.

## Méthode de calcul de cette mesure

Adobe vérifie chaque accès pour voir s’il correspond aux règles de robots configurées par votre organisation. Si un accès donné correspond à une règle de robots, l’accès est exclu du compte rendu des performances et cette mesure augmente de un. Cette mesure inclut les pages vues ([`t()`](/help/implement/vars/functions/t-method.md)) et les accès de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)), tandis que [Pages vues par les robots](bot-page-views.md) n’inclut pas les accès de suivi des liens.
