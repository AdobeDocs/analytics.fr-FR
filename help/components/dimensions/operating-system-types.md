---
title: Types de systèmes d’exploitation
description: Le système d’exploitation, quelle que soit la version.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 53%

---

# Types de systèmes d’exploitation

La dimension « Types de systèmes d’exploitation » [dimension](overview.md) indique le système d’exploitation global utilisé par le visiteur, quelles que soient les versions spécifiques. Cette dimension est utile pour identifier le système d’exploitation et la version spécifique les plus courants, mais aussi la plateforme de système d’exploitation généralement utilisée par les visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Adobe s’associe à [DeviceAtlas](https://deviceatlas.com/) pour gérer les recherches entre l’agent utilisateur et le type de système d’exploitation.

* Pour les implémentations d’AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de Web SDK, activez [!UICONTROL Recherche d’appareil] lors de la [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments Dimension incluent le type de système d’exploitation utilisé. Par exemple, `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` ou `"Apple iOS"`.
