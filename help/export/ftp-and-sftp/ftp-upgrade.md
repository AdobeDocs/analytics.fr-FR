---
description: Les mises à niveau vers les serveurs FTP Adobe peuvent introduire de nouvelles configurations qui affectent les scripts d’automatisation (souvent utilisés pour télécharger ou transférer régulièrement des données), qui dépendent généralement de paramètres de serveur particuliers.
keywords: ftp;sftp
title: Mise à niveau des serveurs FTP et SFTP Adobe
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
TQID: https://experienceleague.adobe.com/z19S-G-h4IHJkt4PNp-ajBapP3EYlo0TUtPSYqbhWJ8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 48%

---

# Mise à niveau des serveurs FTP et SFTP Adobe

Les mises à niveau vers les serveurs FTP et SFTP Adobe peuvent introduire de nouvelles configurations qui affectent les scripts d’automatisation (souvent utilisés pour télécharger ou charger régulièrement des données), qui dépendent souvent de paramètres de serveur particuliers.

Par exemple, un nouvel état de succès est introduit, affectant un script qui utilise l’état de réussite pour déclencher une certaine action. Adobe avertit les utilisateurs de telles modifications de configuration de manière proactive. Si Adobe vous informe qu’une mise à niveau du serveur FTP est imminente, vérifiez vos scripts d’automatisation pour vous assurer qu’ils fonctionnent toujours correctement.
