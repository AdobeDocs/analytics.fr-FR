---
description: Les flux de données constituent une exportation des données de parcours de navigation reçues par Adobe, pour des flux de données standard et personnalisés.
keywords: ftp ; sftp
seo-description: Les flux de données constituent une exportation des données de parcours de navigation reçues par Adobe, pour des flux de données standard et personnalisés.
seo-title: Flux de données
solution: Analytics
title: Flux de données
uuid: 3 c 70 eea 3-ca 59-4 aa 5-9 b 11-64 e 1 bb 677 bfa
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Flux de données

Les flux de données sont une exportation des données de parcours de navigation reçues par Adobe, pour des [flux de données](/help/export/analytics-data-feed/c-getstarted/data-feed-overview.md) standard et personnalisés.

If you have purchased Adobe Data Warehouse, [!UICONTROL Standard Data Feeds] you can set up your own Analytics data feeds. Ils peuvent être envoyés vers un compte FTP (configuré par Adobe ou un FTP externe). Les services techniques Adobe Engineering Services proposent des [!UICONTROL flux de données] personnalisés qui peuvent être envoyés par n’importe quel moyen ou presque.

Les comptes FTP de [!UICONTROL flux de données] sont limités à 2 Go ou 63 fichiers (par défaut). Tous les autres comptes FTP standard sont par défaut limités à 50 Mo. Lorsque le compte FTP est utilisé aux fins prévues, il arrive que certains utilisateurs avec un trafic de données volumineux atteignent rapidement cette limite. Aucun fichier supplémentaire ne peut être transféré sur un compte FTP saturé. Par conséquent, les fichiers transitant par ce compte FTP ([!UICONTROL flux de données], demandes de l’entrepôt de données, etc.) ne sont plus distribués. Aussi est-il important de gérer votre compte FTP Adobe en supprimant les fichiers qui ont déjà été reçus et téléchargés.

Quand un compte FTP est saturé, téléchargez et supprimez les fichiers qui s’y trouvent, puis informez Adobe que l’espace a été libéré. Adobe peut alors renvoyer les fichiers qui n’ont pas été distribués. Avec certains outils, tels que l’entrepôt de données, les utilisateurs peuvent renvoyer eux-mêmes ces fichiers. L’implication d’Adobe n’est alors pas systématiquement nécessaire. Si votre compte FTP semble être fréquemment saturé, contactez l’assistance clientèle d’Adobe qui pourra alors vous suggérer d’autres solutions de distribution, notamment l’augmentation de l’espace FTP et du quota de fichiers autorisé sur ce compte.

Pour en savoir plus sur les limites FTP et la conservation des données, voir [Limites FTP et conservation des données](../../../export/ftp-and-sftp/ftp-limits.md#concept_8CAA1D8F27B3411AB902520AD6C9A70E).
