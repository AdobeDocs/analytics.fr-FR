---
title: Occurrences du robot
description: Nombre d’accès qui correspondaient à des règles de robots.
feature: Metrics
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# Occurrences du robot

&quot;Occurrences du robot&quot; [metric](overview.md) affiche le nombre d’accès correspondant à [Règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

La création de rapports de robots étant séparée du reste des données de votre suite de rapports, cette mesure ne fonctionne qu’avec les dimensions suivantes :

* [Nom du robot](../dimensions/bot-name.md)
* [Page](../dimensions/page.md)
* Dimensions basées sur le temps (par exemple, [Jour](../dimensions/day.md), [Semaine](../dimensions/week.md), ou [Mois](../dimensions/month.md))

L’utilisation d’une autre dimension avec cette mesure ne renvoie pas de données.

## Méthode de calcul de cette mesure

Adobe vérifie chaque accès pour voir s’il correspond aux règles de robots configurées par votre entreprise. Si un accès donné correspond à une règle de robots, l’accès est exclu des rapports et cette mesure augmente d’une unité. Cette mesure inclut les deux pages vues ([`t()`](/help/implement/vars/functions/t-method.md)) et les accès de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)), alors que [Pages vues de robots](bot-page-views.md) n’incluez pas les accès de suivi de liens.
