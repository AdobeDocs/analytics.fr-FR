---
title: Référencement payant
description: Permet de distinguer les mesures de référencement payant des mesures de référencement naturel.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
TQID: https://experienceleague.adobe.com/s9jhjGeXaOCo-Wz-Jyof951NZdRWfz-9tjrVrjHvTS0
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 59%
---
# Référencement payant

La dimension [Référencement payant](overview.md) vous permet de consulter n’importe quelle mesure et de la comparer entre le référencement payant et le référencement naturel. Tous les autres hits en dehors des moteurs de recherche sont omis. Cette dimension permet de comprendre comment vos efforts de référencement payant se comparent au référencement naturel.

## Renseignement de cette dimension avec des données

Adobe dérive cette dimension par la détection de référencement payant, qui classe le trafic des moteurs de recherche comme étant payant ou naturel. Aucune variable à définir. La seule exigence est que la [détection de référencement payant](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) soit correctement configurée dans les paramètres de la suite de rapports. Si la détection de référencement payant est correctement configurée et qu’une suite de rapports comporte des données, cette dimension fonctionne toujours.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (dérivé par détection de référencement payant) |
| **Champ Web SDK/XDM** | Aucun (dérivé par détection de référencement payant) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension comprennent deux valeurs statiques : `"Natural"` et `"Paid"`. Si une visite correspond à la fois aux critères d’un moteur de recherche et à la détection de référencement payant, elle appartient à l’élément de dimension `"Paid"`. Si une visite correspond aux critères d’un moteur de recherche et ne correspond *pas* à la détection de référencement payant, elle appartient à l’élément de dimension `"Natural"`.
