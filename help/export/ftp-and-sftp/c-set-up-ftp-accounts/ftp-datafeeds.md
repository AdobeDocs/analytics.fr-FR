---
description: Les flux de données constituent une exportation des données de parcours de navigation reçues par Adobe, pour des flux de données standard et personnalisés.
keywords: ftp;sftp
title: Flux de données
uuid: 3c70eea3-ca59-4aa5-9b11-64e1bb677bfa
translation-type: tm+mt
source-git-commit: fc14751c810019c5257a23a8a598b16f42ed10ee

---


# Flux de données

Les flux de données constituent une exportation des données de parcours de navigation reçues par Adobe, pour des [flux de données](/help/export/analytics-data-feed/data-feed-overview.md) standard et personnalisés.

If you have purchased Adobe Data Warehouse, [!UICONTROL Standard Data Feeds] you can set up your own Analytics data feeds. Ils peuvent être envoyés vers un compte FTP (configuré par Adobe ou un FTP externe). Adobe Engineering Services offers custom [!UICONTROL Data Feeds] that can be sent by virtually any means.

[!UICONTROL Data Feed]Les comptes FTP autorisent 10 Go (par défaut). Tous les autres comptes FTP standard sont par défaut limités à 50 Mo. Lorsque le compte FTP est utilisé aux fins prévues, il arrive que certains utilisateurs avec un trafic de données volumineux atteignent rapidement cette limite. Aucun fichier supplémentaire ne peut être transféré sur un compte FTP saturé. Therefore, any files being delivered to that FTP account ( [!UICONTROL Data Feeds], data warehouse requests, and so forth) are not delivered. Aussi est-il important de gérer votre compte FTP Adobe en supprimant les fichiers qui ont déjà été reçus et téléchargés.

Quand un compte FTP est saturé, téléchargez et supprimez les fichiers qui s’y trouvent, puis informez Adobe que l’espace a été libéré. Adobe peut alors renvoyer les fichiers qui n’ont pas été distribués. Avec certains outils, tels que l’entrepôt de données, les utilisateurs peuvent renvoyer eux-mêmes ces fichiers. L’implication d’Adobe n’est alors pas systématiquement nécessaire. Si votre compte FTP semble être fréquemment saturé, contactez l’assistance clientèle d’Adobe qui pourra alors vous suggérer d’autres solutions de distribution, notamment l’augmentation de l’espace FTP et du quota de fichiers autorisé sur ce compte.
