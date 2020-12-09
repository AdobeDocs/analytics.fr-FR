---
title: Collecte de données régionales
description: Informations sur la collecte de données régionales
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 77%

---


# Collecte de données régionales

Adobe Experience Cloud utilise la collecte de données régionales (RDC) afin que les interactions entre vos utilisateurs finaux et Adobe Experience Cloud se produisent le plus près possible de vos utilisateurs finaux. Cela améliore les performances du site ou de l’application et garantit que les données sont collectées le plus vite possible pour optimiser l’expérience de l’utilisateur final. Une fois que les données issues des propriétés numériques sont collectées au niveau régional dans un centre de collecte de données, elles sont transférées au moyen d’une connexion sécurisée à un centre de traitement de données, où elles sont traitées et mises à la disposition des produits dans Adobe Experience Cloud.

>[!IMPORTANT]
>
>Le package d’Ajoute-on China RDC (China Performance Optimization) est un module complémentaire payant pour Adobe Analytics. L&#39;optimisation des performances de l&#39;Adobe en Chine continentale permet aux clients en Chine d&#39;envoyer directement des données au noeud de périphérie de la Chine, plutôt qu&#39;à d&#39;autres emplacements à l&#39;échelle mondiale. Ceci améliore les temps de chargement des pages et la précision des données lors de l’envoi des données vers des noeuds en dehors de la Chine. Pour plus d&#39;informations, contactez votre représentant commercial d&#39;Adobe.

La collecte de données régionale inclut les emplacements suivants (sujets à modification) :

## Collecte de données HTTP et tierces

| Type de collecte de données régionale | Centres de collecte de données |
|---------------------|-------------------|
| Par défaut | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney |

Note: If your Analytics image request is sent to the `adobedc`, `2o7.net` or `omtrdc.net` endpoints, then you have third-party data collection. Vous pouvez le déterminer si vous voyez l’un des terminaux présents dans l’URL de vos requêtes.

## Collecte de données HTTPS propriétaires

| Type de collecte de données régionale | Centres de collecte de données |
|---------------------|-------------------|
| Mondiale (par défaut) | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney |
| Amériques uniquement | Oregon, Virginie |
| Europe uniquement | Irlande, Paris |
| Asie-Pacifique uniquement | Mumbai, Singapour, Tokyo, Sydney |

Remarque : Experience Edge Global offre les meilleures performances pour vos utilisateurs finaux.  Si vous souhaitez utiliser un autre type de collecte de données régionale, contactez l’assistance clientèle d’Adobe pour obtenir de l’aide.

## Fonctionnement de la collecte de données régionale

La liste suivante décrit le processus de collecte de données utilisé par Adobe :

1. Le DNS résout automatiquement le nom d’hôte de la collecte à l’adresse IP du centre de collecte de données le plus proche du visiteur.
1. Le visiteur envoie les données à cet emplacement.
1. Les données sont immédiatement transférées au moyen d’une connexion sécurisée à un centre de traitement de données, où elles sont traitées et mises à la disposition des produits dans Adobe Experience Cloud.
