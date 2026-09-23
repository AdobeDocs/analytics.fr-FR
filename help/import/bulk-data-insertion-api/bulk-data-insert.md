---
title: API Bulk Data Insertion
description: L’API Bulk Data Insertion (BDIA) est une fonctionnalité d’Adobe Analytics qui vous permet de télécharger des données d’appels serveurs par lots de fichiers, au lieu d’utiliser des bibliothèques côté client telles qu’AppMeasurement.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
TQID: 'https://experienceleague.adobe.com/TVa-LtTWKi6lQKGQKhH2bu5UcKsSJ2-KVqlfU5tQROQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f46a60da-b0b2-4ca3-bd91-271173f4123d
    internal-label: Data sources
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 53%
---
# API Bulk Data Insertion

L’API Bulk Data Insertion résout plusieurs cas d’utilisation, tels que :

* Ingestion de données historiques issues d’un ancien système analytics

* Système interne de collecte de données analytics qui rend impossible l’utilisation d’AppMeasurement. Vous pouvez utiliser des processus dʼextraction, de transformation et de chargement (ETL) pour placer les données dans des fichiers batch, puis utiliser BDIA pour les charger dans Adobe Analytics.

* Collecte de données à partir dʼappareils ne disposant que dʼune connexion intermittente à Internet. Ces appareils stockent les interactions dans l’attente d’une connexion. L’appareil peut ensuite charger les données en une seule fois via BDIA.

L’API Data Insertion et l’[API Bulk Data Insertion](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/) sont deux méthodes d’envoi de données de collecte côté serveur à Adobe Analytics. Les appels de l’API d’insertion de données sont effectués un événement à la fois. L’API Bulk Data Insertion accepte les fichiers au format CSV (valeurs séparées par des virgules) contenant des données d’événement, un événement par ligne. Si vous travaillez sur une nouvelle implémentation de la collecte côté serveur, Adobe recommande d’utiliser l’API Bulk Data Insertion.

Pour l’authentification, les points d’entrée, le format de fichier, la référence de colonne et la résolution des problèmes, consultez la documentation sur l’[API Bulk Data Insertion](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/) dans Adobe Developer.
