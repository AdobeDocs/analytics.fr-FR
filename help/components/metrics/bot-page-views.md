---
title: Vues de page robot
description: Nombre de pages vues qui correspondaient à des règles de robots.
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 11%

---

# Vues de page robot

La [mesure](overview.md) de &quot;pages vues de robots&quot; indique le nombre d’accès à la page correspondant aux [règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

La création de rapports de robots étant séparée du reste des données de votre suite de rapports, cette mesure ne fonctionne qu’avec les dimensions suivantes :

* [Nom du robot](../dimensions/bot-name.md)
* [Page](../dimensions/page.md)
* Dimensions basées sur le temps (par exemple, [Jour](../dimensions/day.md), [Semaine](../dimensions/week.md) ou [Mois](../dimensions/month.md))

L’utilisation d’une autre dimension avec cette mesure ne renvoie pas de données.

## Méthode de calcul de cette mesure

Adobe vérifie chaque accès à la page pour voir s’il correspond aux règles de robots configurées par votre entreprise. Si un accès donné correspond à une règle de robot, l’accès à la page est exclu des rapports et cette mesure augmente d’une unité. Cette mesure n’inclut pas les accès de suivi de liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).
