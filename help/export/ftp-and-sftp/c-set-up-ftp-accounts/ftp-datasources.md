---
description: Utilisez Analytics pour créer et gérer des sources de données basées sur un FTP qui importent des données hors ligne ou historiques dans Experience Cloud au moyen du transfert de fichiers par FTP.
keywords: ftp;sftp
title: Sources de données
uuid: 41ba2de7-d33d-4394-b7d8-04a116f45419
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sources de données

Utilisez Analytics pour créer et gérer des sources de données basées sur un FTP qui importent des données hors ligne ou historiques dans Experience Cloud au moyen du transfert de fichiers par FTP.

Après avoir créé une instance Sources de données, l’outil fournit un emplacement FTP que vous pouvez utiliser pour télécharger les fichiers de sources de données. Une fois ces fichiers transférés, l’instance Sources de données les localise et les traite automatiquement. Une fois les fichiers traités, les données sont disponibles pour la création de rapports Analytics.

Dans l’onglet [!UICONTROL Créer] du gestionnaire des sources de données, vous pouvez configurer une nouvelle instance de sources de données pour la suite de rapports sélectionnée. L’[!UICONTROL Assistant Sources de données] vous guide tout au long du processus de création d’un modèle de source de données, puis crée un emplacement FTP pour le transfert des données.

Dans la fenêtre [!UICONTROL Gérer les sources de données], recherchez votre source de données et cliquez sur le lien Infos FTP. Les informations de connexion FTP s’affichent dans la fenêtre [!UICONTROL Activer une source de données], sous la section [!UICONTROL Téléchargement / informations FTP].

Pour en savoir plus sur les limites FTP et la conservation des données, voir [Limites FTP et conservation des données](/help/export/ftp-and-sftp/ftp-limits.md).

## Fichier .fin pour les transferts de classifications et de sources de données {#section_1484719F8A134EAE91212DBD8F15174F}

Lorsque vous transférez un fichier de classifications ou de [!UICONTROL source de données] ([!DNL .tab] ou [!DNL .txt]), vous devez également transférer un fichier vide portant le même nom que le fichier de données importé, mais avec une extension [!DNL .fin]. Ce fichier [!DNL .fin] est un fichier de finition. Il indique au système que le fichier de données a été entièrement transféré sur le compte FTP. Ce fichier [!DNL .fin] permet à Adobe de reconnaître quand l’importation est terminée. Après l’avoir soumis, Adobe supprime les deux fichiers du FTP et commence à traiter l’importation.
Importer un fichier : [!DNL Classifications.tab]

Fichier de fin : [!DNL Classifications.fin]

Si vous chargez le fichier de sources de données ou SAINT sans y joindre le fichier [!DNL .fin], il ne sera pas ajouté à la file d’attente de traitement par Adobe. Le fichier reste sur le FTP et n’est pas appliqué à vos données dans [!UICONTROL Experience Cloud]. Vous en êtes informé seulement si vous avez spécifié votre adresse électronique comme [!UICONTROL Destinataire de la notification] dans la fenêtre de création de rapports [!UICONTROL Créer un compte FTP]. Si ce champ ne contient aucune adresse électronique, aucune notification n’est envoyée.

Si vous chargez votre fichier avec un fichier [!DNL .fin], mais qu’il contient une erreur, il est envoyé pour traitement, mais l’erreur interrompt le traitement et place le fichier à envoyer dans un dossier d’erreur. Si cette erreur survient, une notification est envoyée à l’adresse électronique indiquée dans le champ [!UICONTROL Destinataire de la notification] dans la fenêtre [!UICONTROL Créer un compte FTP]. Si ce champ ne contient aucune adresse électronique, aucune notification n’est envoyée.
