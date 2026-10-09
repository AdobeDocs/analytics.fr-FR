---
title: Occurrences de produits robots
description: La mesure « Occurrences de produits robots » indique le nombre de sous-accès à des chaînes de produit qui correspondaient à des règles de robots et qui ont été exclus de la création de rapports Analytics.
feature: Metrics
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 7a99ecd99a9b1a639c8a2d48dc35d57fdfeb1a12
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 5%
---
# Occurrences de produits robots

La mesure « Occurrences de produits robots » [&#128279;](overview.md) indique le nombre de sous-accès correspondant aux [règles de robots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Comme les rapports sur les robots sont séparés du reste des données de votre suite de rapports, cette mesure ne fonctionne qu’avec les dimensions suivantes :

* [Nom du robot](../dimensions/bot-name.md)
* Dimensions temporelles (par exemple, [Jour](../dimensions/day.md), [Semaine](../dimensions/week.md) ou [Mois](../dimensions/month.md))

L’utilisation d’une autre dimension avec cette mesure ne renvoie pas de données.

## Méthode de calcul de cette mesure

Adobe vérifie chaque sous-accès avec la [chaîne de produit](/help/implement/vars/page-vars/products.md) pour voir s’il correspond aux règles de robots configurées par votre organisation. Si un sous-accès donné correspond à une règle de robots, le sous-accès est exclu du compte rendu des performances et cette mesure augmente de un.
