---
title: Langue
description: Paramètre de langue préférée dans le navigateur.
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
TQID: https://experienceleague.adobe.com/KC8nBiwUbQaE8Wi5OVKdjwP-sTijGYYMBK74M-TnOFs
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 65%
---
# Langue

La dimension « Langue [Language](overview.md) indique les principales langues dans lesquelles les visiteurs préfèrent voir le contenu. Cette dimension est utile lorsque vous souhaitez comprendre les langues préférées les plus fréquentes chez les visiteurs dans le cadre de vos efforts de localisation.

>[!NOTE]
>
>Cette dimension ne collecte pas la langue de votre site. Si vous souhaitez collecter la langue de votre site dans une dimension, Adobe recommande d’utiliser une variable personnalisée, telle qu’une [eVar](evar.md).

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `Accept-Language` dans les demandes d’image. Elle est prête à l’emploi dans toute implémentation d’AppMeasurement ou de Web SDK (balises). Il n’y a aucune variable à définir.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (en-tête HTTP) |
| **Champ Web SDK/XDM** | Aucun (en-tête HTTP) |
| **Paramètre de requête** | Aucune (utilise l’en-tête `Accept-Language`) |
| **Balise XML** | [`<language>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension incluent des noms conviviaux pour les langues préférées des visiteurs. Par exemple, `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"` ou `"Spanish (Spain)"`. Si une demande d’image ne contient pas de langue valide dans l’en-tête HTTP, l’élément de dimension est `"None"`.
