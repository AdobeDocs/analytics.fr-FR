---
title: Vues de page robot
description: Nombre de pages vues correspondant aux règles de robots.
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
TQID: https://experienceleague.adobe.com/Y0r2fzF87dep4NsrbJGCC9OnqBHrZozCh2DovNc90KQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 125
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
