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

La [dimension](overview.md) &quot;Types de système d’exploitation&quot; indique le système d’exploitation global utilisé par le visiteur, quelles que soient les versions spécifiques. Cette dimension est utile pour identifier le système d’exploitation et la version spécifique les plus courants, mais aussi la plateforme de système d’exploitation généralement utilisée par les visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Adobe travaille en partenariat avec [DeviceAtlas](https://deviceatlas.com/) pour gérer les recherches entre l’agent utilisateur et le type de système d’exploitation.

* Pour les implémentations AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de SDK Web, activez [!UICONTROL Recherche de périphérique] lors de la [ configuration d’une chaîne de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments de Dimension incluent le type de système d’exploitation utilisé. Par exemple, `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` ou `"Apple iOS"`.
