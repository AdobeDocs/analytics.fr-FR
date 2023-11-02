---
title: Système d’exploitation
description: Système d’exploitation du visiteur.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 9c3e65392d6e5929ce1ecefbc460c1fd5576aed8
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 45%

---

# Système d’exploitation

Le &quot;Système d&#39;exploitation&quot; [dimension](overview.md) affiche le système d’exploitation et la version utilisés par le visiteur. Si votre propriété Web comporte des fonctionnalités spécifiques au système d’exploitation, cette dimension vous permet d’identifier les systèmes d’exploitation les plus courants.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Adobe de partenaires avec [DeviceAtlas](https://deviceatlas.com/) pour gérer les recherches entre l’agent utilisateur et le système d’exploitation.

* Pour les implémentations AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations du SDK Web, activez [!UICONTROL Recherche de périphérique] when [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments de dimension incluent les systèmes d’exploitation utilisés par les visiteurs. Par exemple, `"Windows 10"`, `"OS X 10.15.7"` et `"Android 9"`.

## Suivi de versions de système d’exploitation précises

À mesure que le secteur se dirige vers les conseils des clients, certaines versions des systèmes d’exploitation sont potentiellement dupliquées. Par exemple, &quot;Windows 10&quot; et &quot;Windows 11&quot; peuvent tous deux être regroupés sous &quot;Windows 10&quot; si vous ne collectez pas d’indices client à forte entropie. Voir [Conseils client](/help/technotes/client-hints.md) pour plus d’informations.
