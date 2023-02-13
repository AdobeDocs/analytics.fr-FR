---
title: Collecte de données régionales
description: Informations sur la collecte de données régionales
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: 60c2422ef32a4fadbb975006c111d12878a98f53
workflow-type: ht
source-wordcount: '510'
ht-degree: 100%

---

# Collecte de données régionales

Adobe Experience Cloud utilise la collecte de données régionales (RDC) afin que les interactions entre vos utilisateurs finaux et Adobe Experience Cloud se produisent le plus près possible de vos utilisateurs finaux. Cela améliore les performances du site ou de l’application et garantit que les données sont collectées le plus vite possible pour optimiser l’expérience de l’utilisateur final. Une fois que les données issues des propriétés numériques sont collectées au niveau régional dans un centre de collecte de données, elles sont transférées au moyen d’une connexion sécurisée à un centre de traitement de données, où elles sont traitées et mises à la disposition des produits dans Adobe Experience Cloud.

>[!IMPORTANT]
>
>Le package de composants additionnels de collecte de données régionales pour la Chine (RDC Chine, optimisation des performances en Chine) est un module complémentaire payant pour Adobe Analytics. Lʼoptimisation des performances dʼAdobe en Chine continentale permet aux clients ayant des utilisateurs à lʼintérieur de la Chine dʼenvoyer directement ces données aux serveurs de collecte de périphérie Adobe en Chine, plutôt quʼà dʼautres emplacements à lʼéchelle mondiale. Cela améliore le temps de chargement des pages et la précision des données par rapport à lʼenvoi de données à des nœuds situés en dehors de la Chine. Notez que les données sont finalement transférées vers l’un des centres de traitement de données d’Adobe en dehors de la Chine. Pour plus dʼinformations, contactez votre représentant commercial Adobe.

La collecte de données régionale inclut actuellement les emplacements suivants (sujets à modification) :

## Collecte de données tierces

| Type de collecte de données régionale | Centres de collecte de données |
|---------------------|-------------------|
| Par défaut | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney, Chine* |

*La collecte de données régionale pour la Chine nécessite le package de composants additionnels pour la Chine. Consultez la remarque « Important » ci-dessus.

>[!NOTE]
>
>Si votre demande dʼimage Analytics est envoyée aux points d’entrée `adobedc`, `2o7.net` ou `omtrdc.net`, vous disposez alors dʼune collecte de données tierces. Vous pouvez déterminer cela si l’un des points d’entrée apparaît dans l’URL de vos requêtes.

## Collecte de données propriétaires

| Type de collecte de données régionale | Centres de collecte de données |
|---------------------|-------------------|
| Mondiale (par défaut) | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney |
| Mondiale + Chine* | Chine*, Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney |
| Amériques uniquement | Oregon, Virginie |
| Europe uniquement | Irlande, Paris |
| Asie-Pacifique uniquement | Mumbai, Singapour, Tokyo, Sydney |
| Chine uniquement* | Pékin |

* Les types de collecte de données régionale Chine uniquement et Mondiale + Chine nécessitent le package de composants additionnels pour la Chine. Consultez la remarque « Important » ci-dessus. Mondiale + Chine acheminera les données provenant de lʼintérieur de la Chine vers notre nœud de périphérie pour la Chine, tandis que les données provenant de l’extérieur de la Chine seront acheminées vers le centre de collecte de données le plus proche à lʼextérieur de la Chine.

>[!NOTE]
>
>Experience Edge Global offre les meilleures performances pour vos utilisateurs finaux. Si vous souhaitez utiliser un autre type de collecte de données régionale, contactez lʼassistance clientèle dʼAdobe pour obtenir de lʼaide.

## Avantages de la collecte de données régionale

| Avantage | Description |
| --- | --- |
| Performances | Avec la collecte de données régionale, vos visiteurs se connectent au centre de collecte de données le plus proche. Cela permet de disposer du temps de réponse le plus rapide, ce qui autorise un suivi plus précis et des temps de chargement plus rapides. |
| Redondance | Dans le cas d’une interruption de communication entre le centre de collecte de données et votre centre de traitement de données, l’infrastructure de collecte de données régionale d’Adobe enregistre les données localement, puis les transmet au centre de traitement de données lorsque les communications sont restaurées. |

## Fonctionnement de la collecte de données régionale

La liste suivante décrit le processus de collecte de données utilisé par Adobe :

1. Le DNS résout automatiquement le nom d’hôte de la collecte à l’adresse IP du centre de collecte de données le plus proche du visiteur.
1. Le visiteur envoie les données à cet emplacement.
1. Les données sont immédiatement transférées au moyen d’une connexion sécurisée à un centre de traitement de données, où elles sont traitées et mises à la disposition des produits dans Adobe Experience Cloud.
