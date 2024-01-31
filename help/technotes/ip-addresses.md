---
title: Adresses IP et domaines utilisés par Adobe Analytics
description: Si le pare-feu de votre entreprise bloque les adresses IP qui proviennent d’Adobe, utilisez cette liste pour mettre à jour les paramètres du pare-feu.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 3483e209a6ae8c2b37d45903b270a2adb3b297ca
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 67%

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

## Tous les blocs dʼadresses IP Adobe Analytics

Le tableau suivant couvre toutes les adresses IP détenues par l’Adobe utilisées pour Adobe Analytics. Ils n’incluent pas tous les services hébergés dans des clouds publics.

| Bloc d’adresse IP (notation CIDR) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |
| `185.34.188.0/22` |
| `192.243.240.0/22` |

## Collecte de données et blocs d’adresses IP FTP

Si votre entreprise préfère autoriser des plages d’adresses IP spécifiques, vous pouvez utiliser le tableau suivant. Toutes les plages de cette section sont incluses dans le tableau ci-dessus. Les connexions FTP pour Data Warehouse et les flux de données proviennent uniquement des sites de Londres, de lʼOregon et de Singapour.

| Emplacement | Plage IP (notation CIDR) |
| --- | --- |
| Australie | `63.140.55.0/24` |
| Australie | `63.140.56.0/23` |
| Californie | `63.140.32.0/23` |
| Californie | `63.140.34.0/24` |
| France | `63.140.62.0/23` |
| Inde | `66.117.20.0/24` |
| Inde | `66.117.22.0/23` |
| Japon | `130.248.169.0/23` |
| Japon | `63.140.50.0/23` |
| Japon | `66.117.31.0/24` |
| Londres | `66.235.156.0/24` |
| Londres | `185.34.188.0/22` |
| Londres | `130.248.152.0/22` |
| Londres | `130.248.244.0/23` |
| Oregon | `66.235.132.0/22` |
| Oregon | `130.248.130.0/23` |
| Oregon | `130.248.150.0/24` |
| Oregon | `130.248.160.0/21` |
| Oregon | `192.243.242.0/24` |
| Singapour | `130.248.170.0/23` |
| Singapour | `130.248.240.0/24` |
| Singapour | `63.140.44.0/22` |
| Singapour | `63.140.48.0/23` |
| Singapour | `66.117.30.0/24` |
| Virginie | `63.140.38.0/23` |
| Virginie | `63.140.54.0/24` |

## Hôtes AWS

Adobe Analytics utilise Amazon Web Services dans le cadre de son processus de collecte de données. Le tableau suivant comprend les adresses d’hôte AWS IPv4 réservées à l’Adobe. Ces hôtes ne sont **pas** inclus dans la plage de blocs agrégés ci-dessus.

| Emplacement | Hôte |
| --- | --- |
| Chine | `52.80.168.159` |
| Chine | `52.80.199.104` |
| Chine | `54.223.199.8` |

Le tableau suivant comprend les blocs d’adresses IPv6 d’AWS utilisés par Adobe. Ces hôtes ne sont **pas** inclus dans la plage de blocs agrégés ci-dessus.

| Emplacement | Hôte |
| --- | --- |
| Australie | `2406:da1c:406:1a00::/56` |
| Australie | `2406:da1c:ce5:b400::/56` |
| Californie | `2600:1f1c:366:d900::/56` |
| France | `2a05:d012:706:d000::/56` |
| Inde | `2406:da1a:f34:6a00::/56` |
| Irlande | `2a05:d018:309:600::/56` |
| Japon | `2406:da14:b07:ab00::/56` |
| Oregon | `2600:1f14:1eb:7d00::/56` |
| Oregon | `2600:1f14:9d3:2b00::/56` |
| Singapour | `2406:da18:6e8:1e00::/56` |
| Virginie | `2600:1f18:1a20:e800::/56` |
| Virginie | `2600:1f18:4fd:6000::/56` |
| Virginie | `2600:1f18:b00:e100::/56` |
| Virginie | `2600:1f18:d1f:bd00::/56` |
