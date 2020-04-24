---
description: L’option FTP (SAINT) des classifications offre davantage de flexibilité quant au transfert de jeux de données de classification volumineux, notamment la capacité de transférer des données dans plusieurs suites de rapports et de transférer des jeux de données de plus de 50 000 lignes.
keywords: ftp;sftp
title: Classifications
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Classifications

L’option FTP des classifications offre davantage de flexibilité quant au transfert de jeux de données de classification volumineux, notamment la capacité de transférer des données dans plusieurs suites de rapports et de transférer des jeux de données de plus de 50 000 lignes.

Voir les [classifications](https://marketing.adobe.com/resources/help/fr_FR/reference/c_working_with_saint.html) pour savoir comment télécharger des données de classification par FTP et comment transférer des fichiers de données par FTP (y compris la procédure à suivre pour créer un compte FTP).

Le temps requis par le système pour importer ces fichiers varie, selon un certain nombre de facteurs. Si, après six heures, un fichier transféré est toujours présent sur le serveur FTP, demandez aux personnes habilitées à le faire de contacter l’assistance clientèle d’Adobe.

Si l’importation est réussie, les modifications appropriées sont immédiatement répercutées dans une exportation, tandis qu’avec une importation de navigateur, il peut s’écouler jusqu’à quatre heures avant que les modifications de données dans Analytics ne soient répercutées et jusqu’à 24 heures avec une importation FTP.

Pour en savoir plus sur les limites FTP et la conservation des données, voir [Limites FTP et conservation des données](/help/export/ftp-and-sftp/ftp-limits.md).

## Fichier .fin pour les transferts de classifications et de sources de données {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. Ce fichier [!DNL .fin] est un fichier de finition. Il indique au système que le fichier de données a été entièrement transféré sur le compte FTP. Ce fichier [!DNL .fin] permet à Adobe de reconnaître quand l’importation est terminée. Après l’avoir soumis, Adobe supprime les deux fichiers du FTP et commence à traiter l’importation.
Importer un fichier : [!DNL Classifications.tab]

Fichier de fin : [!DNL Classifications.fin]

Si vous chargez un fichier de source de données ou de classification sans y joindre le fichier [!DNL .fin], il ne sera pas ajouté à la file d’attente de traitement par Adobe. Le fichier reste sur le FTP et n’est pas appliqué à vos données dans [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of Analytics. Si ce champ ne contient aucune adresse électronique, aucune notification n’est envoyée.

Si vous chargez votre fichier avec un fichier [!DNL .fin], mais qu’il contient une erreur, il est envoyé pour traitement, mais l’erreur interrompt le traitement et place le fichier à envoyer dans un dossier d’erreur. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. Si ce champ ne contient aucune adresse électronique, aucune notification n’est envoyée.
