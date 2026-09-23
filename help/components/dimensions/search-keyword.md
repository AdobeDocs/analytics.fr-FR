---
title: Mot-clé de recherche
description: Le mot-clé de recherche utilisé par le visiteur pour accéder à votre site.
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
TQID: https://experienceleague.adobe.com/4naavrC42ddsxGFJfkOJ0wzHLTa7tdMeI9nKDgVWrBY
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 70%
---
# Mot-clé de recherche

La dimension « Mot-clé de recherche » [dimension](overview.md) indique les mots-clés de recherche que les visiteurs et visiteuses utilisent pour accéder à votre site.

>[!IMPORTANT]
>
>La plupart des moteurs de recherche ne transmettent plus le mot-clé de recherche en raison de l’augmentation des pratiques de confidentialité. Les hits dans lesquels Adobe reconnaît un moteur de recherche, mais ne trouve pas de mot-clé sont regroupés sous l’élément de dimension `"Keyword unavailable"`.

Un référent doit répondre aux deux critères suivants pour être qualifié de mot-clé de recherche :

* Le domaine référent est reconnu par Adobe comme un [moteur de recherche](search-engine.md) valide.
* Il existe un paramètre de chaîne de requête de mot-clé dans l’URL de référence. Si la chaîne de requête de mot-clé existe, mais ne contient pas de valeur, elle est classée sous l’élément de dimension `"Keyword unavailable"`.

Si vous souhaitez distinguer le référencement payant du référencement naturel, la [détection de référencement payant](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) est requise. Plusieurs dimensions sont disponibles pour les mots-clés de recherche :

* **Mot-clé de recherche** : le mot-clé de recherche utilisé pour accéder à votre site, qu’il soit payant ou naturel.
* **Mot-clé de recherche - payant** : le mot-clé de recherche utilisé pour accéder à votre site, qui correspond à la détection de référencement payant.
* **Mot-clé de recherche - naturel** : le mot-clé de recherche utilisé pour accéder à votre site, qui ne correspond pas à la détection de référencement payant.

## Renseignement de cette dimension avec des données

Adobe dérive cette dimension du moteur de recherche [référent](referrer.md) de chaque accès, en extrayant le mot-clé de la chaîne de requête du référent. Aucune variable à définir. Comme chaque valeur dépend du référent, assurez-vous que la dimension référent et les [filtres d’URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) sont correctement configurés.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (dérivé du référent du moteur de recherche) |
| **Champ Web SDK/XDM** | Aucun (dérivé du référent du moteur de recherche) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension comprennent les mots-clés de recherche utilisés pour accéder à votre site. L’élément de dimension `"Unspecified"` correspond à l’ensemble du trafic hors recherche.
