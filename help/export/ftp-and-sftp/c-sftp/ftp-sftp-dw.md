---
description: Adobe prend en charge l’exportation de requêtes Data Warehouse vers les serveurs SFTP.
keywords: ftp;sftp
title: Envoi de requêtes Data Warehouse vers les serveurs SFTP
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
TQID: 'https://experienceleague.adobe.com/gZvqhVFN2WKnk0hs2t8R5fcg5g8Tts1jKZPvMqeGcy4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 53%

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
