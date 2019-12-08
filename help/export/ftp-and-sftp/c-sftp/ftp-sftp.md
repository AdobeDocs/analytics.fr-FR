---
description: SFTP est un protocole sécurisé de transfert de données qui garantit que personne ne peut voir vos données sauf vous. Adobe Engineering Services peut configurer un compte SFTP pour conserver vos données en toute sécurité.
keywords: ftp;sftp
title: Protocole de transfert de fichiers sécurisé - Aperçu
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Protocole de transfert de fichiers sécurisé - Aperçu

SFTP est un protocole sécurisé de transfert de données qui garantit que personne ne peut voir vos données sauf vous. Adobe Engineering Services peut configurer un compte SFTP pour conserver vos données en toute sécurité.

## Livraison par émission (push){#section_A47831BB1DCA490BB57F0940617AA506}

Cela signifie que les serveurs d’Adobe « poussent » le fichier sur vos serveurs. Grosso modo, nous délivrons le fichier à votre point de terminaison.

[L’entrepôt](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) de données et le flux [de données](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) Analytics peuvent transmettre des données par SFTP.

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Créateur de rapports

## Livraison par extraction (pull){#section_FA29FAEF02FE40B8B32452146A036F48}

Ceci signifie que le fichier est envoyé à l’un des serveurs Adobe par l’intermédiaire d’un protocole FTP standard. Si vous souhaitez placer le fichier sur votre serveur, vous devez le retirer du serveur Adobe à l’aide de SFTP de votre serveur vers le serveur FTP d’Adobe. Vous pouvez le faire de trois façons :

* [Connexion à Adobe via SFTP sans mot de passe.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Connectez-vous à un compte FTP Adobe avec SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Vous pouvez transmettre des rapports vers des flux de données/rapports et analyses/analyses ad hoc de type FTP Adobe, puis les extraire. Adobe ne peut pas diffuser ces rapports sur le serveur SFTP que vous avez configuré.

