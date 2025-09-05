---
title: Vues de page robot
description: Nombre de pages vues correspondant aux règles de robots.
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 11%

---

# Vues de page robot

La [mesure](overview.md) « Pages vues par les robots » indique le nombre d’accès aux pages qui correspondaient [Règles de robots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Comme les rapports sur les robots sont séparés du reste des données de votre suite de rapports, cette mesure ne fonctionne qu’avec les dimensions suivantes :

* [Nom du robot](../dimensions/bot-name.md)
* [Page](../dimensions/page.md)
* Dimensions temporelles (par exemple, [Jour](../dimensions/day.md), [Semaine](../dimensions/week.md) ou [Mois](../dimensions/month.md))

L’utilisation d’une autre dimension avec cette mesure ne renvoie pas de données.

## Méthode de calcul de cette mesure

Adobe vérifie chaque accès à la page pour déterminer s’il correspond aux règles de robots configurées par votre entreprise. Si un accès donné correspond à une règle de robots, l’accès à la page est exclu des rapports et cette mesure augmente de un. Cette mesure n’inclut pas les accès de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)).
