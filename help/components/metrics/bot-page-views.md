---
title: Pages vues de robots
description: Nombre de pages vues qui correspondaient à des règles de robots.
feature: Metrics
exl-id: 9b1efcb1-10ca-40fb-8f20-e6da105366d9
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 4%

---

# Pages vues de robots

La mesure &quot;Pages vues de robots&quot; indique le nombre d’accès à la page correspondant à [Règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

La création de rapports de robots étant séparée du reste des données de votre suite de rapports, cette mesure ne fonctionne qu’avec les dimensions suivantes :

* [Nom du robot](../dimensions/bot-name.md)
* [Page](../dimensions/page.md)
* Dimensions basées sur le temps (par exemple, [Jour](../dimensions/day.md), [Semaine](../dimensions/week.md)ou [Mois](../dimensions/month.md))

L’utilisation d’une autre dimension avec cette mesure ne renvoie pas de données.

## Méthode de calcul de cette mesure

Adobe vérifie chaque accès à la page pour voir s’il correspond aux règles de robots configurées par votre entreprise. Si un accès donné correspond à une règle de robot, l’accès à la page est exclu des rapports et cette mesure augmente d’une unité. Cette mesure n’inclut pas les accès de suivi de liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).
