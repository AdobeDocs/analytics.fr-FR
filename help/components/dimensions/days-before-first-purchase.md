---
title: Jours avant le premier achat
description: Nombre de jours entre la première visite d’un visiteur et son premier achat.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
TQID: https://experienceleague.adobe.com/fA8CgahXKwJfiynK-I8yuD-byaIyFPkaii3FzkrrPoI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 63%
---
# Jours avant le premier achat

La dimension [&#x200B; Jours avant le premier achat »](overview.md) indique le nombre de jours qui s’écoulent entre la première fois qu’un visiteur accède à votre site et le moment où il effectue un achat. Par exemple, si un visiteur effectue un achat un jour après sa première visite, toute visite ou tout événement ultérieur appartient alors à l’élément de dimension « 1 jour ».

Une fois qu’un visiteur a effectué son premier achat, il appartient au même élément de dimension pour le reste de la durée de vie du cookie du visiteur.

## Renseignement de cette dimension avec des données

Adobe calcule cette dimension côté serveur à partir de l’historique des achats du visiteur. Aucune variable à définir ; cela dépend de l’événement [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) implémenté sur votre site.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (calculé par Adobe) |
| **Champ Web SDK/XDM** | Aucun (calculé par Adobe) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | Visiteur |

## Éléments de dimension

Les éléments de dimension comprennent le nombre de jours entre la première visite d’un visiteur sur votre site et son premier achat. Chaque nombre de jours est un élément de dimension distinct. « Même jour » survient lorsque la première visite d’un visiteur et son premier achat ont eu lieu le même jour.
