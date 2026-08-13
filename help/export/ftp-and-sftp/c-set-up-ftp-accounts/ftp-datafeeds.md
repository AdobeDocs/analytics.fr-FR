---
description: Les flux de données constituent un export des données de flux de clics reçues par Adobe, pour des flux de données standard et personnalisés.
keywords: ftp;sftp
title: Flux de données
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
TQID: 'https://experienceleague.adobe.com/JYiAXR-SbFNV3xQQ5Y1Qv10kVWpFJRWmuOvERcQ-zP4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 63%

---

# Flux de données

>[!NOTE]
>
>Les informations suivantes concernent les types de destinations FTP et SFTP. FTP et SFTP sont des types de destination hérités. Lors de la configuration d’un flux de données, vous devez utiliser un type de destination cloud , qui est plus sécurisé. Pour plus d’informations sur la configuration des types de destinations cloud pour un flux de données, voir [Créer un flux de données](/help/export/analytics-data-feed/create-feed.md).

Les flux de données constituent un export des données de flux de clics reçues par Adobe, pour des [flux de données](/help/export/analytics-data-feed/data-feed-overview.md) standard et personnalisés.

Si vous avez acheté Adobe Data Warehouse ou les [!UICONTROL flux de données standard], vous pouvez configurer vos propres flux de données Analytics. Ils peuvent être envoyés vers un compte FTP (configuré par Adobe ou un FTP externe). Les services d’ingénierie Adobe proposent des [!UICONTROL flux de données] personnalisés qui peuvent être envoyés par pratiquement n’importe quel moyen.

Les comptes FTP [!UICONTROL Flux de données] autorisent 10 Go (par défaut). Tous les autres comptes FTP standard sont par défaut limités à 50 Mo. Lorsque le compte FTP est utilisé aux fins prévues, il arrive que certains utilisateurs avec un trafic de données volumineux atteignent rapidement cette limite. Aucun fichier supplémentaire ne peut être transféré sur un compte FTP saturé. Par conséquent, les fichiers transitant par ce compte FTP ([!UICONTROL flux de données], demandes de l’entrepôt de données, etc.) ne sont plus distribués. C’est l’une des raisons pour lesquelles il est important de gérer votre compte FTP Adobe en supprimant les fichiers reçus et téléchargés.

Quand un compte FTP est saturé, téléchargez et supprimez les fichiers qui s’y trouvent, puis informez Adobe que l’espace a été libéré. Adobe peut alors renvoyer les fichiers qui n’ont pas été distribués. Avec certains outils, tels que l’entrepôt de données, les utilisateurs peuvent renvoyer eux-mêmes ces fichiers. L’implication d’Adobe n’est alors pas systématiquement nécessaire. Si votre compte FTP semble se remplir fréquemment, contactez l’assistance clientèle d’Adobe afin de proposer des alternatives de diffusion, notamment l’augmentation de l’espace FTP et du quota de numéros de fichier sur le compte.
