---
title: Durée de la visite (dimensions)
description: La durée totale de la visite.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
TQID: 'https://experienceleague.adobe.com/jtBAAq-Pe0PyCQJPwvzwnK9eLv14CxTvrVQP4lvWy7k'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
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
source-wordcount: '349'
ht-degree: 76%
---
# Durée de la visite

>[!BEGINSHADEBOX]

*Cette page d’aide décrit le fonctionnement de « Durée de la visite » en tant que [dimensions](overview.md) respectives. Pour plus d’informations, consultez la mesure [Durée de la visite](../metrics/time-spent-per-visit.md).*

>[!ENDSHADEBOX]

Les dimensions « Temps passé par visite » enregistrent le temps passé par un visiteur ou une visiteuse pendant l’intégralité de la visite. Elle utilise les étapes suivantes pour mesurer le calcul :

1. Examinez l’heure et la date du premier hit de la visite.
2. Comparez ce hit aux valeurs de date et heure du dernier hit de la visite.
3. Le temps écoulé entre ces deux hits contribue à la durée de consultation.

Ces dimensions sont utiles pour déterminer la durée d’interaction des visiteurs avec votre site en général.

>[!TIP]
>
>Lors d’une visite, au moins deux hits sont nécessaires pour mesurer la durée. Les visites composées d’un seul hit n’apparaissent pas dans cette dimension.

Cette dimension est basée sur les visites, ce qui signifie que la valeur s’applique à chaque hit lors de la visite et ne change pas. Comparez cette dimension à la [durée de consultation de la page](time-spent-on-page.md), qui est une dimension basée sur les hits.

Cette dimension est liée aux mesures [Durée moyenne de la visite du site](../metrics/average-time-on-site.md) et [Durée de la visite](../metrics/time-spent-per-visit.md).

## Renseignement de cette dimension avec des données

Adobe calcule ces dimensions côté serveur à partir du temps écoulé entre le premier et le dernier accès de la visite. Il n’existe aucune variable à définir ; elles sont prêtes à l’emploi pour toutes les implémentations.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (calculé par Adobe) |
| **Champ Web SDK/XDM** | Aucun (calculé par Adobe) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | Visite |

## Éléments de dimension

La durée de la visite comporte plusieurs dimensions :

* **Durée de la visite - regroupée** : la durée est regroupée. Les éléments de dimension sont compris entre `"Less than 1 minute"` et `"More than 15 hours"`. En règle générale, les visites ne durent pas plus de 12 heures. Toutefois, les visites peuvent dépasser 12 heures si vous utilisez des hits horodatés ou des sources de données.
* **Durée de la visite - granulaire** : chaque nombre de secondes est un élément de dimension unique. Cette dimension n’est pas disponible dans Data Warehouse.

Consultez [Présentation de la durée de consultation](../metrics/time-spent.md) pour obtenir des informations plus générales sur la durée de consultation.
