---
title: API Bulk Data Insertion
description: L’API Bulk Data Insertion (BDIA) est une fonctionnalité d’Adobe Analytics qui vous permet de charger des données d’appel au serveur par lots de fichiers au lieu d’utiliser des bibliothèques côté client telles qu’AppMeasurement. Les appels au serveur dans ces fichiers de lot peuvent être des données actives ou historiques. Il s’agit d’un successeur plus évolutif de l’API d’insertion de données dans les versions précédentes de l’API Adobe Analytics.
solution: Analytics
feature: API
source-git-commit: d8603ddd6cee2ccc930281003d9ff1befa15c95c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 27%

---


# API Bulk Data Insertion

L’insertion de données en bloc résout plusieurs cas d’utilisation, tels que :

* Ingestion de données historiques à partir d’un système d’analyse précédent

* Système de collecte d’analyses interne qui rend impossible l’utilisation d’AppMeasurement. Vous pouvez utiliser des processus ETL (Extract-Transform-Load) pour placer des données dans des fichiers de lot, puis utiliser BDIA pour les charger dans Adobe Analytics.

* Collecte de données à partir de périphériques qui n’ont qu’une connexion intermittente à Internet. Ces appareils stockent les interactions jusqu’à ce qu’ils reçoivent une connexion. L’appareil peut ensuite charger les données en une seule fois via BDIA.

API d’insertion de données et [API Bulk Data Insertion](https://www.adobe.io/apis/experiencecloud/analytics/docs.html?lang=fr#!AdobeDocs/analytics-2.0-apis/master/bdia.md)sont deux méthodes permettant d’envoyer des données de collecte côté serveur à Adobe Analytics. Les appels de l’API d’insertion de données sont effectués un événement à la fois. L’API d’insertion de données en bloc accepte les fichiers au format CSV contenant des données d’événement, un événement par ligne. Si vous travaillez sur une nouvelle implémentation de la collecte côté serveur, nous vous recommandons d’utiliser l’API d’insertion de données en bloc.