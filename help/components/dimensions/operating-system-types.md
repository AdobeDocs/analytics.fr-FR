---
title: Types de systèmes d’exploitation
description: Le système d’exploitation, quelle que soit la version.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 100%

---

# Types de systèmes d’exploitation

La dimension « Types de systèmes d’exploitation » indique le système d’exploitation global utilisé par le visiteur, quelle que soit la version spécifique. Cette dimension est utile pour identifier le système d’exploitation et la version spécifique les plus courants, mais aussi la plateforme de système d’exploitation généralement utilisée par les visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension incluent le type de système d’exploitation utilisé. Par exemple, `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` ou `"Apple iOS"`.
