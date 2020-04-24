---
description: Utilisez Analytics pour créer et gérer des sources de données basées sur un FTP qui importent des données hors ligne ou historiques dans Experience Cloud au moyen du transfert de fichiers par FTP.
keywords: ftp;sftp
title: Sources de données
uuid: 41ba2de7-d33d-4394-b7d8-04a116f45419
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sources de données

Utilisez Analytics pour créer et gérer des sources de données basées sur un FTP qui importent des données hors ligne ou historiques dans Experience Cloud au moyen du transfert de fichiers par FTP.

Après avoir créé une instance Sources de données, l’outil fournit un emplacement FTP que vous pouvez utiliser pour télécharger les fichiers de sources de données. Une fois ces fichiers transférés, ils sont automatiquement localisés et traités. Une fois les fichiers traités, les données sont disponibles pour la création de rapports Analytics.

The [!UICONTROL Create] tab in the Data Sources Manager lets you configure a new Data Sources instance for the selected report suite. The [!UICONTROL Data Sources Wizard] guides you through the process of creating a Data Sources template, and creates an FTP location for uploading data.

In the [!UICONTROL Manage Data Sources] window, find your data source and select the FTP Info link. Vos informations de connexion FTP s’affichent dans la [!UICONTROL Activate a Data Source] fenêtre de la [!UICONTROL Upload/FTP Information] section.

Pour en savoir plus sur les limites FTP et la conservation des données, voir [Limites FTP et conservation des données](/help/export/ftp-and-sftp/ftp-limits.md).

## Fichier .fin pour les transferts de classifications et de sources de données {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. Ce fichier [!DNL .fin] est un fichier de finition. Il indique au système que le fichier de données a été entièrement transféré sur le compte FTP. Ce fichier [!DNL .fin] permet à Adobe de reconnaître quand l’importation est terminée. Après l’avoir soumis, Adobe supprime les deux fichiers du FTP et commence à traiter l’importation.
Importer un fichier : [!DNL Classifications.tab]

Fichier de fin : [!DNL Classifications.fin]

Si vous chargez le fichier de sources de données ou SAINT sans y joindre le fichier [!DNL .fin], il ne sera pas ajouté à la file d’attente de traitement par Adobe. Le fichier reste sur le FTP et n’est pas appliqué à vos données dans [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of reporting. Si ce champ ne contient aucune adresse électronique, aucune notification n’est envoyée.

Si vous chargez votre fichier avec un fichier [!DNL .fin], mais qu’il contient une erreur, il est envoyé pour traitement, mais l’erreur interrompt le traitement et place le fichier à envoyer dans un dossier d’erreur. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. Si ce champ ne contient aucune adresse électronique, aucune notification n’est envoyée.
