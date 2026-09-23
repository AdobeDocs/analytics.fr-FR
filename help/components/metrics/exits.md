---
title: Sorties
description: Une instance de la dernière valeur d’une visite.
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
TQID: https://experienceleague.adobe.com/KTpLeq4YjWgaFR-xcq1PBENAO5mb-wV-71BODlRGGlM
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
source-wordcount: '187'
ht-degree: 88%
---
# Sorties

>[!BEGINSHADEBOX]

*Cette page d’aide décrit le fonctionnement des sorties en tant que mesure. Pour plus d’informations sur le fonctionnement des sorties en tant que dimension, consultez [Dimensions de sortie](../dimensions/exit-dimensions.md).*

>[!ENDSHADEBOX]

La [mesure](overview.md) « Sorties » indique le nombre de fois où un élément de dimension donné est capturé comme dernière valeur d’une visite. Cette mesure s’avère utile lorsque vous souhaitez en savoir plus sur le dernier élément que les visiteurs voient avant de quitter votre site. L’affichage des dernières valeurs d’une dimension peut vous aider à comprendre et à optimiser l’expérience du visiteur avant de quitter le site.

## Méthode de calcul de cette mesure

Une fois la [visite](visits.md) terminée, enregistrez l’élément de dimension le plus récent comme sortie. Il n’existe qu’une seule sortie par dimension et par visite. Il ne s’agit pas nécessairement du dernier hit de la visite si la dimension a été définie dans les hits précédents. Il s’agit d’une mesure basée sur les visites. Elle s’applique rétroactivement à tous les hits de la visite.

>[!TIP]
>
>Si vous définissez cette mesure sur une dimension qui n’est pas toujours définie à chaque visite, vous pouvez masquer l’élément de dimension « Non spécifié » dans Analysis Workspace. Cliquez sur l’icône de filtre, puis décochez la case [!UICONTROL Inclure non spécifié (Aucun)].
