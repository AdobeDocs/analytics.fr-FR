---
title: Langue
description: Paramètre de langue préféré dans le navigateur.
translation-type: tm+mt
source-git-commit: 2c262e5345c39a71a6a54062c607273528294b24
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Langue

La dimension &quot;Langue&quot; affiche les principales langues dans lesquelles les visiteurs préfèrent voir le contenu. Cette dimension est utile lorsque vous souhaitez comprendre les langues préférées les plus fréquentes du visiteur pour faciliter les efforts de localisation.

> [!NOTE] Cette dimension ne collecte pas la langue de votre site. Si vous souhaitez collecter la langue de votre site dans une dimension, Adobe recommande d’utiliser une variable personnalisée, telle qu’une [eVar](evar.md).

## Renseigner cette dimension avec des données

Cette dimension fait référence à une table de choix interne à Adobe. La valeur de recherche est basée sur l’en-tête `Accept-Language` HTTP dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par exemple via le lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi.

## Valeurs de dimension

Les valeurs de dimension incluent des noms conviviaux des langues préférées du visiteur. Examples include `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`, and `"Spanish (Spain)"`. Si une demande d’image ne contient pas de langue valide dans l’en-tête HTTP, la valeur de la dimension est `"None"`.
