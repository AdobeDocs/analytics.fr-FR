---
title: Langue
description: Paramètre de langue préférée dans le navigateur.
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: ht
source-wordcount: '158'
ht-degree: 100%

---

# Langue

La dimension « Langue » affiche les principales langues dans lesquelles les visiteurs préfèrent voir le contenu. Cette dimension est utile lorsque vous souhaitez comprendre les langues préférées les plus fréquentes chez les visiteurs dans le cadre de vos efforts de localisation.

>[!NOTE]
>
>Cette dimension ne collecte pas la langue de votre site. Si vous souhaitez collecter la langue de votre site dans une dimension, Adobe recommande d’utiliser une variable personnalisée, telle qu’une [eVar](evar.md).

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `Accept-Language` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension incluent des noms conviviaux pour les langues préférées des visiteurs. Par exemple, `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"` ou `"Spanish (Spain)"`. Si une demande d’image ne contient pas de langue valide dans l’en-tête HTTP, l’élément de dimension est `"None"`.
