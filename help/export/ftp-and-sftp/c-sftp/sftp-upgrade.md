---
title: Mise à niveau des services SFTP - FAQ
description: Questions fréquentes sur la mise à niveau prévue des services SFTP en mai 2022.
source-git-commit: eb9bdcbd99d45afc913c5ade37e8fb5c62a3a456
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 2%

---


# Mise à niveau des services SFTP - FAQ

Activé **2 mai 2022**, Adobe Analytics mettra à niveau son protocole de transfert de fichiers sécurisé. [SFTP] afin de fournir une sécurité améliorée pour les transferts de fichiers. Avec cette modification, certaines configurations de client SFTP ne seront plus prises en charge. Nous ajouterons également quelques options de connexion disponibles par **1 mars 2022**. Cela aura uniquement un impact sur les données envoyées à ou récupérées à partir d’Adobe Analytics par SFTP. Le protocole FTP ne sera pas affecté. Afin d’éviter les interruptions de service, veillez à ce que vos clients SFTP (code, outils, services) soient conformes aux modifications présentées ci-dessous.

## Comment puis-je déterminer les algorithmes, les types de connexions et les protocoles actuellement utilisés par mon entreprise ?

Le logiciel FTP/SFTP que vous utilisez doit indiquer les paramètres spécifiques utilisés dans les connexions que vous avez configurées pour échanger des données avec Adobe Analytics. Ce logiciel doit également inclure la documentation sur les différentes options disponibles pour les connexions. Les options qui seront prises en charge après cette mise à jour sont largement prises en charge et acceptées par le secteur.

## Quelles fonctionnalités Adobe Analytics utilisent le protocole SFTP pour l’ingestion de données ?

Les fonctionnalités suivantes offrent une option pour télécharger des données vers Adobe Analytics par SFTP.

* [Classifications](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html)

* [Flux de données](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html)

* [Sources de données](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html)

* [Rapports distribués sur l’Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html)

* En outre, certaines implémentations personnalisées créées par [Services d’ingénierie](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html) peut utiliser le protocole SFTP pour échanger des données avec Adobe.

## Quelles modifications spécifiques seront incluses dans cette mise à jour ?

Vous trouverez ci-dessous une liste détaillée des connexions et algorithmes qui seront supprimés et qui seront pris en charge :

* Algorithmes Mac du protocole SFTP :

   * Nous ne prendrons plus en charge : hmac-md5, hmac-md5-96, hmac-ripemd160, hmacripemd160@openssh.com, hmac-sha1, hmac-sha1-96, hmac-sha1-etm@openssh.com, umac-64-etm@openssh.com, umac-64@openssh.com

   * Nous ne prendrons en charge que les éléments suivants : hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, hmac-sha2-512, hmacsha2-256, umac-128@openssh.com

* Algorithme de chiffrement de protocole SFTP :

   * Nous ne prendrons plus en charge : 3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se

   * Nous ne prendrons en charge que les éléments suivants : aes128-ctr, aes192-ctr, aes256-ctr

* Le protocole SFTP prend en charge les connexions :

   * Nous ne prendrons plus en charge l’utilisation des commandes scp et rsync ou des connexions via le protocole sftp

   * Nous ne prendrons en charge que les connexions au protocole SFTP pur.

* Clients/protocoles FTP/SFTP pris en charge :

   * FTP : vsftpd version 3.0.2-25 ou ultérieure

   * SFTP : openssh version 7.4p1-21 ou ultérieure