---
title: Entrées
description: Instance de la première valeur d’une visite.
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
TQID: https://experienceleague.adobe.com/H3LE0wm2uDL3-pILbvOXvccAJQdo5o9X3uHJ4xZe7UU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 89%
---
# Entrées

>[!BEGINSHADEBOX]

*Cette page d’aide décrit le fonctionnement des entrées en tant que mesure. Pour plus d’informations sur le fonctionnement des entrées en tant que dimension, consultez la dimension [Entrées](../dimensions/entry-dimensions.md).*

>[!ENDSHADEBOX]

La [mesure](overview.md) « Entrées » indique le nombre de fois où un élément de dimension donné est capturé comme première valeur d’une visite. Cette mesure s’avère utile lorsque vous souhaitez en savoir plus sur les premières impressions des visiteurs sur votre site. L’affichage des premières valeurs d’une dimension peut vous aider à comprendre et à optimiser l’expérience d’un nouveau visiteur.

## Méthode de calcul de cette mesure

Pour une dimension donnée, enregistrez comme entrée le premier élément de dimension rencontré au cours d’une visite. Il n’existe qu’une seule entrée par dimension et par visite. Il ne s’agit pas nécessairement du premier hit de la visite si la dimension n’est pas initialement définie. Il s’agit d’une mesure basée sur la visite. Une fois qu’elle est liée à un élément de dimension, elle persiste pour le reste de la visite.

>[!TIP]
>
>Si vous affichez cette mesure pour une dimension qui n’est pas systématiquement définie à chaque visite, vous pouvez masquer l’élément de dimension « Non spécifié » dans Analysis Workspace. Cliquez sur l’icône de filtre, puis décochez la case [!UICONTROL Inclure non spécifié (Aucun)].
