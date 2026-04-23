---
description: Les mises à niveau vers les serveurs FTP Adobe peuvent introduire de nouvelles configurations qui affectent les scripts d’automatisation (souvent utilisés pour télécharger ou transférer régulièrement des données), qui dépendent généralement de paramètres de serveur particuliers.
keywords: ftp;sftp
title: Mise à niveau des serveurs FTP et SFTP Adobe
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
source-git-commit: 6008cd51b86e403668c15bbfb9d50513e46ddf4d
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 47%

---

# Mise à niveau des serveurs FTP et SFTP Adobe

Les mises à niveau vers les serveurs FTP et SFTP Adobe peuvent introduire de nouvelles configurations qui affectent les scripts d’automatisation (souvent utilisés pour télécharger ou charger régulièrement des données), qui dépendent souvent de paramètres de serveur particuliers.

Par exemple, un nouvel état de succès est introduit, affectant un script qui utilise l’état de réussite pour déclencher une certaine action. Adobe avertit les utilisateurs de telles modifications de configuration de manière proactive. Si Adobe vous informe qu’une mise à niveau du serveur FTP est imminente, vérifiez vos scripts d’automatisation pour vous assurer qu’ils fonctionnent toujours correctement.
