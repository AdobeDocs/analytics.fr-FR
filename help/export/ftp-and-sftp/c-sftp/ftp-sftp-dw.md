---
description: Adobe prend en charge l’exportation de requêtes Data Warehouse vers les serveurs SFTP.
keywords: ftp;sftp
title: Envoi de requêtes Data Warehouse vers les serveurs SFTP
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: d8bfad5d388f906c7c7301a9126813f5c2a5dbaa
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 52%

---

# Envoi de requêtes Data Warehouse vers les serveurs SFTP

Adobe prend en charge l’exportation de requêtes Data Warehouse vers des serveurs SFTP, comme décrit dans la section [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) de l’article [Configurer une destination de rapport pour une requête Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

Veillez à accomplir les tâches suivantes :

* Seul le port 22 est utilisé lors de la demande d’un rapport Data Warehouse.
* Le fichier `authorized_keys` d’Adobe se trouve dans le répertoire `.ssh` du répertoire racine de l’utilisateur avec lequel vous vous connectez.
* La destination ne figure pas sur `ftp.omniture.com`. Le protocole SFTP entre les serveurs internes d’Adobe n’est pas pris en charge.
* La destination prend en charge l’authentification à un facteur (PKI). S’il y a deux facteurs, le rapport ne sera pas remis. Vérifiez que le serveur n’est pas configuré pour une authentification à deux facteurs. Avec Adobe Analytics, seule cette clé est nécessaire pour se connecter.
* Adobe prend en charge le chiffrement SSHv2 et revient à SSHv1 (clé RSA seulement).

Pour envoyer une requête Data Warehouse par SFTP :

1. Suivez les étapes décrites dans [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) dans l’article, [Configuration d’une destination de rapport pour une requête Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), y compris le téléchargement de la clé publique.
1. Connectez-vous au site SFTP avec les mêmes informations d’identification que celles utilisées pour la requête Data Warehouse.
1. Dans le répertoire racine, naviguez jusqu’au dossier nommé `.ssh` (s’il n’existe pas, créez-le) et placez-y le fichier `authorized_keys`.

1. Complétez la requête Data Warehouse si vous ne l’avez pas déjà fait, comme décrit dans la section [ Configurer une destination de rapport pour une requête Data Warehouse ](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).
