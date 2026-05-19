---
title: Adresses IP utilisées par Adobe Analytics
description: Si le pare-feu de votre entreprise bloque les adresses IP qui proviennent d’Adobe, utilisez cette liste pour mettre à jour les paramètres du pare-feu.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
TQID: https://experienceleague.adobe.com/-4XZdprTBXpIaFnHeXBQsAr5YoZMW4ocnZRY50bHGUs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 32%

---

# Adresses IP utilisées par Adobe Analytics

Certaines configurations de pare-feu bloquent les adresses IP en provenance des serveurs de collecte de données d’Adobe ou des serveurs responsables de l’accès aux données. Vous pouvez utiliser cette liste de plages pour modifier les paramètres de pare-feu de votre entreprise afin d’autoriser l’accès et d’envoyer des données depuis votre entreprise.

Toutes les adresses IP utilisées par Adobe Analytics font partie des adresses [IP utilisées par CX Enterprise](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses), à l’exception du package complémentaire Optimisation des performances pour la Chine .

## Adresses IP d’optimisation des performances pour la Chine

Le package de modules complémentaires Optimisation des performances en Chine est un service payant supplémentaire qui améliore les performances de la collecte de données AppMeasurement pour les visiteurs en Chine. Pour en savoir plus sur l’utilisation de cette fonctionnalité, contactez l’équipe chargée de votre compte Adobe.

>[!IMPORTANT]
>
>RDC Chine n’est pas disponible pour la collecte de données Web SDK. Ces serveurs s’appliquent uniquement aux bibliothèques AppMeasurement.

Les serveurs de collecte de données régionaux en Chine utilisent les adresses IP suivantes :

| Emplacement | Hôte |
| --- | --- |
| Chine | `52.80.168.159` |
| Chine | `52.80.199.104` |
| Chine | `54.223.199.8` |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>
>[Adresses IP utilisées par CX Enterprise](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)
>
>[Domaines utilisés par Adobe Analytics](domains.md)
