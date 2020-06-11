---
title: Types de système d’exploitation
description: Système d’exploitation, quelle que soit la version.
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---


# Types de système d’exploitation

La dimension &quot;Types de système d’exploitation&quot; indique le système d’exploitation global utilisé par le visiteur, quelles que soient les versions spécifiques. Cette dimension est utile pour comprendre non seulement quel système d’exploitation et quelle version spécifique sont les plus courants, mais aussi quelle plate-forme de système d’exploitation utilisent généralement les visiteurs.

## Renseigner cette dimension avec des données

Cette dimension fait référence à une table de choix interne à Adobe. La valeur de recherche est basée sur l’en-tête `User-Agent` HTTP dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par exemple via le lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi.

## Valeurs de dimension

Les valeurs de dimension incluent le type de systèmes d’exploitation utilisés. Examples include `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`, and `"Apple iOS"`.
