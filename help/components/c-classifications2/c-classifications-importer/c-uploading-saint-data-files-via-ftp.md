---
description: Description de la procédure de téléchargement de fichiers de données via FTP.
seo-description: Description de la procédure de téléchargement de fichiers de données via FTP.
seo-title: Importation FTP
solution: Analytics
subtopic: Gestionnaire
title: Importation FTP
topic: Outils d’administration
uuid: a 914970 d-ba 02-4111-9 dcf -06448 f 71 b 9 f 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Importation FTP

Description de la procédure de téléchargement de fichiers de données via FTP.

## FTP import {#concept_2F965BE873254546A61FB755F25299FD}

Description de la procédure de téléchargement de fichiers de données via FTP.

**[!UICONTROL Admin]** &gt; **[!UICONTROL Importateur de classifications]**.

Les limites recommandées suivantes sont importantes :

* S’il y a beaucoup de petits fichiers, le traitement sera plus lent qu’avec quelques gros fichiers. Ceci est dû à la quantité de fichiers en file d’attente et à la hiérarchisation requise pour les tâches plus petites.
* Segmentez les fichiers volumineux par blocs de 50 Mo. Même si ce n’est pas obligatoire, ceci est recommandé car vous bénéficiez ainsi d’une meilleure visibilité sur la progression d’ensemble. Par ailleurs, en cas d’erreur pendant le traitement de la tâche, celle-ci est redémarrée, ce qui, selon ce scénario, génère une somme de travail à refaire considérable.

La configuration initiale remplit la base de données des classifications par un important jeu de données initiales ou restructure les classifications, plutôt que de reclasser quelques lignes ou d’en ajouter.

Après un premier chargement dans une suite de rapports (pour une variable ou un rapport donnés), Adobe recommande de ne charger que les lignes nouvelles et mises à jour lors des prochaines importations. Les lignes qui ne sont pas modifiées doivent être ignorées lors des chargements ultérieurs.

Chaque nouvelle valeur de clé chargée compte comme valeur unique de cette variable pour le mois.

Si vous avez dépassé les limites des valeurs uniques pour le mois, vous ne verrez pas les données de classifications correspondantes pour les valeurs dépassées dans les rapports. Ces classifications sont visibles dans Data Warehouse ou dans l’Ad Hoc Analysis.

>[!NOTE]
>
>Le temps nécessaire au traitement d'un fichier de données de classification varie selon la taille du fichier et le nombre actuel de fichiers en cours de traitement par les serveurs d'Adobe. En règle générale, le traitement des fichiers de données ne dure pas plus de 72 heures.

Avant de charger des données via FTP, vous devez créer un compte FTP. Pour plus d’informations, reportez-vous à la section [Créer un compte FTP](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importer des classifications via FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Description de la procédure d’utilisation d’un compte FTP pour importer des classifications dans Adobe Analytics.

Pour plus d’informations sur la création d’un compte FTP, consultez [Créer un compte FTP](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. Utilisez les informations d’accès FTP (Hôte, Identifiant, Mot de passe) pour accéder au serveur FTP à l’aide d’un client FTP de votre choix.
1. Upload the data file ( [!DNL .tab] or [!DNL .txt]) to the FTP server.
1. Une fois le fichier de données chargé, chargez un fichier FIN indiquant que le fichier est prêt pour le traitement.

   The FIN file is an empty file that has the same name as your data file, with a [!DNL .fin] filename extension. For example, if your data file is [!DNL classdata1.tab], the FIN filename is [!DNL classdata1.fin].

À intervalles réguliers, Adobe récupère les fichiers de données chargés auxquels un fichier FIN est associé. Adobe les importe ensuite dans les suites de rapports et dans les ensembles de données spécifiés dans la configuration du compte FTP.

## Créer un compte FTP {#task_C019268E6C934C7C95F4326F42A22CCF}

Avant de charger des données via FTP, vous devez créer un compte FTP. &gt;

<!-- 

t_create_an_ftp_account.xml

 -->

Voir [FTP et SFTP](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/) pour en savoir plus sur les serveurs FTP d’Adobe.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. Sous l'onglet **Importer un fichier**, cliquez sur **[!UICONTROL Ajouter nouveau]**.
1. Spécifiez les détails du compte FTP : 

   | Élément | Description |
   |---|---|
   | Nom | Nom du compte FTP. |
   | Données à classer | Dans la liste déroulante, sélectionnez le jeu de données (variable de rapport marketing) que vous souhaitez classer. |
   | Sélectionner des suites de rapports | Sélectionnez les suites de rapport dans lesquelles vous souhaitez classer le jeu de données sélectionné. Si vous voulez sélectionner plusieurs suites de rapports, les classifications de chaque suite sélectionnée doivent être identiques. |
   | Remplacer les données en cas de conflit | Sélectionnez cette option pour écraser les données en double. Elle s’avère utile lorsque vous mettez à jour des classifications existantes. Si vous ajoutez des classifications, cette option n’est pas recommandée. |
   | Au terme de l’importation | Sélectionnez cette option pour exporter automatiquement le jeu de données mis à jour vers le même compte FTP. Indiquez l’adresse de courriel à laquelle doivent être envoyées les notifications concernant ce compte FTP une fois l’importation terminée. |
   | Destinataire de la notification | Indiquez l’adresse de courriel à laquelle doivent être envoyées les notifications concernant ce compte FTP. |
   | Autoriser | (Obligatoire) Autorise Adobe à importer automatiquement tous les fichiers de données envoyés au nouveau compte FTP. |

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Une fois les comptes FTP créés, vous pouvez les modifier ou les supprimer en cliquant sur le lien correspondant en regard du compte FTP souhaité.
