---
title: Navigateur
description: Le nom et la version du navigateur utilisé.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 206df584deab5f6f9b8eeb09d9c8ad4983424eea
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 58%

---

# Navigateur

L’[!UICONTROL Navigateur]’ [dimension](overview.md) indique le nom et la version du navigateur qui envoie l’accès. Cette dimension est utile lorsque vous souhaitez mesurer les navigateurs les plus courants des visiteurs. Lors du test de nouvelles versions du site, vous pouvez exécuter ces tests sur les principaux navigateurs de cette dimension afin d’optimiser les tâches de contrôle de la qualité.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Adobe travaille en partenariat avec [DeviceAtlas](https://deviceatlas.com/) pour gérer les recherches entre l’agent utilisateur et le navigateur.

* Pour les implémentations AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de SDK Web, activez [!UICONTROL Recherche de périphérique] lors de la [ configuration d’une chaîne de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments de dimension comprennent les noms et les versions des navigateurs utilisés. Les différentes versions d’un même navigateur sont des éléments de dimension distincts.

Certains éléments de dimension contiennent `"(unknown version)"` à la place du numéro de version. Cet élément de dimension fait référence à une version récente du navigateur qui n’a pas encore été ajoutée à leurs tables de recherche. Comme les navigateurs sont fréquemment mis à jour, l’élément `"(unknown version)"` d’un navigateur donné est courant et temporaire. Adobe met généralement à jour les tables de recherche lors des versions de maintenance mensuelles.