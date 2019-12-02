---
description: Les flux de données constituent une exportation des données de parcours de navigation reçues par Adobe, pour des flux de données standard et personnalisés.
keywords: ftp;sftp
solution: Analytics
title: Flux de données
uuid: 3c70eea3-ca59-4aa5-9b11-64e1bb677bfa
translation-type: tm+mt
source-git-commit: a52516c7746db399ff54a1a4880eeb7ee0ca66e1

---


# Flux de données

Les flux de données sont une exportation des données de parcours de navigation reçues par Adobe, pour des [flux de données](/help/export/analytics-data-feed/data-feed-overview.md) standard et personnalisés.

Si vous avez acheté Adobe Data Warehouse, vous pouvez configurer vos propres flux  de données Analytics. Ils peuvent être envoyés vers un compte FTP (configuré par Adobe ou un FTP externe). Les services techniques Adobe Engineering Services proposent des [!UICONTROL flux de données] personnalisés qui peuvent être envoyés par n’importe quel moyen ou presque.

Les comptes FTP de [!UICONTROL flux de données] sont limités à 2 Go ou 63 fichiers (par défaut). Tous les autres comptes FTP standard sont par défaut limités à 50 Mo. Lorsque le compte FTP est utilisé aux fins prévues, il arrive que certains utilisateurs avec un trafic de données volumineux atteignent rapidement cette limite. Aucun fichier supplémentaire ne peut être transféré sur un compte FTP saturé. Par conséquent, les fichiers transitant par ce compte FTP ([!UICONTROL flux de données], demandes de l’entrepôt de données, etc.) ne sont plus distribués. Aussi est-il important de gérer votre compte FTP Adobe en supprimant les fichiers qui ont déjà été reçus et téléchargés.

Quand un compte FTP est saturé, téléchargez et supprimez les fichiers qui s’y trouvent, puis informez Adobe que l’espace a été libéré. Adobe peut alors renvoyer les fichiers qui n’ont pas été distribués. Avec certains outils, tels que l’entrepôt de données, les utilisateurs peuvent renvoyer eux-mêmes ces fichiers. L’implication d’Adobe n’est alors pas systématiquement nécessaire. Si votre compte FTP semble être fréquemment saturé, contactez l’assistance clientèle d’Adobe qui pourra alors vous suggérer d’autres solutions de distribution, notamment l’augmentation de l’espace FTP et du quota de fichiers autorisé sur ce compte.
