---
title: Système d’exploitation
description: Système d’exploitation du visiteur.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
TQID: https://experienceleague.adobe.com/WM6GQ-AhLmtudRWXF6lOez6DaVxMBU3rSaEb2UdsXdc
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
source-wordcount: '207'
ht-degree: 34%
---
# Système d’exploitation

La dimension « Système d’exploitation » [dimension](overview.md) indique le système d’exploitation et la version utilisés par le visiteur. Si votre propriété web comporte des fonctionnalités spécifiques au système d’exploitation, cette dimension vous permet d’identifier les systèmes d’exploitation les plus courants.

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

Les éléments de dimension incluent les systèmes d’exploitation utilisés par les visiteurs. Par exemple, `"Windows 10"`, `"OS X 10.15.7"` et `"Android 9"`.

## Suivi de versions de systèmes d’exploitation précises

Lorsque le secteur se dirige vers les indications du client, certaines versions de systèmes d’exploitation peuvent être confondues. Par exemple, « Windows 10 » et « Windows 11 » peuvent tous deux être regroupés sous « Windows 10 » si vous ne collectez pas d’indications du client à entropie élevée. Voir [Indications du client](/help/technotes/client-hints.md) dans le guide des notes techniques pour plus d’informations.
