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

Après avoir créé une instance Sources de données, l’outil fournit un emplacement FTP que vous pouvez utiliser pour télécharger les fichiers de sources de données. Une fois ces fichiers transférés, l’instance Sources de données les localise et les traite automatiquement. Une fois les fichiers traités, les données sont disponibles pour la création de rapports Analytics.

Dans l’onglet [!UICONTROL Créer] du gestionnaire des sources de données, vous pouvez configurer une nouvelle instance de sources de données pour la suite de rapports sélectionnée. L’[!UICONTROL Assistant Sources de données] vous guide tout au long du processus de création d’un modèle de source de données, puis crée un emplacement FTP pour le transfert des données.

Dans la fenêtre [!UICONTROL Gérer les sources de données], recherchez votre source de données et cliquez sur le lien Infos FTP. Les informations de connexion FTP s’affichent dans la fenêtre [!UICONTROL Activer une source de données], sous la section [!UICONTROL Téléchargement / informations FTP].

Pour en savoir plus sur les limites FTP et la conservation des données, voir [Limites FTP et conservation des données](/help/export/ftp-and-sftp/ftp-limits.md).

## Fichier .fin pour les transferts de classifications et de sources de données {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. Il indique au système que le fichier de données a été entièrement transféré sur le compte FTP. The [!DNL .fin] file lets Adobe recognize that you are done with your import. Après l’avoir soumis, Adobe supprime les deux fichiers du FTP et commence à traiter l’importation.
Importer un fichier: [!DNL Classifications.tab]

Fichier de fin : [!DNL Classifications.fin]

If you upload your Data Sources or SAINT file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. Vous en êtes informé seulement si vous avez spécifié votre adresse électronique comme [!UICONTROL Destinataire de la notification] dans la fenêtre de création de rapports [!UICONTROL Créer un compte FTP]. Si ce champ ne contient aucune adresse électronique, aucune notification n’est envoyée.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. Si cette erreur survient, une notification est envoyée à l’adresse électronique indiquée dans le champ [!UICONTROL Destinataire de la notification] dans la fenêtre [!UICONTROL Créer un compte FTP]. Si ce champ ne contient aucune adresse électronique, aucune notification n’est envoyée.
