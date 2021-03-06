---
title: Système d’exploitation
description: Système d’exploitation du visiteur.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 100%

---

# Système d’exploitation

La dimension « Système d’exploitation » indique le système d’exploitation et la version utilisés par le visiteur. Si votre propriété Web comporte des fonctionnalités spécifiques au système d’exploitation, cette dimension vous permet d’identifier les systèmes d’exploitation les plus courants.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension incluent les systèmes d’exploitation utilisés par les visiteurs. Par exemple, `"Windows 10"`, `"OS X 10.15"` et `"Android 9"`.
