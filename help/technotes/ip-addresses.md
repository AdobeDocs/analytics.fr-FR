---
title: IP et domaines utilisés par l’Adobe Analytics
description: Si le pare-feu de votre entreprise bloque les adresses IP qui proviennent d’Adobe, utilisez cette liste pour mettre à jour les paramètres du pare-feu.
translation-type: tm+mt
source-git-commit: 891bc69f924b95cfe0bba2797319b59e1874dfd1
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 86%

---


# IP et domaines utilisés par l’Adobe Analytics

Certaines configurations de pare-feu bloquent les adresses IP en provenance des serveurs de collecte de données d’Adobe ou des serveurs responsables de l’accès aux données. Vous pouvez utiliser cette liste de plages pour modifier les paramètres de pare-feu de votre entreprise afin d’autoriser l’accès et d’envoyer des données depuis votre entreprise.

>[!IMPORTANT]
>
>Bien qu’Adobe fasse de son mieux pour garder ce document à jour, il se peut que la liste des plages d’adresses IP fasse l’objet de modifications. Les changements possibles comprennent la croissance et l’expansion des activités, un registre Internet nécessitant des modifications de l’espace d’adressage IP d’Adobe ou l’arrêt du fonctionnement d’un fournisseur d’accès Internet.

## Autorisation des domaines technologiques dépendants

Adobe Analytics utilise les hôtes suivants pour améliorer les performances et l’expérience du produit. Adobe recommande d’ajouter ces domaines à la liste autorisée de votre pare-feu pour une expérience optimale lors de l’utilisation d’Adobe Analytics.

| Technologie | Domaine |
| --- | --- |
| Domaines Adobe Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Domaine hérité Adobe Analytics | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Stockage Blob Microsoft Azure | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft Azure CDN | `aauicdnva7.azureedge.net` |

## Tous les blocs d’adresse IP Adobe Analytics

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

Si votre entreprise préfère autoriser des plages d’adresses IP spécifiques, vous pouvez utiliser le tableau suivant. Toutes les plages de cette section sont incluses dans le tableau ci-dessus.

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
| Virginie | Voir les hôtes AWS |

## Hôtes AWS

Adobe Analytics utilise les services Web Amazon dans le cadre de son processus de collecte de données. Le tableau suivant comprend les hôtes AWS réservés pour Adobe. Ces hôtes ne sont **pas** inclus dans la plage de blocs agrégés ci-dessus.

| Emplacement | Hôte |
| --- | --- |
| Australie | `13.238.77.77` |
| Australie | `52.62.21.192` |
| Australie | `54.66.152.159` |
| France | `15.237.76.117` |
| France | `15.237.136.106` |
| France | `35.181.18.61` |
| Inde | `13.232.177.101` |
| Inde | `13.235.4.163` |
| Inde | `3.6.119.69` |
| Irlande | `52.17.94.37` |
| Irlande | `52.49.253.16` |
| Irlande | `52.51.63.15` |
| Oregon | `44.233.255.254` |
| Oregon | `44.237.54.118` |
| Oregon | `44.238.157.95` |
| Singapour | `13.228.34.224` |
| Singapour | `18.136.20.161` |
| Singapour | `52.74.162.152` |
| Tokyo | `13.112.72.86` |
| Tokyo | `18.178.74.225` |
| Tokyo | `18.179.88.228` |
| Virginie | `3.213.168.181` |
| Virginie | `3.219.249.186` |
| Virginie | `3.220.129.153` |
| Virginie | `18.206.109.10` |
| Virginie | `18.211.197.67` |
| Virginie | `34.227.41.189` |
| Virginie | `34.228.124.176` |
| Virginie | `54.90.190.103` |
| Virginie | `54.174.149.161` |
