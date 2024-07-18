---
description: Les attributs du client sont stockés dans un nouveau type d’élément appelé VisAttr, qui peut être configuré comme une dimension ou une mesure.
title: Attributs du client
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 83%

---

# Attributs du client

Les attributs du client sont stockés dans un nouveau type d’élément appelé VisAttr, qui peut être configuré comme une dimension ou une mesure.

Pour obtenir des informations plus détaillées sur le chargement des attributs du client, reportez-vous à l’[aide d’Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=fr).

* S’il est configuré en tant que mesure, VisAttr est exposé en tant que mesure et &quot;dimension&quot;.

  ![Capture d’écran montrant les attributs du client de mesure et de dimension.](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Il prend en charge la même répartition qu’une eVar (tout peut être réparti par tout).
* VisAttr prend en charge toutes les mesures d’eVar.
* VisAttr en tant que mesure prend en charge la « périodisation » (par ex. Durée moyenne de la visite du site : 0 à 30, 31 à 60, ...).
* VisAttr est disponible comme une dimension de segmentation.
