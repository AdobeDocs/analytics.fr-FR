---
title: Types de systèmes d’exploitation
description: Le système d’exploitation, quelle que soit la version.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
TQID: https://experienceleague.adobe.com/onZ7Wt7A44gd42hqmjqYHL7OF6VtBke1NDgu1tsnMIg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
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
source-wordcount: '165'
ht-degree: 40%
---
# Types de systèmes d’exploitation

La dimension « Types de systèmes d’exploitation » [dimension](overview.md) indique le système d’exploitation global utilisé par le visiteur, quelles que soient les versions spécifiques. Cette dimension est utile pour identifier le système d’exploitation et la version spécifique les plus courants, mais aussi la plateforme de système d’exploitation généralement utilisée par les visiteurs.

## Renseignement de cette dimension avec des données

Adobe dérive cette dimension de l’en-tête HTTP `User-Agent`, en la comparant à une table de recherche interne qu’Adobe conserve en partenariat avec [DeviceAtlas](https://deviceatlas.com/). Aucune variable à définir.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucune (dérivée de l’agent utilisateur) |
| **Champ Web SDK/XDM** | Aucune (dérivée de l’agent utilisateur) |
| **Paramètre de requête** | S.O. |
| **Balise XML** | S.O. |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

* Pour les implémentations d’AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de Web SDK, activez [!UICONTROL Recherche d’appareil] lors de la [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments Dimension incluent le type de système d’exploitation utilisé. Par exemple, `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` ou `"Apple iOS"`.
