---
title: Collecte de données régionale
description: Informations sur la collecte des données régionales
translation-type: tm+mt
source-git-commit: 6d8f081d5ed86dfd6aeb0b68c5ae9624edb84b21

---


# Collecte de données régionale

Découvrez la collecte de données régionale et comment modifier votre réseau de collecte, si nécessaire.

Pour améliorer les performances de la collecte de données, tous les clients Adobe Experience Cloud ont été convertis en collecte de données régionale (RDC) afin que la collecte se déroule aussi près que possible de vos utilisateurs finaux. Cela améliore les performances de votre site/application et garantit que les données sont collectées le plus rapidement possible pour optimiser l’expérience de l’utilisateur final. Une fois que les données provenant des propriétés numériques sont collectées dans un centre de collecte de données, elles sont transférées au moyen d’une connexion sécurisée à un centre de traitement de données, où elles sont traitées et mises à la disposition des produits dans Adobe Experience Cloud. La collecte de données régionale est choisie par défaut pour les nouvelles implémentations depuis 2009.

La collecte de données régionale inclut les emplacements suivants (sujets à modification) :

## Collecte de données tierces

| Type de collecte de données régionale | Centres de collecte de données |
|---------------------|-------------------|
| Par défaut | San José, Virginie, Londres, Singapour, Hong Kong, Sydney, Amsterdam |

Note: If your Analytics image request is sent to the `2o7.net` or `omtdrc.net` endpoints, then you have third-party data collection. Vous pouvez le déterminer si vous voyez l’un des terminaux présents dans l’URL de vos requêtes.

## Collecte de données propriétaires

| Type de collecte de données régionale | Centres de collecte de données |
|---------------------|-------------------|
| Standard | San José, Virginie, Londres, Singapour |
| Toutes | Standard plus Hong Kong, Sydney, Amsterdam |
| Etats-Unis uniquement | San José, Virginie |
| UE uniquement | Londres, Amsterdam |
| Inde seulement | Mumbai |

## Fonctionnement de la collecte de données régionale

La liste suivante décrit le processus de collecte de données utilisé par Adobe :

1. Le DNS résout automatiquement le nom d’hôte de la collecte à l’adresse IP du centre de collecte de données le plus proche du visiteur.
1. Le visiteur envoie les données à cet emplacement.
1. Les données sont immédiatement transférées au moyen d’une connexion sécurisée à un centre de traitement de données, où elles sont traitées et mises à la disposition des produits dans Adobe Experience Cloud.

## Avantages de la collecte de données régionale

| Avantage | Description |
|---------|-----------|
| Performances | Avec la collecte de données régionale, vos visiteurs se connecteront au CC le plus proche. Ainsi, les temps de réponse sur votre page diminuent, ce qui entraîne un suivi plus précis et des temps de chargement plus courts. Vous trouverez des informations détaillées supplémentaires sur les temps de réponse dans la section Améliorations des performances liées à la collecte de données régionale. |
| Redondance | En cas d’interruption de la communication avec un CDC, la collecte de données est automatiquement acheminée vers le CC le plus proche afin d’assurer la continuité du service. |
| Redondance | Dans le cas d’une interruption de communication entre le centre de collecte de données et votre centre de traitement de données, l’infrastructure de collecte de données régionale d’Adobe enregistre les données localement, puis les transmet au centre de traitement de données lorsque les communications sont restaurées. |

## Historique des révisions de la documentation

| Mise à jour | Description |
|--------|---------|
| 20 février 2019 | Réécriture terminée. Ajout d’informations réseau de CRD. |
