---
title: Classement de toutes les pages de recherche
description: Déterminez la page de moteur de recherche sur laquelle un visiteur a cliqué pour accéder à votre site.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
TQID: https://experienceleague.adobe.com/U7WgtQDXInyD1gXeBntncC9Fao1Rdc9W4AHFgx07T4A
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 62%
---
# Classement de toutes les pages de recherche

La dimension [Classement de toutes les pages de recherche](overview.md) fournit insight la page de résultats de recherche sur laquelle un visiteur a cliqué pour accéder à votre site. Par exemple, si votre site apparaît sur la deuxième page de résultats d’un moteur de recherche, l’élément de dimension de cette variable est « Page de recherche 2 ».

## Renseignement de cette dimension avec des données

Adobe dérive cette dimension du moteur de recherche [référent](referrer.md) de chaque accès, déterminant la page de résultats de recherche sur laquelle le visiteur a cliqué. Aucune variable à définir. Pour que cette dimension fonctionne, vous devez simplement configurer correctement les [filtres URL internes](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) de votre suite de rapports.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (dérivé du référent du moteur de recherche) |
| **Champ Web SDK/XDM** | Aucun (dérivé du référent du moteur de recherche) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

## Éléments de dimension

Si un visiteur utilise un moteur de recherche pour accéder à votre site, la valeur de cette dimension est « Page de recherche » suivie du numéro de la page sur laquelle il a cliqué. Si un hit ne provient pas d’un moteur de recherche, la valeur de cette dimension est « Non spécifié ».
