---
title: Adresses IP et domaines utilisés par Adobe Analytics
description: Si le pare-feu de votre entreprise bloque les adresses IP qui proviennent d’Adobe, utilisez cette liste pour mettre à jour les paramètres du pare-feu.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 6788b904295fd92642d27ade65a31d61897069a3
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 85%

---

# Adresses IP et domaines utilisés par Adobe Analytics

Certaines configurations de pare-feu bloquent les adresses IP en provenance des serveurs de collecte de données d’Adobe ou des serveurs responsables de l’accès aux données. Vous pouvez utiliser cette liste de plages pour modifier les paramètres de pare-feu de votre entreprise afin d’autoriser l’accès et d’envoyer des données depuis votre entreprise. Cette page comprend les systèmes entrants (tels que la collecte de données) et les systèmes sortants (tels que les flux de données) utilisés par l’Adobe.

>[!IMPORTANT]
>
>Bien qu’Adobe fasse de son mieux pour garder ce document à jour, il ne peut garantir que la liste des plages d’adresses IP reste la même. Les changements possibles comprennent la croissance et l’expansion des activités, un registre Internet nécessitant des modifications de l’espace d’adressage IP d’Adobe ou l’arrêt du fonctionnement d’un fournisseur d’accès Internet.

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

## Tous les blocs dʼadresses IP des collectes de données d’Adobe Analytics

Le tableau suivant couvre tous les serveurs de collecte de données standard et les serveurs de collecte de données régionaux pour Adobe Analytics. Elles n’incluent pas les hôtes AWS individuels.

| Bloc d’adresse IP (notation CIDR) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |
| `172.82.192.0/18` |
| `185.34.188.0/22` |
| `192.243.224.0/19` |
| `205.219.231.0/24` |
| `208.67.40.0/22` |
| `208.77.136.0/22` |

## Collecte de données et blocs d’adresses IP FTP

Si votre entreprise préfère autoriser des plages d’adresses IP spécifiques, vous pouvez utiliser le tableau suivant. Toutes les plages de cette section sont incluses dans le tableau ci-dessus. Les connexions FTP pour Data Warehouse et les flux de données proviennent uniquement des sites de Londres, de lʼOregon et de Singapour.

| Emplacement | Plage IP (notation CIDR) |
| --- | --- |
| Amsterdam | `66.117.28.0/23` |
| Dallas | `205.219.231.0/24` |
| Dallas | `66.235.152.0/22` |
| Dallas | `66.235.140.0/22` |
| Dallas | `63.140.32.0/21` |
| Dallas | `172.82.208.0/22` |
| Hong Kong (RAS de la Chine) | `66.117.24.0/22` |
| Londres | `66.235.156.0/24` |
| Londres | `66.235.148.0/23` |
| Londres | `63.140.40.0/22` |
| Londres | `208.67.41.0/24` |
| Londres | `192.243.254.0/23` |
| Londres | `192.243.244.0/22` |
| Londres | `185.34.188.0/23` |
| Londres | `130.248.152.0/21` |
| Londres | `172.82.224.0/21` |
| Londres | `172.82.232.0/21` |
| Oregon | `192.243.240.0/22` |
| Oregon | `192.243.232.0/21` |
| Oregon | `192.243.224.0/21` |
| Oregon | `130.248.160.0/21` |
| Oregon | `130.248.148.0/22` |
| Oregon | `172.82.192.0/21` |
| Oregon | `172.82.216.0/21` |
| Paris | `208.67.40.0/24` |
| Singapour | `66.235.150.0/24` |
| Singapour | `66.235.130.0/23` |
| Singapour | `63.140.44.0/22` |
| Singapour | `208.67.43.0/24` |
| Singapour | `172.82.240.0/22` |
| Singapour | `172.82.246.0/23` |
| Singapour | `172.82.248.0/21` |
| San José | `66.117.20.0/24` |
| San José | `66.235.132.0/22` |
| San José | `130.248.128.0/22` |
| San José | `192.243.248.0/23` |
| San José | `172.82.200.0/22` |
| San José | `66.235.136.0/22` |
| San José | `208.91.175.0/24` |
| San José | `208.91.174.0/24` |
| San José | `208.91.169.0/24` |
| Sydney | `216.104.216.0/23` |
| Tokyo | `66.235.159.0/24` |
| Tokyo | `66.117.21.0/24` |
| Tokyo | `63.140.52.0/24` |
| Tokyo | `63.140.50.0/23` |
| Virginie | `66.235.144.0/22` |
| Virginie | `208.77.138.0/23` |
| Virginie | `208.77.136.0/23` |
| Virginie | `192.243.250.0/23` |
| Virginie | `130.248.144.0/22` |
| Virginie | `172.82.204.0/22` |
| Virginie | `172.82.212.0/22` |

## Hôtes AWS

Adobe Analytics utilise Amazon Web Services dans le cadre de son processus de collecte de données. Le tableau suivant comprend les hôtes AWS réservés pour Adobe. Ces hôtes ne sont **pas** inclus dans la plage de blocs agrégés ci-dessus.

| Emplacement | Hôte |
| --- | --- |
| Chine | `140.179.89.228` |
| Chine | `140.179.125.98` |
| France | `13.36.218.177` |
| France | `15.188.95.229` |
| France | `15.236.176.210` |
| Irlande | `54.74.170.177` |
| Irlande | `54.195.254.128` |
| Irlande | `54.220.133.225` |
| Oregon | `52.10.149.115` |
| Oregon | `52.40.172.46` |
| Oregon | `54.212.155.93` |
| Virginie | `3.216.131.23` |
| Virginie | `34.204.237.47` |
| Virginie | `54.163.234.74` |
