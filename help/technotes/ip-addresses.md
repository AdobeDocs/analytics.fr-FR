---
title: Adresses IP et domaines utilisés par Adobe Analytics
description: Si le pare-feu de votre entreprise bloque les adresses IP qui proviennent d’Adobe, utilisez cette liste pour mettre à jour les paramètres du pare-feu.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: ea859717c6a40b4eeeb9eca54b95718859af9c7b
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 32%

---

# Adresses IP et domaines utilisés par Adobe Analytics

Certaines configurations de pare-feu bloquent les domaines sur lesquels Adobe Analytics repose pour son interface de produit. Vous pouvez utiliser cette liste de domaines pour modifier les paramètres réseau de votre entreprise afin d’autoriser l’accès aux produits au sein de votre entreprise.

## Autorisation des domaines technologiques dépendants

Adobe Analytics utilise les hôtes suivants pour améliorer les performances et l’expérience du produit. Adobe recommande d’autoriser ces domaines à travers le pare-feu de votre entreprise pour une expérience optimale avec Adobe Analytics.

| Technologie | Domaine |
| --- | --- |
| Domaines Adobe Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Domaine hérité Adobe Analytics | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Stockage Blob Microsoft Azure | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Blocs d’adresses IP Adobe Experience Cloud

Outre les domaines ci-dessus, Adobe Analytics s’appuie sur plusieurs blocs d’adresses IP pour collecter des données et exporter des rapports.

Voir Adresses IP de Adobe Experience Cloud pour obtenir la liste complète des plages d’adresses IP.

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
