---
title: Intensité des couleurs
description: Profondeur de couleur du périphérique.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# Intensité des couleurs

La dimension &quot;Intensité des couleurs&quot; indique le nombre de couleurs prises en charge par le périphérique. Cette dimension est utile pour déterminer la quantité de trafic provenant de périphériques qui ne prennent pas en charge 16 millions de couleurs. Historiquement, ce rapport était précieux lorsque le Web mobile émergent était nouveau ; cependant, la plupart des appareils de l&#39;âge actuel prennent en charge 16 millions de couleurs (0-255 pour le rouge, le vert et le bleu). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Renseigner cette dimension avec des données

Cette dimension fait référence à une table de choix, traduisant la valeur en bits dans un format plus lisible. Elle collecte les données de la chaîne [`c` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement utilise la `screen.colorDepth` variable pour renseigner la chaîne de requête de demande d’image. Si vous utilisez AppMeasurement (par le biais du lancement d’Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de `c` requête sur chaque accès avec une valeur de bit valide.

## Valeurs de dimension

Les valeurs de dimension comprennent le nombre de couleurs prises en charge par le périphérique. Les exemples de valeurs incluent `"16 million (24-bit)"`, `"16 million (32-bit)"`et `"65,536 (16-bit)"`. Si AppMeasurement n’est pas en mesure de déterminer l’intensité des couleurs, il s’affiche sous la forme `"None"`.

>[!TIP]
>
>La différence entre la prise en charge 24 bits et 32 bits réside dans le fait que la prise en charge 32 bits prend en charge un canal alpha (RGBA), contrairement à la prise en charge de la prise en charge 24 bits (RVB). Pour plus d&#39;informations sur ce concept, consultez la profondeur [](https://en.wikipedia.org/wiki/Color_depth) de couleur sur Wikipedia.
