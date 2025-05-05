---
title: Adresses IP utilisées par Adobe Analytics
description: Si le pare-feu de votre entreprise bloque les adresses IP qui proviennent d’Adobe, utilisez cette liste pour mettre à jour les paramètres du pare-feu.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 5ac6da2eb53d2748e8838ef2c6334a771abc26c9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 35%

---

# Adresses IP utilisées par Adobe Analytics

Certaines configurations de pare-feu bloquent les adresses IP en provenance des serveurs de collecte de données d’Adobe ou des serveurs responsables de l’accès aux données. Vous pouvez utiliser cette liste de plages pour modifier les paramètres de pare-feu de votre entreprise afin d’autoriser l’accès et d’envoyer des données depuis votre entreprise.

Toutes les adresses IP utilisées par Adobe Analytics font partie des [adresses IP utilisées par Adobe Experience Cloud](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/ip-addresses), à l’exception du module complémentaire China Performance Optimization.

## Adresses IP d’optimisation des performances de la Chine

Le module complémentaire d’optimisation des performances en Chine est un service payant supplémentaire qui améliore les performances de collecte de données d’AppMeasurement pour les visiteurs en Chine. Contactez votre équipe de compte d’Adobe pour en savoir plus sur l’utilisation de cette fonctionnalité.

>[!IMPORTANT]
>
>La collecte de données régionale pour la Chine n’est pas disponible pour la collecte de données du SDK Web. Ces serveurs s’appliquent uniquement aux bibliothèques AppMeasurement.

Les serveurs de collecte de données régionaux en Chine utilisent les adresses IP suivantes :

| Emplacement | Hôte |
| --- | --- |
| Chine | `52.80.168.159` |
| Chine | `52.80.199.104` |
| Chine | `54.223.199.8` |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>
>[Adresses IP utilisées par Adobe Experience Cloud](https://experienceleague.adobe.com/fr/docs/core-services/interface/data-collection/ip-addresses)
>
>[Domaines utilisés par Adobe Analytics](domains.md)
