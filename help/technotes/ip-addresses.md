---
title: IP et domaines utilisés par l’Adobe Analytics
description: Si le pare-feu de votre entreprise bloque les adresses IP qui proviennent d'Adobe, utilisez cette liste pour mettre à jour vos paramètres de pare-feu.
translation-type: tm+mt
source-git-commit: 4faa557120f937eb240e6d12ab0e2fc0ae7372ab
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 16%

---


# IP et domaines utilisés par l’Adobe Analytics

Certaines configurations de pare-feu bloquent les adresses IP provenant des serveurs de collecte de données d&#39;Adobe ou des serveurs responsables de l&#39;accès aux données. Vous pouvez utiliser cette liste de plages pour modifier les paramètres de pare-feu de votre entreprise afin d’autoriser l’accès et d’envoyer des données depuis votre entreprise.

>[!IMPORTANT]
>
>Bien que l&#39;Adobe fasse de son mieux pour maintenir ce document à jour, il ne peut garantir que la liste des plages d&#39;adresses IP reste la même. Les changements possibles incluent la croissance et l&#39;expansion de l&#39;entreprise, un registre Internet nécessite des modifications de l&#39;espace d&#39;adresse IP de l&#39;Adobe, ou un prestataire Internet cesse de fonctionner.

## Autoriser les domaines technologiques dépendants

adobe analytics utilise les hôtes suivants pour améliorer les performances et l’expérience des produits. adobe recommande d’ajouter ces domaines à la liste autorisée de votre pare-feu afin d’optimiser l’utilisation de Adobe Analytics.

| Technologie | Domaine |
| --- | --- |
| Domaine Adobe Analytics | `adobe.com` |
| Domaine hérité Adobe Analytics | `omniture.com` |
| amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Enregistrement Blob Microsoft Azure | `awaascicdprodva7.blob.core.windows.net` |
| CDN Microsoft Azure | `aauicdnva7.azureedge.net` |

## Tous les blocs d’adresse IP Adobe Analytics

Le tableau suivant couvre tous les serveurs de collecte de données standard et les serveurs de collecte de données régionaux pour Adobe Analytics. Ils n’incluent pas les hôtes AWS individuels.

| Bloc IP (NOTATION CIDR) |
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

Si votre organisation préfère autoriser des plages d’adresses IP spécifiques, vous pouvez utiliser le tableau suivant. Toutes les plages de cette section sont incluses dans le tableau ci-dessus.

| Emplacement | Plage IP (NOTATION CIDR) |
| --- | --- |
| Amsterdam | `66.117.28.0/23` |
| Dallas | `205.219.231.0/24` |
| Dallas | `66.235.152.0/22` |
| Dallas | `66.235.140.0/22` |
| Dallas | `63.140.32.0/21` |
| Dallas | `172.82.208.0/22` |
| RAS de Hong Kong (Chine) | `66.117.24.0/22` |
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
| San Jose | `66.117.20.0/24` |
| San Jose | `66.235.132.0/22` |
| San Jose | `130.248.128.0/22` |
| San Jose | `192.243.248.0/23` |
| San Jose | `172.82.200.0/22` |
| San Jose | `66.235.136.0/22` |
| San Jose | `208.91.175.0/24` |
| San Jose | `208.91.174.0/24` |
| San Jose | `208.91.169.0/24` |
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
| Virginie | Voir Hôtes AWS |

## Hôtes AWS

adobe analytics utilise les services Web Amazon dans le cadre de son processus de collecte de données. Le tableau suivant comprend les hôtes AWS réservés à l’Adobe. Ces hôtes **ne sont pas** inclus dans la plage de blocs d&#39;agrégat ci-dessus.

| Emplacement | Hôte |
| --- | --- |
| Australie | `13.238.77.77` |
| Australie | `52.62.21.192` |
| Australie | `54.66.152.159` |
| France | `15.188.154.177` |
| France | `15.236.175.233` |
| France | `15.236.9.100` |
| Inde | `13.232.177.101` |
| Inde | `13.235.4.163` |
| Inde | `3.6.119.69` |
| Irlande | `52.17.94.37` |
| Irlande | `52.49.253.16` |
| Irlande | `52.51.63.15` |
| Londres | `172.82.228.19` |
| Oregon | `52.42.60.49` |
| Oregon | `54.212.169.56` |
| Oregon | `54.214.170.191` |
| Singapour | `13.228.34.224` |
| Singapour | `18.136.20.161` |
| Singapour | `52.74.162.152` |
| Tokyo | `13.112.72.86` |
| Tokyo | `18.178.74.225` |
| Tokyo | `18.179.88.228` |
| Virginie | `34.234.106.101` |
| Virginie | `52.22.231.198` |
| Virginie | `54.157.65.136` |
| Virginie | `107.23.142.4` |
| Virginie | `34.192.14.184` |
| Virginie | `34.192.146.173` |
| Virginie | `34.192.229.76` |
| Virginie | `34.196.183.216` |
| Virginie | `34.196.219.120` |
| Virginie | `34.196.54.55` |
| Virginie | `34.197.179.21` |
| Virginie | `34.197.45.49` |
| Virginie | `34.197.93.163` |
| Virginie | `34.198.80.27` |
| Virginie | `34.199.102.192` |
| Virginie | `34.199.46.40` |
| Virginie | `34.199.99.62` |
| Virginie | `34.200.67.35` |
| Virginie | `34.204.146.235` |
| Virginie | `34.204.164.1` |
| Virginie | `34.204.27.249` |
| Virginie | `34.205.224.111` |
| Virginie | `34.206.69.71` |
| Virginie | `52.193.88.44` |
| Virginie | `52.200.108.250` |
| Virginie | `52.200.171.156` |
| Virginie | `52.201.49.195` |
| Virginie | `52.205.244.105` |
| Virginie | `52.207.161.156` |
| Virginie | `52.22.148.55` |
| Virginie | `52.4.155.255` |
| Virginie | `52.72.182.205` |
| Virginie | `52.72.185.111` |
| Virginie | `54.152.218.194` |
| Virginie | `54.173.37.66` |
| Virginie | `54.173.69.38` |
| Virginie | `54.236.180.248` |
| Virginie | `54.236.71.218` |
| Virginie | `54.80.103.29` |
| Virginie | `54.88.180.124` |
