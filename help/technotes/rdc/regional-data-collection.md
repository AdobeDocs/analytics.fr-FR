---
title: Collecte de données régionales
description: Informations sur la collecte de données régionales
translation-type: tm+mt
source-git-commit: 91867f379c9f3e0f4e7fdeed572a94ff798653ba
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 94%

---


# Collecte de données régionales

Adobe Experience Cloud utilise la collecte de données régionales (RDC) afin que les interactions entre vos utilisateurs finaux et Adobe Experience Cloud se produisent le plus près possible de vos utilisateurs finaux. Cela améliore les performances du site ou de l’application et garantit que les données sont collectées le plus vite possible pour optimiser l’expérience de l’utilisateur final. Une fois que les données issues des propriétés numériques sont collectées au niveau régional dans un centre de collecte de données, elles sont transférées au moyen d’une connexion sécurisée à un centre de traitement de données, où elles sont traitées et mises à la disposition des produits dans Adobe Experience Cloud.

>[!IMPORTANT]
>
>Le module de Ajoute sur la collecte de données régionale pour la Chine (China Performance Optimization) est un module complémentaire facturable à Adobe Analytics. Veuillez contacter votre représentant commercial Adobe pour plus d&#39;informations.

La collecte de données régionale inclut les emplacements suivants (sujets à modification) :

## Collecte de données HTTP et tierces

| Type de collecte de données régionale | Centres de collecte de données |
|---------------------|-------------------|
| Par défaut | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney |

Remarque : si votre demande d’image Analytics est envoyée aux terminaux `2o7.net` ou `omtdrc.net`, vous disposez alors d’une collecte de données tierces. Vous pouvez le déterminer si vous voyez l’un des terminaux présents dans l’URL de vos requêtes.

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

## Avantages de la collecte de données régionale

| Avantage | Description |
|---------|-----------|
| Performances | Avec la collecte de données régionale, les visiteurs se connectent au centre de données le plus proche. Ainsi, les temps de réponse sur votre page diminuent (plus elle est basse, mieux c’est), ce qui entraîne un suivi plus précis et des temps de chargement plus courts. |
| Redondance | En cas d’interruption de communication avec un centre de collecte de données, la collecte de données est automatiquement acheminée vers le prochain centre le plus proche, ce qui assure la continuité du service. |
| Redondance | Dans le cas d’une interruption de communication entre le centre de collecte de données et votre centre de traitement de données, l’infrastructure de collecte de données régionale d’Adobe enregistre les données localement, puis les transmet au centre de traitement de données lorsque les communications sont restaurées. |

## Historique des révisions de la documentation

| Mise à jour | Description |
|--------|---------|
| 4 février 2020 | Mise à jour des emplacements RDC |
| 20 février 2019 | Fin de la réécriture. Ajout d’informations sur le réseau RDC. |
