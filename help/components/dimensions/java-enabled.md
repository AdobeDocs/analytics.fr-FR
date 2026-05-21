---
title: Compatible Java
description: Détermine si Java est activé dans le navigateur.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 93%

---

# Compatible Java

La [dimension](overview.md) « Compatible Java » détermine si Java est activé dans le navigateur au moment de l’appel. Elle s’avère utile lorsque vous souhaitez introduire des fonctionnalités Java sur votre site et savoir combien de visiteurs ont déjà activé Java. Pour ceux qui ont désactivé Java, vous pouvez fournir une alternative ou des instructions pour son activation.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la chaîne de requête [`v`](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données en détectant si Java est activé dans le navigateur. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi. Si vous utilisez une méthode de collecte de données en dehors d’AppMeasurement (via l’API, par exemple), veillez à inclure le paramètre de chaîne de requête `v` contenant « Y » ou « N » si vous souhaitez utiliser cette dimension.

## Éléments de dimension

Les éléments de dimension sont « Activé », « Désactivé » et « Inconnu ».

* **Activé** : Java est activé dans le navigateur. La chaîne de requête `v` contenait la valeur « Y ».
* **Désactivé** : Java est désactivé dans le navigateur ou celui-ci n’est pas compatible avec Java. La chaîne de requête `v` contenait la valeur « N ».
* **Inconnu** : AppMeasurement n’a pas pu déterminer la prise en charge de Java. La chaîne de requête `v` n’était pas présente dans la demande d’image.
