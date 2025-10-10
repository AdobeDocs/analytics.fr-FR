---
description: Découvrez comment utiliser les flux de données pour extraire des données brutes d’Adobe Analytics. Découvrez les conditions préalables requises pour utiliser les flux de données. Que faire ensuite ?
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Présentation Du Flux De Données Analytics
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 79%

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
* [Contenu du flux de données ](c-df-contents/datafeeds-contents.md) : comprendre ce qui se trouve dans le <!-- Is this still the output users can download from the destination? I aske Jun. --> de fichiers compressés.
* [Définitions des colonnes de données](c-df-contents/datafeeds-reference.md) : une liste complète de l’ensemble des colonnes disponibles.

>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navigation dans l’interface du flux de données](https://video.tv.adobe.com/v/25452?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rechercher votre identifiant de flux de données](https://video.tv.adobe.com/v/335747?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]
