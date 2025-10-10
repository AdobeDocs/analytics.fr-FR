---
title: Système d’exploitation
description: Système d’exploitation du visiteur.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 9c3e65392d6e5929ce1ecefbc460c1fd5576aed8
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 42%

---

# Système d’exploitation

La dimension « Système d’exploitation » [dimension](overview.md) indique le système d’exploitation et la version utilisés par le visiteur. Si votre propriété Web comporte des fonctionnalités spécifiques au système d’exploitation, cette dimension vous permet d’identifier les systèmes d’exploitation les plus courants.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Adobe s’associe à [DeviceAtlas](https://deviceatlas.com/) pour gérer les recherches entre l’agent utilisateur et le système d’exploitation.

* Pour les implémentations d’AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de Web SDK, activez [!UICONTROL Recherche d’appareil] lors de la [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments de dimension incluent les systèmes d’exploitation utilisés par les visiteurs. Par exemple, `"Windows 10"`, `"OS X 10.15.7"` et `"Android 9"`.

## Suivi de versions de systèmes d’exploitation précises

Lorsque le secteur se dirige vers les indications du client, certaines versions de systèmes d’exploitation peuvent être confondues. Par exemple, « Windows 10 » et « Windows 11 » peuvent tous deux être regroupés sous « Windows 10 » si vous ne collectez pas d’indications du client à entropie élevée. Voir [Indications du client](/help/technotes/client-hints.md) dans le guide des notes techniques pour plus d’informations.
