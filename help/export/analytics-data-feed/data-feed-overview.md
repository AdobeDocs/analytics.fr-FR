---
description: Découvrez comment utiliser les flux de données pour extraire des données brutes d’Adobe Analytics. Découvrez les conditions préalables requises afin d’utiliser les flux de données pour les étapes suivantes.
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Flux de données Analytics - Vue d’ensemble
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
TQID: 'https://experienceleague.adobe.com/XVFQdMEfIM7lQlnU3b-zRbQ9-RliqtaBjr-7ptxkI1o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: ede9f3ba-4ee4-4497-9d8e-e9da5848bda0
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 335
ht-degree: 95%

---

# Flux de données Analytics - Aperçu

Les flux de données sont un moyen puissant d’extraire des données brutes d’Adobe Analytics. Il est possible d’utiliser ces données brutes sur d’autres plateformes en dehors d’Adobe à la discrétion de votre entreprise. Les données sont diffusées sous la forme de lots horaires à la fin de chaque heure ou sous la forme de lots quotidiens à la fin de chaque jour.

## Conditions préalables

Assurez-vous de respecter l’ensemble des exigences suivantes avant d’utiliser les flux de données.

* Une implémentation opérationnelle qui envoie des données vers les serveurs de collecte de données Adobe. Consultez la section [Valider et publier une implémentation](/help/implement/launch/validate-publish-prod.md) dans le guide de l’implémentation.
* Votre compte est un compte administrateur produit Analytics ou il appartient à un profil produit ayant accès aux flux de données.
* Un compartiment configuré sur Amazon S3, Google Cloud Platform, Azure RBAC ou Azure SAS.
* (Hérité : requis uniquement pour les types de destination FTP et SFTP hérités) Veillez à disposer d’un site FTP et d’informations d’identification (informations d’identification FTP fournies par votre organisation).

## Étapes suivantes

Les ressources suivantes vous aident à comprendre le workflow de base de l’obtention des flux de données. Une fois que vous avez compris le workflow de base, vous pouvez travailler avec des équipes au sein de votre organisation pour stocker ou ingérer des données brutes dans une base de données.

* [Bonnes pratiques relatives aux flux de données](/help/export/analytics-data-feed/data-feeds-best-practices.md) : bonnes pratiques pour la création et la gestion des flux de données.
* [Créer un flux de données](create-feed.md) : informations techniques relatives à la création d’un flux de données, expliquant les champs individuels de manière plus détaillée
* [Gérer les flux de données](df-manage-feeds.md) : découvrez-en plus sur la navigation dans l’interface des flux de données
* [Contenu du flux de données](c-df-contents/datafeeds-contents.md) : comprendre ce qui se trouve dans le fichier compressé <!-- Is this still the output users can download from the destination? I aske Jun. -->.
* [Définitions des colonnes de données](c-df-contents/datafeeds-reference.md) : une liste complète de l’ensemble des colonnes disponibles.

>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navigation dans l’interface du flux de données](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/exporting/data-feeds/data-feeds-management-ui){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rechercher votre identifiant de flux de données](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/exporting/data-feeds/find-your-data-feed-id){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]
