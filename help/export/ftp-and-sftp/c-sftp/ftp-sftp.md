---
description: SFTP est un protocole sécurisé de transfert des données, grâce auquel personne d’autre que vous ne peut accéder à vos données. Adobe Engineering Services peut configurer un compte SFTP afin de conserver vos données de manière sécurisée.
keywords: ftp;sftp
title: Protocole de transfert de fichiers sécurisé - Aperçu
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Protocole de transfert de fichiers sécurisé - Aperçu

SFTP est un protocole sécurisé de transfert des données, grâce auquel personne d’autre que vous ne peut accéder à vos données. Adobe Engineering Services peut configurer un compte SFTP afin de conserver vos données de manière sécurisée.

## Livraison par émission (push) {#section_A47831BB1DCA490BB57F0940617AA506}

Cela signifie que les serveurs d’Adobe « poussent » le fichier sur vos serveurs. Grosso modo, nous délivrons le fichier à votre point de terminaison.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) et le [flux de données Analytics](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html) peuvent transmettre les données par SFTP.

Les outils Analytics suivants **ne peuvent pas** transmettre les données par SFTP :

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## Livraison par extraction (pull) {#section_FA29FAEF02FE40B8B32452146A036F48}

Ceci signifie que le fichier est envoyé à l’un des serveurs Adobe par l’intermédiaire d’un protocole FTP standard. Pour récupérer le fichier sur votre serveur, vous devez l’extraire du serveur Adobe par SFTP de votre serveur vers le serveur FTP Adobe. Vous pouvez le faire de trois façons :

* [Connexion à Adobe via SFTP sans mot de passe.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Connexion à un compte FTP Adobe par SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Vous pouvez transmettre des rapports vers des flux de données/rapports et analyses/analyses ad hoc de type FTP Adobe, puis les extraire. Adobe ne peut pas livrer ces rapports au serveur SFTP que vous avez configuré.

