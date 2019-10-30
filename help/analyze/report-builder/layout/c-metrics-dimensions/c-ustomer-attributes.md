---
description: Les attributs du client sont stockés dans un nouveau type d’élément appelé VisAttr, qui peut être configuré comme une dimension ou une mesure.
seo-description: Les attributs du client sont stockés dans un nouveau type d’élément appelé VisAttr, qui peut être configuré comme une dimension ou une mesure.
seo-title: Attributs du client
title: Attributs du client
uuid: a8340b83-d7ba-46fe-bb20-b546cdf375b8
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Attributs du client

Les attributs du client sont stockés dans un nouveau type d’élément appelé VisAttr, qui peut être configuré comme une dimension ou une mesure.

Pour obtenir des informations plus détaillées sur le transfert des attributs du client, reportez-vous à l’[aide d’Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html).

* S’il est configuré en tant que mesure, VisAttr est exposé en tant que "dimension" et mesure.

   ![](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Il prend en charge la même ventilation qu’une eVar (tout peut être ventilé par tout).
* VisAttr prend en charge toutes les mesures d’eVar.
* VisAttr en tant que mesure prend en charge la "bucketisation" (comme Durée de consultation du site : 0 à 30, 31 à 60, ...)
* VisAttr est disponible comme une dimension de segmentation.

