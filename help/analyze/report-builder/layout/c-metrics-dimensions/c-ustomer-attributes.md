---
description: Les attributs du client sont stockés dans un nouveau type d’élément appelé VisAttr, qui peut être configuré comme une dimension ou une mesure.
title: Attributs du client
uuid: a8340b83-d7ba-46fe-bb20-b546cdf375b8
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 100%

---

# Attributs du client

Les attributs du client sont stockés dans un nouveau type d’élément appelé VisAttr, qui peut être configuré comme une dimension ou une mesure.

Pour obtenir des informations plus détaillées sur le transfert des attributs du client, reportez-vous à l’[aide d’Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=fr).

* S’il est configuré comme une mesure, VisAttr est présenté comme dimension et comme mesure.

   ![](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Il prend en charge la même ventilation qu’une eVar (tout peut être ventilé par tout).
* VisAttr prend en charge toutes les mesures d’eVar.
* VisAttr en tant que mesure prend en charge la « périodisation » (par ex. Durée moyenne de la visite du site : 0 à 30, 31 à 60, ...).
* VisAttr est disponible comme une dimension de segmentation.
