---
title: Mise à niveau des services SFTP - FAQ
description: Questions fréquentes sur la mise à niveau des services SFTP prévue.
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 100%

---

# Mise à niveau des services SFTP - FAQ

Le 20 septembre 2022, Adobe Analytics procédera à la mise à niveau de ses services [SFTP] (Secure File Transfer Protocol) afin de fournir une sécurité accrue lors des transferts de fichiers. Suite à la mise à niveau, certaines configurations de clients SFTP ne seront plus prises en charge. Cela n’affecte que les données envoyées ou récupérées depuis Adobe Analytics au moyen du protocole SFTP. Le protocole FTP ne sera pas affecté. Pour éviter toute interruption de service, assurez-vous que vos clients SFTP (code, outils, services) sont compatibles avec les modifications détaillées ci-dessous.

## Comment puis-je connaître les algorithmes, les types de connexion et les protocoles actuellement utilisés par mon organisation ?

Le logiciel FTP/SFTP que vous utilisez doit indiquer les paramètres spécifiques utilisés dans les connexions qui ont été configurées pour échanger des données avec Adobe Analytics. Ce logiciel doit également inclure la documentation sur les différentes options disponibles pour les connexions. Les options qui seront prises en charge après cette mise à jour sont couramment utilisées et acceptées dans le secteur.

Les options de connexion qui seront supprimées sont généralement considérées comme obsolètes et non utilisées dans les logiciels actuels. Si vous avez mis à niveau votre logiciel FTP/SFTP au cours des trois dernières années, vous disposez probablement déjà d’une connexion conforme.

## Quelles fonctionnalités Adobe Analytics utilisent le protocole SFTP pour l’ingestion de données ?

Les fonctionnalités suivantes offrent une option pour télécharger des données vers Adobe Analytics au moyen du protocole SFTP.

* [Classifications](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)

* [Attributs du client](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=fr)

* [Flux de données](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)

* [Sources de données](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)

* [Rapports distribués sur Data Warehouse](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)

* En outre, certaines implémentations personnalisées créées par les [Services d’ingénierie](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md) peuvent utiliser le protocole SFTP pour échanger des données avec Adobe.

## Quelles modifications spécifiques seront incluses dans cette mise à jour ?

Consultez ci-dessous une liste détaillée des connexions et algorithmes qui seront supprimés et ceux qui seront pris en charge :

* Algorithmes MAC pour le protocole SFTP :

   * Fin de la prise en charge des algorithmes suivants : hmac-md5, hmac-md5-96, hmac-ripemd160, hmacripemd160@openssh.com, hmac-sha1, hmac-sha1-96, hmac-sha1-etm@openssh.com, umac-64-etm@openssh.com, umac-64@openssh.com.

   * Seuls les algorithmes suivants seront pris en charge : hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, hmac-sha2-512, hmacsha2-256, umac-128@openssh.com.

* Algorithme de chiffrement pour le protocole SFTP :

   * Fin de la prise en charge des algorithmes suivants : 3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se.

   * Seuls les algorithmes suivants seront pris en charge : aes128-ctr, aes192-ctr, aes256-ctr.

* Connexions prises en charge par le protocole SFTP :

   * Nous nʼassurerons plus la prise en charge de l’utilisation des commandes scp et rsync ou des connexions au moyen du protocole SFTP.

   * Nous ne prendrons en charge que les connexions au moyen du protocole SFTP pur.

* Clients/protocoles FTP/SFTP pris en charge :

   * FTP : vsftpd version 3.0.2-25 ou ultérieure.

   * SFTP : openssh version 7.4p1-21 ou ultérieure.
