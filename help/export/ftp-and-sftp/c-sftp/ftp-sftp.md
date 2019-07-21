---
description: SFTP est un protocole sécurisé de transfert des données qui permet à personne d'afficher vos données mais vous-même. Adobe Engineering Services peut configurer un compte SFTP pour conserver vos données de manière sécurisée.
keywords: ftp ; sftp
seo-description: SFTP est un protocole sécurisé de transfert des données qui permet à personne d'afficher vos données mais vous-même. Adobe Engineering Services peut configurer un compte SFTP pour conserver vos données de manière sécurisée.
seo-title: Protocole de transfert de fichiers sécurisé - aperçu
solution: Analytics
title: Protocole de transfert de fichiers sécurisé - aperçu
uuid: 7 dd 1 a 867-e 828-4 c 7 b-bf 11-75 a 81 d 4 c 149 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Protocole de transfert de fichiers sécurisé - aperçu

SFTP est un protocole sécurisé de transfert des données qui permet à personne d'afficher vos données mais vous-même. Adobe Engineering Services peut configurer un compte SFTP pour conserver vos données de manière sécurisée.

## Livraison par émission (push){#section_A47831BB1DCA490BB57F0940617AA506}

Cela signifie que les serveurs d’Adobe « poussent » le fichier sur vos serveurs. Grosso modo, nous délivrons le fichier à votre point de terminaison.

[L'entrepôt de données](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md#concept_904ADB7B4FE04DCCB90EFDB6D0DB1076) et [le flux de données Analytics](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) peuvent transmettre les données par SFTP.

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Créateur de rapports

## Livraison par extraction (pull){#section_FA29FAEF02FE40B8B32452146A036F48}

Ceci signifie que le fichier est envoyé à l’un des serveurs Adobe par l’intermédiaire d’un protocole FTP standard. Si vous souhaitez que le fichier sur votre serveur, vous devez l'extraire du serveur Adobe via SFTP de votre serveur vers le serveur FTP Adobe. Vous pouvez le faire de trois façons :

* [Connectez-vous à Adobe via SFTP sans mot de passe.](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846)
* [Connectez-vous à un compte FTP Adobe avec SFTP.](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md#concept_01176600188441C6AFB28F5E264D89F8)
* Vous pouvez transmettre des rapports vers des flux de données/rapports et analyses/analyses ad hoc de type FTP Adobe, puis les extraire. Adobe ne peut pas livrer ces rapports au serveur SFTP que vous avez configuré.

