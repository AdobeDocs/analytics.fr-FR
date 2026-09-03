---
description: Les attributs du client sont stockés dans un nouveau type d’élément appelé VisAttr, qui peut être configuré comme une dimension ou une mesure.
title: Attributs du client
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
TQID: https://experienceleague.adobe.com/J-KoYBPg-bECW1utOk2L0YLtBWd9-jHT6gwAEm54fs4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 135
ht-degree: 73%

---

# Attributs du client

{{legacy-arb}}

Les attributs du client sont stockés dans un nouveau type d’élément appelé VisAttr, qui peut être configuré comme une dimension ou une mesure.

Pour plus d’informations sur le téléchargement des attributs du client, reportez-vous à l’aide d’[CX Enterprise](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=fr).

* S’il est configuré en tant que mesure, VisAttr est exposé à la fois en tant que mesure et « dimension ».

  ![Capture d’écran affichant la mesure et la dimension Attributs du client.](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Il prend en charge la même répartition qu’une eVar (tout peut être réparti par tout).
* VisAttr prend en charge toutes les mesures d’eVar.
* VisAttr en tant que mesure prend en charge la « périodisation » (par ex. Durée moyenne de la visite du site : 0 à 30, 31 à 60, ...).
* VisAttr est disponible comme une dimension de segmentation.
