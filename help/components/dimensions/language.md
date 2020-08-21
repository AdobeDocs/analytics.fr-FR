---
title: Langue
description: Paramètre de langue préférée dans le navigateur.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 80%

---


# Langue

La dimension « Langue » affiche les principales langues dans lesquelles les visiteurs préfèrent voir le contenu. Cette dimension est utile lorsque vous souhaitez comprendre les langues préférées les plus fréquentes chez les visiteurs dans le cadre de vos efforts de localisation.

>[!NOTE]
>
>Cette dimension ne collecte pas la langue de votre site. Si vous souhaitez collecter la langue de votre site dans une dimension, Adobe recommande d’utiliser une variable personnalisée, telle qu’une [eVar](evar.md).

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `Accept-Language` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais d’Adobe Experience Platform Launch, par exemple), cette dimension est prête à l’emploi.

## Éléments de Dimension

Les éléments de Dimension incluent les noms conviviaux des langues préférées du visiteur. Par exemple, `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"` ou `"Spanish (Spain)"`. If an image request does not contain a valid language in the HTTP header, the dimension item is `"None"`.
