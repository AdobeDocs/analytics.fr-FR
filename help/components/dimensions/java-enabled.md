---
title: Compatible Java
description: Détermine si Java est activé dans le navigateur.
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 90%

---

# Compatible Java

La dimension « Compatible Java » détermine si Java est activé dans le navigateur. Elle s’avère utile lorsque vous souhaitez introduire des fonctionnalités Java sur votre site et savoir combien de visiteurs ont déjà activé Java. Pour ceux qui ont désactivé Java, vous pouvez fournir une alternative ou des instructions pour son activation.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`v`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données en détectant si Java est activé dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par le biais de balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `v` contenant « Y » ou « N » si vous souhaitez utiliser cette dimension.

## Éléments de dimension

Les éléments de dimension sont « Activé », « Désactivé » et « Inconnu ».

* **Activé** : Java est activé dans le navigateur. La chaîne de requête `v` contenait la valeur « Y ».
* **Désactivé** : Java est désactivé dans le navigateur ou celui-ci n’est pas compatible avec Java. La chaîne de requête `v` contenait la valeur « N ».
* **Inconnu** : AppMeasurement n’a pas pu déterminer la prise en charge de Java. La chaîne de requête `v` n’était pas présente dans la demande d’image.
