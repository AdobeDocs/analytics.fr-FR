---
description: Migration des comptes d’utilisateurs Analytics sous la forme d’Enterprise ID ou de Federated ID vers Adobe Admin Console.
title: Migration de comptes d’utilisateurs Analytics sous la forme d’Enterprise ID et de Federated ID
feature: Admin Tools
exl-id: 988ed685-4eca-4b0b-a653-9c6a156852f1
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 97%

---

# Migration de comptes d’utilisateurs Analytics sous la forme d’Enterprise ID et de Federated ID

Migration des comptes d’utilisateurs Analytics sous la forme d’Enterprise ID ou de Federated ID vers Adobe Admin Console.

## Conditions préalables {#prereqs}

Conditions préalables à la gestion des utilisateurs dans Adobe Admin Console.

Pour les nouveaux domaines et les nouveaux répertoires, suivez les étapes afin de :

* Configurer un répertoire
* Configurer des domaines
* Lier des domaines à des répertoires

Voir [Configurer un système d’identités](https://helpx.adobe.com/fr/enterprise/using/set-up-identity.html) pour obtenir de l’aide.

Lorsqu’un répertoire a déjà été créé dans une autre organisation par une autre unité ou équipe commerciale, suivez les étapes décrites dans [Configuration d’identité](https://helpx.adobe.com/fr/enterprise/using/set-up-identity.html#Directorytrusting) afin d’établir le répertoire dans l’organisation que vous utilisez pour Analytics.

## Migration de comptes d’utilisateurs sous la forme d’Enterprise ID et de Federated ID {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

Lors de cette procédure, vous serez amené à effectuer les opérations suivantes :

* Télécharger une liste de comptes utilisateurs dans **[!UICONTROL Analytics]** > **[!UICONTROL Utilisateurs et ressources Analytics]**.

* Télécharger une liste actualisée des utilisateurs dans **[!UICONTROL Admin Console]** > **[!UICONTROL Utilisateurs]**.

* Comparer les listes (rechercher les doublons afin d’éviter d’écraser des données de compte dans Adobe Admin Console).
* Charger un fichier [!DNL .csv] complet (dans **[!UICONTROL Admin Console]** > **[!UICONTROL Utilisateurs]**) avec les utilisateurs Enterprise ID ou Federated ID dans Adobe Admin Console.

Si vous devez migrer des comptes utilisateurs Adobe ID déjà existants vers un Enterprise ID ou un Federated ID, contactez l’Assistance clientèle d’Adobe et demandez le [changement d’identité d’utilisateurs en bloc](https://helpx.adobe.com/fr/enterprise/using/bulk-operations.html).

**Pour migrer des comptes utilisateurs**

1. Téléchargez le fichier de comptes utilisateurs Analytics ([!DNL User Logins List.tab]) dans la gestion des utilisateurs d’Analytics, en employant une des méthodes suivantes (selon si vous avez, ou pas, déjà migré certains utilisateurs).
   1. *Avant de procéder à la migration,* accédez à **[!UICONTROL Administration]** > **[!UICONTROL Gestion des utilisateurs (héritée)]** > **[!UICONTROL Modifier les utilisateurs]**, puis cliquez sur **[!UICONTROL Télécharger le rapport]**.

      ![](/help/admin/admin/user-management2/user-migration/assets/download-report.png)

      Le lien de téléchargement du rapport n’est visible que pour les clients n’ayant pas encore migré d’utilisateurs.

   1. *Si vous avez déjà migré des utilisateurs,* accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Utilisateurs et ressources Analytics]**.

      ![Infos sur l’étape](/help/admin/admin/user-management2/user-migration/assets/admin-analytics-users-assets.png)

   1. Sur la page [!DNL Users], sélectionnez Utilisateurs, puis cliquez sur **[!UICONTROL Exporter au format CSV]**.

      ![Infos sur l’étape](/help/admin/admin/user-management2/user-migration/assets/export-csv-migrate.png)

   1. Ouvrez le fichier téléchargé [!DNL User List.csv] dans Excel.

      Soyez prêt à copier les valeurs *`Email`*, *`First Name`* et *`Last Name`* dans un fichier [!DNL sample.csv] (décrit à l’étape suivante).

      >[!IMPORTANT]
      >
      >Les valeurs du fichier CSV doivent être délimitées par des virgules.

      >[!TIP]
      >
      >Lors de cette étape, Adobe recommande d’écrémer votre liste d’utilisateurs pour vous assurer que seuls ceux possédant un ID d’e-mail valide soient inclus dans la migration sous la forme d’Enterprise ID ou de Federated ID.

1. Téléchargez la liste des utilisateurs Adobe Admin Console dans l’[!UICONTROL Adobe Admin] :

   1. Accédez à [!UICONTROL Admin Console] > **[!UICONTROL Utilisateurs]**, puis cliquez sur [Exporter utilisateurs vers CSV](https://helpx.adobe.com/fr/enterprise/using/users.html).

      ![](/help/admin/admin/user-management2/user-migration/assets/export-csv.png)

   1. Comparez les deux fichiers : les utilisateurs Adobe Admin Console existants du fichier [!DNL .csv] exporté ([!DNL sample.csv], dans notre exemple) aux utilisateurs du fichier Analytics [!DNL User Logins List.csv].

      >[!IMPORTANT]
      >
      >Si vous trouvez des doublons, supprimez-les dans le fichier Analytics [!DNL User Logins List.csv]. Cette étape permet de prévenir l’écrasement d’autorisations utilisateur d’Experience Cloud existantes dans Adobe Admin Console et d’obtenir la liste des comptes à migrer.

1. Téléchargez un modèle de fichier CSV depuis Adobe Admin Console :
   1. Dans l’onglet Utilisateurs, cliquez sur **[!UICONTROL Ajouter des utilisateurs par fichier CSV]**, puis sur **[!UICONTROL Télécharger un modèle de fichier CSV]**.

      ![Infos sur l’étape](/help/admin/admin/user-management2/user-migration/assets/add-users-csv.png)

   1. Sélectionnez **[!UICONTROL Modèle standard]**.

      Lors de cette étape, un fichier modèle [!DNL sample.csv] se télécharge.

      ![](/help/admin/admin/user-management2/user-migration/assets/download-csv-template.png)

1. Copiez les valeurs des colonnes *`Email`*, *`First Name`* et *`Last Name`* depuis [!DNL User Logins List.tab] dans les colonnes correspondantes du modèle [!DNL sample.csv].

   **Exemple de fichier modèle**

   ![](/help/admin/admin/user-management2/user-migration/assets/sample.png)

1. Dans le modèle ([!DNL sample.csv]), remplissez les champs requis suivants :

<table id="table_1B5EEFDB5BD8436EB760BE5FFAB1CF02"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Courriel </p> </td> 
   <td colname="col2"> <p>Copié depuis <span class="filepath"> User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prénom </p> </td> 
   <td colname="col2"> <p>Copié depuis <span class="filepath"> User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom </p> </td> 
   <td colname="col2"> <p>Copié depuis <span class="filepath"> User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type d’identité </p> </td> 
   <td colname="col2"> <p><span class="term"> Federated ID</span> ou <span class="term"> Enterprise ID</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine </p> </td> 
   <td colname="col2"> <p>Assurez-vous que les domaines dans les colonnes <span class="term"> Domain</span> et <span class="term"> Email</span> correspondent au(x) domaine(s) défini(s) dans les conditions préalables</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code de pays </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

Pour plus d’informations sur les champs du fichier [!DNL .csv], voir [Format du fichier CSV](https://helpx.adobe.com/fr/enterprise/using/users.html)

>[!NOTE]
>
>D’autres colonnes telles que [!UICONTROL Configurations de produit] et [!UICONTROL Rôles d’administration] peuvent être vides.

1. Chargez le fichier modèle dans l’onglet Utilisateurs d’Adobe Admin Console en cliquant sur **[!UICONTROL Ajouter des utilisateurs par fichier CSV]** (comme indiqué à l’Étape 3).
1. Dans Analytics, exécutez l’outil de migration (comme décrit dans [Migration des comptes d’utilisateurs Analytics](/help/admin/admin/user-management2/user-migration/t-migrate-users.md).
1. Cliquez sur **[!UICONTROL Migrer]** > **[!UICONTROL Migrer comme Enterprise ID]**.

   ![Infos sur l’étape](/help/admin/admin/user-management2/user-migration/assets/migrate-as-enterprise.png)

   Lorsque vous cliquez sur **[!UICONTROL Migrer]**, les utilisateurs sont associés aux comptes Enterprise ID ou Federated ID dans Adobe Admin Console. Les autorisations du compte utilisateur hérité dans Analytics correspondent aux autorisations accordées au compte Enterprise/Federated ID dans **[!UICONTROL Admin Console]** > **[!UICONTROL Analytics]** > **[!UICONTROL Profils produits]**. L’ID utilisateur s’affiche dans la section Migration terminée. Désactivez l’accès à [!DNL my.omniture.com] des comptes hérités.

   Après la migration des utilisateurs, l’état de la colonne État de migration passe de **[!UICONTROL Non initiée]** à **[!UICONTROL Migré]**.

   Les utilisateurs d’Adobe ID qui apparaissent dans l’outil de migration peuvent également être migrés durant ce processus. Ils devront continuer à s’identifier à l’aide de leur Adobe ID jusqu’à ce qu’un changement d’identité soit effectué. Contactez l’assistance clientèle d’Adobe pour obtenir de l’aide sur le changement d’identité.
