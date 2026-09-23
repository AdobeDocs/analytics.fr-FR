---
title: Compatible Java
description: Détermine si Java est activé dans le navigateur.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 51%
---
# Compatible Java

La [dimension](overview.md) « Compatible Java » détermine si Java est activé dans le navigateur au moment de l’appel. Elle s’avère utile lorsque vous souhaitez introduire des fonctionnalités Java sur votre site et savoir combien de visiteurs ont déjà activé Java. Pour ceux qui ont désactivé Java, vous pouvez proposer une solution alternative ou des instructions pour l’activer.

## Renseignement de cette dimension avec des données

Java activé est collecté automatiquement, côté client : AppMeasurement détecte si Java est activé dans le navigateur et indique « Y » ou « N ». Elle est prête à l’emploi dans toute implémentation d’AppMeasurement ou de Web SDK (balises). Il n’y a aucune variable à définir. Si vous collectez des données en dehors d’AppMeasurement ou de Web SDK (par exemple via l’API), envoyez « Y » ou « N » pour utiliser cette dimension.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun (collecté automatiquement) |
| **Champ Web SDK/XDM** | Aucun (collecté automatiquement) |
| **Paramètre de requête** | [`v`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<javaEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 1 octet |
| **Persistance** | S.O. |

## Éléments de dimension

Les éléments de dimension sont « Activé », « Désactivé » et « Inconnu ».

* **Activé** : Java est activé dans le navigateur. La chaîne de requête `v` contenait la valeur « Y ».
* **Désactivé** : Java est désactivé dans le navigateur ou celui-ci n’est pas compatible avec Java. La chaîne de requête `v` contenait la valeur « N ».
* **Inconnu** : AppMeasurement n’a pas pu déterminer la prise en charge de Java. La chaîne de requête `v` n’était pas présente dans la demande d’image.
