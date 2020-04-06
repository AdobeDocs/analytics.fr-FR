---
description: Description de la procédure de téléchargement de fichiers de données via FTP.
subtopic: Classifications
title: Importation FTP
topic: Admin tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Importation FTP

Description de la procédure de téléchargement de fichiers de données via FTP.

## Importation FTP {#concept_2F965BE873254546A61FB755F25299FD}

Description de la procédure de téléchargement de fichiers de données via FTP.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

Les limites recommandées suivantes sont importantes :

* Un grand nombre de petits fichiers se traduira par un traitement plus lent que quelques fichiers volumineux. Cela est dû au nombre de files d’attente et à la définition des priorités requises pour les tâches plus petites.
* Veuillez diviser les fichiers volumineux en blocs de 50 Mo. Cette opération n’est pas obligatoire, mais elle est recommandée, car elle offre une meilleure visibilité sur l’avancement sur l’arrière-plan. En outre, si des erreurs se produisent pendant le traitement de votre tâche, celle-ci sera redémarrée ; dans ce scénario, les fichiers volumineux se traduisent par une grande quantité de travail refait.

La configuration initiale remplit la base de données des classifications avec un grand jeu de données d’origine ou restructure les classifications, plutôt que de reclasser quelques lignes ou d’ajouter des lignes.

À la suite d’un premier chargement dans une suite de rapports (pour une variable ou un rapport donné), Adobe recommande de ne charger que les lignes nouvelles et mises à jour lors des prochaines importations. Les lignes qui ne sont pas modifiées doivent être omises lors des prochains chargements.

Chaque nouvelle valeur de clé que vous téléchargez est prise en compte par rapport à vos valeurs uniques pour cette variable pour le mois.

Si vous avez dépassé vos valeurs uniques pour le mois, vous ne verrez pas les données de classification correspondantes pour les valeurs dépassées dans . Vous pouvez voir ces classifications dans l’entrepôt de données ou dans le  ad hoc .

>[!NOTE] Le temps nécessaire au traitement d’un fichier de données de classification varie selon la taille du fichier et le nombre de fichiers en cours de traitement par les serveurs d’Adobe. Le traitement des fichiers de données ne dure généralement pas plus de 72 heures.

Avant de charger des données via FTP, vous devez créer un compte FTP. Pour plus d’informations, voir [Créer un compte FTP](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importer des classifications via FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Description de la procédure d’utilisation d’un compte FTP pour importer des classifications dans Adobe Analytics.

Pour plus d’informations sur la création d’un compte FTP, consultez  [Créer un compte FTP](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Cliquez sur **[!UICONTROL Import File]**, puis sur **[!UICONTROL FTP Import]**.
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. Utilisez les informations d’accès FTP (Hôte, Identifiant, Mot de passe) pour accéder au serveur FTP à l’aide d’un client FTP de votre choix.
1. Chargez le fichier de données ([!DNL .tab] ou [!DNL .txt]) sur le serveur FTP.
1. Une fois le fichier de données chargé, chargez un fichier FIN indiquant que le fichier est prêt pour le traitement.

   Le fichier FIN est un fichier vide qui porte le même nom que votre fichier de données et qui est doté de l’extension de fichier [!DNL .fin]. Par exemple, si votre fichier de données se nomme [!DNL classdata1.tab], le nom du fichier est [!DNL classdata1.fin].fin.

À intervalles réguliers, Adobe récupère les fichiers de données téléchargés auxquels est associé un fichier FIN. Adobe les importe dans les suites de rapports et les jeux de données spécifiés dans la configuration du compte FTP.

## Créer un compte FTP {#task_C019268E6C934C7C95F4326F42A22CCF}

Avant de charger des données via FTP, vous devez créer un compte FTP. >

<!-- 

t_create_an_ftp_account.xml

 -->

Voir [FTP et SFTP](https://marketing.adobe.com/resources/help/fr_FR/whitepapers/ftp/) pour en savoir plus sur les serveurs FTP d’Adobe.

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Cliquez sur **[!UICONTROL Import File]**, puis sur **[!UICONTROL FTP Import]**.
1. Sur l’ **[!UICONTROL Import File]** onglet, cliquez sur **[!UICONTROL Add New]**.
1. Spécifiez les détails du compte FTP :

   | Elément | Description |
   |---|---|
   | Nom | Nom du compte FTP. |
   | Données à classer | Dans le  déroulant, sélectionnez le jeu de données (variable de rapport marketing) à classifier. |
   | Sélectionner des suites de rapports | Sélectionnez les suites de rapports dans lesquelles vous souhaitez classer le jeu de données sélectionné. Pour sélectionner plusieurs suites de rapports, les classifications de chacune des suites de rapports sélectionnées doivent être identiques. |
   | Remplacer les données en cas de conflit | Sélectionnez cette option pour remplacer les données  du. Cette option est utile si vous mettez à jour des classifications existantes. Si vous ajoutez des classifications supplémentaires, cette option n’est pas recommandée. |
   | Une fois l’importation terminée | Sélectionnez cette option pour exporter automatiquement le jeu de données mis à jour vers le même compte FTP une fois Spécifiez l’adresse électronique à laquelle recevoir les notifications concernant ce compte FTP une fois l’importation terminée. |
   | Destinataire de la notification | Spécifiez l’adresse électronique à laquelle recevoir les notifications concernant ce compte FTP. |
   | Autoriser | (Obligatoire) Autorise Adobe à importer automatiquement tous les fichiers de données envoyés au nouveau compte FTP. |

1. Cliquez sur **[!UICONTROL Save]**.

Une fois les comptes FTP créés, vous pouvez les modifier ou les supprimer en cliquant sur le lien correspondant en regard du compte FTP souhaité.
