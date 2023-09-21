---
title: Types de systèmes d’exploitation
description: Le système d’exploitation, quelle que soit la version.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 85%

---

# Types de systèmes d’exploitation

Types de systèmes d’exploitation [dimension](overview.md) affiche le système d’exploitation global utilisé par le visiteur, quelles que soient les versions spécifiques. Cette dimension est utile pour identifier le système d’exploitation et la version spécifique les plus courants, mais aussi la plateforme de système d’exploitation généralement utilisée par les visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension incluent le type de système d’exploitation utilisé. Par exemple, `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` ou `"Apple iOS"`.
