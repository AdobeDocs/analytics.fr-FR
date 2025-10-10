---
title: API Bulk Data Insertion
description: L’API Bulk Data Insertion (BDIA) est une fonctionnalité d’Adobe Analytics qui vous permet de télécharger des données d’appels serveurs par lots de fichiers, au lieu d’utiliser des bibliothèques côté client telles qu’AppMeasurement.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 84%

---

# API Bulk Data Insertion

L’API Bulk Data Insertion résout plusieurs cas d’utilisation, tels que :

* Ingestion de données historiques provenant d’un système d’analyse antérieur

* Système interne de collecte d’analyses qui rend impossible l’utilisation d’AppMeasurement. Vous pouvez utiliser des processus dʼextraction, de transformation et de chargement (ETL) pour placer les données dans des fichiers de lot, puis utiliser BDIA pour les transférer vers Adobe Analytics.

* Collecte de données à partir dʼappareils ne disposant que dʼune connexion intermittente à Internet. En attente dʼune connexion, ces appareils stockeront les interactions. L’appareil peut ensuite charger les données en une seule fois via BDIA.

LʼAPI Data Insertion et lʼ[API Bulk Data Insertion](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) sont deux méthodes d’envoi de données de collecte côté serveur à Adobe Analytics. Les appels de l’API d’insertion de données sont effectués un événement à la fois. L’API d’insertion de données en bloc accepte les fichiers au format CSV contenant des données d’événement, un événement par ligne. Si vous travaillez sur une nouvelle implémentation de la collecte côté serveur, nous vous recommandons d’utiliser l’API d’insertion de données en bloc.
