---
title: Profondeur de couleur
description: Profondeur de couleur de l’appareil.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 94%

---


# Profondeur de couleur

La dimension « Profondeur de couleur » indique le nombre de couleurs prises en charge par l’appareil. Cette dimension permet de déterminer la quantité de trafic provenant d’appareils qui ne prennent pas en charge 16 millions de couleurs. Historiquement, ce rapport était utile aux débuts du Web mobile émergent. Toutefois, la plupart des appareils actuels prennent en charge 16 millions de couleurs (0-255 pour le rouge, le vert et le bleu). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche, convertissant la valeur en bits en un format plus lisible. Elle collecte les données de la [`c`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement utilise la variable `screen.colorDepth` pour renseigner la chaîne de requête de demande d’image. Si vous utilisez AppMeasurement (par le biais d’Adobe Experience Platform Launch, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `c` sur chaque accès avec une valeur en bits valide.

## Éléments de Dimension

Les éléments de Dimension incluent le nombre de couleurs prises en charge par le périphérique. Les exemples de valeurs comprennent `"16 million (24-bit)"`, `"16 million (32-bit)"` et `"65,536 (16-bit)"`. Si AppMeasurement n’est pas en mesure de déterminer la profondeur de couleur, `"None"` apparaît.

>[!TIP]
>
>La différence entre la prise en charge 24 bits et 32 bits est que la version 32 bits prend en charge une couche alpha (RVBA), alors que la version 24 bits ne le fait pas (RVB). Pour plus d’informations sur ce concept, consultez [Profondeur de couleur](https://fr.wikipedia.org/wiki/Profondeur_de_couleur_(informatique)) sur Wikipédia.
