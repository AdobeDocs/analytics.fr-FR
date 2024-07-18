---
title: Occurrences du robot
description: Nombre d’accès qui correspondaient à des règles de robots.
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# Occurrences du robot

La [mesure](overview.md) des &quot;occurrences de robots&quot; indique le nombre d’accès qui correspondaient à [règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

La création de rapports de robots étant séparée du reste des données de votre suite de rapports, cette mesure ne fonctionne qu’avec les dimensions suivantes :

* [Nom du robot](../dimensions/bot-name.md)
* [Page](../dimensions/page.md)
* Dimensions basées sur le temps (par exemple, [Jour](../dimensions/day.md), [Semaine](../dimensions/week.md) ou [Mois](../dimensions/month.md))

L’utilisation d’une autre dimension avec cette mesure ne renvoie pas de données.

## Méthode de calcul de cette mesure

Adobe vérifie chaque accès pour voir s’il correspond aux règles de robots configurées par votre entreprise. Si un accès donné correspond à une règle de robots, l’accès est exclu des rapports et cette mesure augmente d’une unité. Cette mesure inclut à la fois les pages vues ([`t()`](/help/implement/vars/functions/t-method.md)) et les accès de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)), tandis que les [ pages vues de robots ](bot-page-views.md) n’incluent pas les accès de suivi de liens.
