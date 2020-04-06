---
description: Informations sur la façon dont Adobe fournit l’accès aux sources de données.
subtopic: Data sources
title: Fonctionnement des sources de données
topic: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Fonctionnement des sources de données

Informations sur la façon dont Adobe fournit l’accès aux sources de données.

>[!NOTE] Une fois envoyées par l’intermédiaire de la fonctionnalité Sources de données, les données importées ne peuvent plus être distinguées des données des rapports collectées à l’aide d’autres méthodes (balise JavaScript, ActionSource, API d’insertion de données, etc.). Vous ne pouvez pas supprimer les données une fois qu’elles ont été importées.

![](assets/data_sources_overview.png)

Deux méthodes sont disponibles pour envoyer des données :

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

Vous pouvez créer et gérer des sources de données FTP au moyen de rapports marketing ; le transfert de fichier FTP est alors mis à profit pour importer des fichiers de données dans la fonctionnalité Sources de données. Après avoir créé une source de données, Adobe vous fournit un emplacement FTP que vous pouvez utiliser pour transférer les fichiers de source de données. Une fois ces fichiers transférés, ils sont automatiquement localisés et traités. Une fois traitées, les données sont disponibles pour les rapports marketing.

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe  une API de sources de données  qui vous permet de lier par programmation vos applications à des sources de données. Cela évite la nécessité d’un serveur FTP intermédiaire et transfère les données via HTTP, SOAP et REST.

Voir Documentation [de l’API Sources de](https://github.com/AdobeDocs/analytics-1.4-apis/tree/master/docs/data-sources-api)données.
