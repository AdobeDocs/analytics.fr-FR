---
title: Collecte de données régionales
description: Informations sur la collecte de données régionales
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: f75d123c93d446776492dd933d03d32c2496fa69
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 36%

---

# Collecte de données régionales

Adobe Experience Cloud utilise la collecte de données régionale (RDC) afin que les interactions entre vos visiteurs et votre Adobe se produisent aussi près que possible de vos visiteurs. Une fois les données collectées à l’échelle régionale dans un centre de collecte de données, elles sont transférées au moyen d’une connexion sécurisée à un centre de traitement de données. Après le traitement, les données sont disponibles pour les produits dans Adobe Experience Cloud. Pour modifier votre type de collecte de données régionale, contactez l’assistance clientèle d’Adobe.

Le processus de collecte de données régionale suit les étapes suivantes :

1. Le DNS résout automatiquement le nom d’hôte de la collecte sur l’adresse IP du centre de collecte de données le plus proche du visiteur.
1. Le visiteur envoie les données à cet emplacement.
1. Les données sont immédiatement transférées au moyen d’une connexion sécurisée à un centre de traitement de données, où elles sont traitées et mises à la disposition des produits dans Adobe Experience Cloud.

L’utilisation de la collecte de données régionale présente plusieurs avantages :

* **Performances**: Avec la collecte de données régionale, vos visiteurs se connectent au centre de collecte de données le plus proche. Cette optimisation fournit le temps de réponse le plus rapide, ce qui se traduit par un suivi plus précis et des temps de chargement plus rapides.
* **Redondance**: En cas d’interruption de communication entre le centre de collecte de données et votre centre de traitement des données, l’infrastructure de collecte de données régionale de l’Adobe enregistre les données localement, puis les transfère au centre de traitement des données lorsque les communications sont restaurées.

La collecte de données régionale inclut actuellement les emplacements suivants (sujets à modification) :

## Collecte de données tierces

| Type de collecte de données régionale | Centres de collecte de données |
| --- | --- |
| Par défaut | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney, Chine* |

{style="table-layout:auto"}

*La collecte de données régionale pour la Chine nécessite le package de composants additionnels pour la Chine. Voir [Optimisation des performances en Chine](#china-performance-optimization) ci-dessous.

>[!NOTE]
>
>Si votre demande dʼimage Analytics est envoyée aux points d’entrée `adobedc.net`, `2o7.net` ou `omtrdc.net`, vous disposez alors dʼune collecte de données tierces. Vous pouvez déterminer cela si l’un des points d’entrée apparaît dans l’URL de vos requêtes.

## Collecte de données propriétaires

| Type de collecte de données régionale | Centres de collecte de données |
| --- | --- |
| Mondiale (par défaut) | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney |
| Mondiale + Chine* | Chine*, Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney |
| Amériques uniquement | Oregon, Virginie |
| Europe uniquement | Irlande, Paris |
| Asie-Pacifique uniquement | Mumbai, Singapour, Tokyo, Sydney |
| Chine uniquement* | Pékin |

{style="table-layout:auto"}

* Les types de collecte de données régionale Chine uniquement et Mondiale + Chine nécessitent le package de composants additionnels pour la Chine. Global + Chine achemine les données en provenance de Chine vers la RDC Chine de l’Adobe tout en acheminant les données provenant de l’extérieur de la Chine vers la RDC la plus proche en dehors de la Chine. Voir [Optimisation des performances en Chine](#china-performance-optimization) ci-dessous.

## Optimisation des performances en Chine

Le module complémentaire RDC Chine (China Performance Optimization) est un module complémentaire payant d’Adobe Analytics. L’optimisation des performances d’Adobe en Chine continentale permet aux clients ayant des utilisateurs en Chine d’envoyer ces données directement vers les serveurs de collecte de données d’Adobe en Chine plutôt qu’ailleurs dans le monde. Cette optimisation améliore les temps de chargement des pages et la précision des données par rapport à l’envoi de données à des emplacements en dehors de la Chine. Les données sont finalement transférées vers l’un des centres de traitement de données (DPC) d’Adobe en dehors de la Chine. Pour plus d’informations, contactez votre représentant commercial d’Adobe.

>[!NOTE]
>
>Le module complémentaire RDC pour la Chine n’est pas pris en charge pour la variable [SDK Web](/help/implement/aep-edge/overview.md).

