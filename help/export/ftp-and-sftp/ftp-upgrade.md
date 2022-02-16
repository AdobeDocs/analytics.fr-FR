---
description: Les mises à niveau vers les serveurs FTP Adobe peuvent introduire de nouvelles configurations qui affectent les scripts d’automatisation (souvent utilisés pour télécharger ou transférer régulièrement des données), qui dépendent généralement de paramètres de serveur particuliers.
keywords: ftp;sftp
title: Mettre à niveau les serveurs FTP Adobe
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 100%

---

# Mettre à niveau les serveurs FTP Adobe

Les mises à niveau vers les serveurs FTP Adobe peuvent introduire de nouvelles configurations qui affectent les scripts d’automatisation (souvent utilisés pour télécharger ou transférer régulièrement des données), qui dépendent généralement de paramètres de serveur particuliers.

Par exemple, un nouvel état de succès est introduit, affectant un script qui utilise l’état de réussite pour déclencher une certaine action. Adobe avertit les utilisateurs de telles modifications de configuration de manière proactive. Si Adobe vous informe qu’une mise à niveau de serveur FTP est imminente, vérifiez vos scripts d’automatisation afin de vous assurer qu’ils fonctionnent correctement.
