---
description: La politique FTP d’Adobe désactive automatiquement l’accès aux comptes FTP qui restent inactifs pendant 90 jours consécutifs.
keywords: ftp;sftp
title: Suppression de comptes et de données FTP et SFTP
feature: FTP Export
exl-id: accf2f8d-c22c-4684-ba85-73a286325d0c
TQID: https://experienceleague.adobe.com/7x8bYAZmZ4Bn-7Sbpf7wGFfOQbkxRQ2CsUcXUgVDTPQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 237
ht-degree: 8%

---

# Suppression de comptes et de données FTP et SFTP

La stratégie FTP et SFTP d’Adobe peut désactiver l’accès aux comptes FTP et SFTP qui restent inactifs pendant 90 jours consécutifs.

Adobe peut ensuite supprimer les comptes FTP et SFTP désactivés (et supprimer définitivement toutes les données stockées dans ces comptes) après une période de grâce supplémentaire de 90 jours. Par exemple, un compte SFTP qui reste inactif pendant 90 jours (du 5 juillet 2025 au 2 octobre 2025) est désactivé le 3 octobre 2025. Il est ensuite entièrement supprimé le 2 janvier 2026.

Aucun compte n’est désactivé avant le 5 octobre 2025 et aucun compte n’est supprimé avant le 2 janvier 2026.

Adobe peut également supprimer définitivement les anciennes données des comptes actifs si ces données n’ont pas été consultées depuis 90 jours.

Pour nous aider dans ce processus et nous assurer que l’environnement FTP ou SFTP continue à fournir un transfert de données sécurisé et fiable à nos clients, nous demandons à nos clients de procéder comme suit :

* Supprimez les données sortantes des systèmes FTP et SFTP une fois que ces données ont été transférées avec succès vers votre environnement interne. Adobe peut identifier et supprimer tous les fichiers restants sur le système après 90 jours.
* Avertissez Adobe lorsque les comptes FTP et SFTP ne sont plus nécessaires afin qu’ils puissent être désactivés et supprimés.
