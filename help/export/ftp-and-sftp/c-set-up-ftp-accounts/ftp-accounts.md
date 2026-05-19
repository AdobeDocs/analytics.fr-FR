---
description: Configurez et utilisez des comptes FTP hébergés par Adobe.
keywords: ftp;sftp
title: Configuration de comptes FTP - Aperçu
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
TQID: https://experienceleague.adobe.com/38oslnk-IS87YU9qpOJyEoqytnrMuK5lp3VtYnTyQOg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 14%

---

# Configuration de comptes FTP ou SFTP - Présentation

Configurez et utilisez des comptes FTP ou SFTP hébergés par Adobe.

Adobe conserve des clusters FTP ou SFTP haute disponibilité et hautes performances spécialement conçus pour améliorer la fiabilité du transfert de fichiers tout en continuant à garantir des performances élevées.

Les clients d’Adobe reçoivent des notifications de maintenance par le biais de leur processus standard, en fonction des événements de maintenance programmés. Pour vous assurer que les systèmes FTP ou SFTP Adobe fonctionnent comme prévu et continuent à fournir un transfert de données sécurisé et fiable et haute performance, Adobe demande à respecter les instructions suivantes :

* La plupart des comptes FTP ou SFTP Adobe (classifications, sources de données et autres) sont activés automatiquement lorsque la fonctionnalité donnée est configurée. Pour les comptes de flux de données et de diffusion de fichiers généraux, l’assistance clientèle d’Adobe peut configurer un nouveau compte FTP ou SFTP pour vous. Ce processus permet de garantir la sécurité et l’espace disponible pour le compte FTP ou SFTP.
* Les utilisateurs doivent supprimer les données diffusées par Adobe sur le compte FTP ou SFTP une fois que les données ont été transférées correctement vers leurs systèmes.
* Avertissez Adobe lorsque les comptes FTP ou SFTP ne sont plus nécessaires afin qu’ils puissent être désactivés.

L’hôte FTP Adobe se nomme `ftp://ftp.omniture.com` ou `ftp://ftp2.omniture.com`.

Ces informations, ainsi qu’un nom d’utilisateur et un mot de passe, doivent être fournis soit dans CX Enterprise (pour les classifications et les sources de données), soit par le représentant Adobe chargé de la configuration du compte, à votre demande. Si vous ne savez pas quelle adresse FTP ou SFTP utiliser, contactez l’équipe chargée de votre compte Adobe, qui pourra vous fournir l’adresse appropriée. En outre, pour les comptes de classifications et de sources de données, Adobe n’a pas d’heure spécifique dans la journée pour le traitement des fichiers FTP ou SFTP. Adobe utilise plutôt un script qui interroge en permanence les comptes FTP ou SFTP pour le traitement des nouveaux fichiers. Les fichiers chargés dans ces comptes sont traités aussi rapidement que possible.
