---
title: Navigateur
description: Le nom et la version du navigateur utilisé.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
TQID: https://experienceleague.adobe.com/J6rDfVwmRZpRLrultdurQkRih2HcPygjcjwO0bkms5E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 202
ht-degree: 59%

---

# Navigateur

La [dimension](overview.md) « [!UICONTROL Navigateur] » indique le nom et la version du navigateur qui envoie l’accès. Cette dimension est utile lorsque vous souhaitez mesurer les navigateurs les plus courants utilisés par les visiteurs et visiteuses. Lors du test de nouvelles versions du site, vous pouvez exécuter ces tests sur les principaux navigateurs de cette dimension afin d’optimiser les tâches de contrôle de la qualité.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Adobe s’associe à [DeviceAtlas](https://deviceatlas.com/) pour gérer les recherches entre l’agent utilisateur et le navigateur.

* Pour les implémentations d’AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de Web SDK, activez [!UICONTROL Recherche d’appareil] lors de la [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments de dimension comprennent les noms et les versions des navigateurs utilisés. Les différentes versions d’un même navigateur sont des éléments de dimension distincts.

Certains éléments de dimension contiennent `"(unknown version)"` à la place du numéro de version. Cet élément de dimension fait référence à une version récente du navigateur qu’Adobe n’a pas encore ajoutée à ses tables de recherche. Comme les navigateurs sont fréquemment mis à jour, l’élément `"(unknown version)"` d’un navigateur donné est courant et temporaire. Adobe met généralement à jour les tables de recherche lors des versions de maintenance mensuelles.