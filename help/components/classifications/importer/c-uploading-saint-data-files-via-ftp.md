---
description: Comment télécharger des fichiers de données via FTP.
title: Importation FTP
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
source-git-commit: d21903fe5683cadf2e235f5a1f911e2a62881c58
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 80%

---

# Importation FTP

>[!IMPORTANT]
>
>Il n’est plus recommandé d’utiliser le protocole FTP pour l’importation comme décrit sur cette page.
>
>Le protocole FTP n’est pas recommandé car il s’agit d’une méthode de partage de fichiers non chiffrée, ce qui signifie que tout le monde peut intercepter le contenu du fichier ainsi que le nom d’utilisateur et le mot de passe utilisés pour le compte.
>
>Configurez plutôt un compte cloud comme décrit à la section [Configuration des emplacements d’importation dans le cloud](/help/components/locations/configure-import-accounts.md).

Description de la procédure de téléchargement de fichiers de données via FTP.

## Importation FTP {#concept_2F965BE873254546A61FB755F25299FD}

Pour télécharger des fichiers de données via FTP :

1. **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.

Les limites recommandées suivantes sont importantes.

>[!IMPORTANT]
>
>Le fait d’avoir trop de petits fichiers ou de fichiers volumineux uniques peut créer une charge de traitement inutile sur les serveurs de traitement. Adobe recommande de diviser les fichiers volumineux en blocs de 50 Mo et de combiner les petits fichiers.

La configuration initiale remplit la base de données des classifications par un important jeu de données initiales ou restructure les classifications, plutôt que de reclasser quelques lignes ou d’en ajouter.

Après un premier chargement dans une suite de rapports (pour une variable ou un rapport donnés), Adobe recommande de ne charger que les lignes nouvelles et mises à jour lors des prochaines importations. Les lignes qui ne sont pas modifiées doivent être ignorées lors des chargements ultérieurs.

Chaque nouvelle valeur de clé chargée compte comme valeur unique de cette variable pour le mois.

Si vous avez dépassé les limites des valeurs uniques pour le mois, vous ne verrez pas les données de classifications correspondantes pour les valeurs dépassées dans les rapports. Vous pouvez voir ces classifications dans Data Warehouse.

>[!NOTE]
>
>Le temps nécessaire au traitement d’un fichier de données de classification varie selon la taille du fichier et le nombre de fichiers en cours de traitement par les serveurs d’Adobe. En règle générale, le traitement des fichiers de données ne dure pas plus de 72 heures.

## Créer un compte FTP

Avant de charger des données via FTP, vous devez créer un compte FTP. >

Voir [FTP et SFTP](/help/export/ftp-and-sftp/ftp-overview.md) pour en savoir plus sur les serveurs FTP d’Adobe.

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
1. Cliquez sur **[!UICONTROL Importer un fichier]**, puis sur **[!UICONTROL Importation FTP]**.
1. Sous l’onglet **[!UICONTROL Importer un fichier]**, cliquez sur **[!UICONTROL Ajouter nouveau]**.
1. Spécifiez les détails du compte FTP :

   | Élément | Description |
   |---|---|
   | **Nom** | Nom du compte FTP. |
   | **Données à classer** | Dans la liste déroulante, sélectionnez le jeu de données (variable de rapport marketing) que vous souhaitez classer. |
   | **Sélectionner des suites de rapports** | Sélectionnez les suites de rapport dans lesquelles vous souhaitez classer le jeu de données sélectionné. Si vous voulez sélectionner plusieurs suites de rapports, les classifications de chaque suite sélectionnée doivent être identiques. |
   | **Remplacer les données en cas de conflit** | Sélectionnez cette option pour écraser les données en double. Elle s’avère utile lorsque vous mettez à jour des classifications existantes. Si vous utilisez la variable [dernière architecture de classification](../sets/overview.md), ce paramètre est toujours activé. |
   | **Au terme de l’importation** | Sélectionnez cette option pour exporter automatiquement le jeu de données mis à jour vers le même compte FTP. Indiquez l’adresse de courriel à laquelle doivent être envoyées les notifications concernant ce compte FTP une fois l’importation terminée. Si vous utilisez la variable [dernière architecture de classification](../sets/overview.md), cette option n’est pas disponible. |
   | **Destinataire de la notification** | Indiquez l’adresse de courriel à laquelle doivent être envoyées les notifications concernant ce compte FTP. |
   | **Autoriser** | (Obligatoire) Autorise Adobe à importer automatiquement tous les fichiers de données envoyés au nouveau compte FTP. |

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Une fois les comptes FTP créés, vous pouvez les modifier ou les supprimer en cliquant sur le lien correspondant en regard du compte FTP souhaité.

>[!NOTE]
>
>Les notifications ne sont pas envoyées si une importation n’introduit aucune modification à une classification. Un email est envoyé uniquement si cette opération réussit et entraîne des modifications au niveau d’une classification.

## Importer des classifications via FTP

Vous pouvez utiliser un compte FTP pour importer des classifications dans Adobe Analytics.

Pour importer des classifications via FTP :

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
1. Cliquez sur **[!UICONTROL Importer un fichier]**, puis sur **[!UICONTROL Importation FTP]**.
1. Cliquez sur **[!UICONTROL Afficher]** en regard du compte FTP à utiliser.
1. Utilisez les informations d’accès FTP (Hôte, Identifiant, Mot de passe) pour accéder au serveur FTP à l’aide d’un client FTP de votre choix.
1. Chargez le fichier de données (`.tab` ou `.txt`) sur le serveur FTP.
1. Une fois le fichier de données chargé, chargez un fichier FIN indiquant que le fichier est prêt pour le traitement.

   Le fichier FIN est un fichier vide qui porte le même nom que votre fichier de données et qui est doté de l’extension de fichier `.fin`. Par exemple, si votre fichier de données se nomme `classdata1.tab`, le nom du fichier est `classdata1.fin` .fin.

À intervalles réguliers, Adobe récupère les fichiers de données chargés auxquels un fichier FIN est associé. Adobe les importe ensuite dans les suites de rapports et dans les ensembles de données spécifiés dans la configuration du compte FTP.

Une fois les fichiers lus et traités transférés dans le dossier FTP par Adobe Analytics, ils sont automatiquement supprimés du site FTP.
