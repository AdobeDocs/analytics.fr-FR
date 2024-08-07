---
description: SFTP est un protocole sécurisé de transfert des données, grâce auquel personne d’autre que vous ne peut accéder à vos données. Adobe Engineering Services peut configurer un compte SFTP afin de conserver vos données de manière sécurisée.
keywords: ftp;sftp
title: Protocole de transfert de fichiers sécurisé - Aperçu
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 88%

---

# Protocole de transfert de fichiers sécurisé - Aperçu

SFTP est un protocole sécurisé de transfert de données qui garantit que personne d’autre que vous ne peut voir vos données. Adobe Engineering Services peut configurer un compte SFTP afin de conserver vos données de manière sécurisée.

## Livraison par émission (push)  {#section_A47831BB1DCA490BB57F0940617AA506}

Cela signifie que les serveurs d’Adobe « poussent » le fichier sur vos serveurs. Grosso modo, nous délivrons le fichier à votre point de terminaison.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) et le [flux de données Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=fr) peuvent transmettre les données par SFTP.

Le Report Builder **ne peut pas** transmettre des données par SFTP.

## Livraison par extraction (pull)  {#section_FA29FAEF02FE40B8B32452146A036F48}

Ceci signifie que le fichier est envoyé à l’un des serveurs Adobe par l’intermédiaire d’un protocole FTP standard. Pour récupérer le fichier sur votre serveur, vous devez l’extraire du serveur Adobe par SFTP de votre serveur vers le serveur FTP Adobe. Vous pouvez le faire de trois façons :

* [Connexion à Adobe via SFTP sans mot de passe.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Connexion à un compte FTP Adobe par SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Vous pouvez transmettre des rapports vers des flux de données/rapports et analyses/analyses ad hoc de type FTP Adobe, puis les extraire. Adobe ne peut pas livrer ces rapports au serveur SFTP que vous avez configuré.
