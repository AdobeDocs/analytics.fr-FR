---
description: Description de la procédure de téléchargement de fichiers de données via FTP.
subtopic: Classifications
title: Importation FTP
topic: Admin tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Importation FTP

Description de la procédure de téléchargement de fichiers de données via FTP.

## Importation FTP {#concept_2F965BE873254546A61FB755F25299FD}

Description de la procédure de téléchargement de fichiers de données via FTP.

**[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.

Les limites recommandées suivantes sont importantes :

* S’il y a beaucoup de petits fichiers, le traitement sera plus lent qu’avec quelques gros fichiers. Ceci est dû à la quantité de fichiers en file d’attente et à la hiérarchisation requise pour les tâches plus petites.
* Segmentez les fichiers volumineux par blocs de 50 Mo. Même si ce n’est pas obligatoire, ceci est recommandé car vous bénéficiez ainsi d’une meilleure visibilité sur la progression d’ensemble. Par ailleurs, en cas d’erreur pendant le traitement de la tâche, celle-ci est redémarrée, ce qui, selon ce scénario, génère une somme de travail à refaire considérable.

La configuration initiale remplit la base de données des classifications par un important jeu de données initiales ou restructure les classifications, plutôt que de reclasser quelques lignes ou d’en ajouter.

Après un premier chargement dans une suite de rapports (pour une variable ou un rapport donnés), Adobe recommande de ne charger que les lignes nouvelles et mises à jour lors des prochaines importations. Les lignes qui ne sont pas modifiées doivent être ignorées lors des chargements ultérieurs.

Chaque nouvelle valeur de clé chargée compte comme valeur unique de cette variable pour le mois.

Si vous avez dépassé les limites des valeurs uniques pour le mois, vous ne verrez pas les données de classifications correspondantes pour les valeurs dépassées dans les rapports. Ces classifications sont visibles dans Data Warehouse ou dans l’Ad Hoc Analysis.

> [!NOTE] Le temps nécessaire au traitement d’un fichier de données de classification varie selon la taille du fichier et le nombre de fichiers en cours de traitement par les serveurs d’Adobe. En règle générale, le traitement des fichiers de données ne dure pas plus de 72 heures.

Avant de charger des données via FTP, vous devez créer un compte FTP. Pour plus d’informations, voir [Créer un compte FTP](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importer des classifications via FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Description de la procédure d’utilisation d’un compte FTP pour importer des classifications dans Adobe Analytics.

Pour plus d’informations sur la création d’un compte FTP, consultez  [Créer un compte FTP](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
1. Cliquez sur **[!UICONTROL Importer un fichier]**, puis sur **[!UICONTROL Importation FTP]**.
1. Cliquez sur **[!UICONTROL Afficher]** en regard du compte FTP à utiliser.
1. Utilisez les informations d’accès FTP (Hôte, Identifiant, Mot de passe) pour accéder au serveur FTP à l’aide d’un client FTP de votre choix.
1. Chargez le fichier de données ([!DNL .tab] ou [!DNL .txt]) sur le serveur FTP.
1. Une fois le fichier de données chargé, chargez un fichier FIN indiquant que le fichier est prêt pour le traitement.

   Le fichier FIN est un fichier vide qui porte le même nom que votre fichier de données et qui est doté de l’extension de fichier [!DNL .fin]. Par exemple, si votre fichier de données se nomme [!DNL classdata1.tab], le nom du fichier est [!DNL classdata1.fin].fin.

À intervalles réguliers, Adobe récupère les fichiers de données chargés auxquels un fichier FIN est associé. Adobe les importe ensuite dans les suites de rapports et dans les ensembles de données spécifiés dans la configuration du compte FTP.

## Créer un compte FTP {#task_C019268E6C934C7C95F4326F42A22CCF}

Avant de charger des données via FTP, vous devez créer un compte FTP. >

<!-- 

t_create_an_ftp_account.xml

 -->

Voir [FTP et SFTP](https://marketing.adobe.com/resources/help/fr_FR/whitepapers/ftp/) pour en savoir plus sur les serveurs FTP d’Adobe.

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
1. Cliquez sur **[!UICONTROL Importer un fichier]**, puis sur **[!UICONTROL Importation FTP]**.
1. Sous l’onglet **[!UICONTROL Importer un fichier]**, cliquez sur **[!UICONTROL Ajouter nouveau]**.
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
