---
title: Compatible Java
description: Détermine si Java est activé dans le navigateur.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 1%

---


# Compatible Java

La dimension &quot;Java enabled&quot; détermine si Java est activé dans le navigateur à l’époque. Il s’avère utile lorsque vous souhaitez introduire des fonctionnalités Java sur votre site et que vous souhaitez savoir combien de visiteurs ont déjà activé Java. Pour ceux qui ont désactivé Java, vous pouvez fournir une alternative ou des instructions sur la manière de l’activer.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la chaîne [`v` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données en détectant si Java est activé dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par exemple par le biais du lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (par exemple via l’API), veillez à inclure le paramètre de chaîne de `v` requête contenant &quot;Y&quot; ou &quot;N&quot; si vous souhaitez utiliser cette dimension.

## Éléments de dimension

Les éléments de dimension sont &quot;Activé&quot;, &quot;Désactivé&quot; et &quot;Inconnu&quot;.

* **Activé**: Java est activé dans le navigateur. La chaîne de `v` requête contenait la valeur &quot;Y&quot;.
* **Désactivé**: Java est désactivé dans le navigateur ou n’est pas pris en charge par d’autres méthodes. La chaîne de `v` requête contenait la valeur &quot;N&quot;.
* **Inconnu**: AppMeasurement n&#39;a pas pu déterminer la prise en charge de Java. La chaîne de `v` requête n&#39;était pas présente dans la demande d&#39;image.
