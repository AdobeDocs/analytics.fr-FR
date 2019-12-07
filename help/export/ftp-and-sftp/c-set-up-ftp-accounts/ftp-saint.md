---
description: L’option FTP (SAINT) des classifications offre davantage de flexibilité quant au transfert de jeux de données de classification volumineux, notamment la capacité de transférer des données dans plusieurs suites de rapports et de transférer des jeux de données de plus de 50 000 lignes.
keywords: ftp;sftp
title: Classifications
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Classifications

L’option FTP de classifications offre davantage de souplesse lors du transfert de jeux de données de classification volumineux, notamment la possibilité de télécharger des données dans plusieurs suites de rapports et des jeux de données de plus de 50 000 lignes.

Voir les [classifications](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) pour savoir comment télécharger des données de classification par FTP et comment transférer des fichiers de données par FTP (y compris la procédure à suivre pour créer un compte FTP).

Le temps requis par le système pour importer ces fichiers varie, selon un certain nombre de facteurs. Si, après six heures, un fichier transféré est toujours présent sur le serveur FTP, demandez aux personnes habilitées à le faire de contacter l’assistance clientèle d’Adobe.

Si l’importation est réussie, les modifications appropriées sont immédiatement répercutées dans une exportation, tandis qu’avec une importation de navigateur, il peut s’écouler jusqu’à quatre heures avant que les modifications de données dans Analytics ne soient répercutées et jusqu’à 24 heures avec une importation FTP.

Pour en savoir plus sur les limites FTP et la conservation des données, voir [Limites FTP et conservation des données](/help/export/ftp-and-sftp/ftp-limits.md).

## Fichier .fin pour les transferts de classifications et de sources de données {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. Il indique au système que le fichier de données a été entièrement transféré sur le compte FTP. The [!DNL .fin] file lets Adobe recognize that you are done with your import. Après l’avoir soumis, Adobe supprime les deux fichiers du FTP et commence à traiter l’importation.
Importer un fichier: [!DNL Classifications.tab]

Fichier de fin : [!DNL Classifications.fin]

If you upload your Data Sources or classification file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. Vous en êtes informé seulement si vous avez spécifié votre adresse électronique comme [!UICONTROL Destinataire de la notification] dans la fenêtre [!UICONTROL Créer un compte FTP] d’Analytics. Si ce champ ne contient aucune adresse électronique, aucune notification n’est envoyée.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. Si cette erreur survient, une notification est envoyée à l’adresse électronique indiquée dans le champ [!UICONTROL Destinataire de la notification] dans la fenêtre [!UICONTROL Créer un compte FTP]. Si ce champ ne contient aucune adresse électronique, aucune notification n’est envoyée.
