---
title: Exigences de sécurité pour les serveurs FTP et SFTP
description: Découvrez les exigences de sécurité des serveurs FTP et SFTP.
feature: Data Configuration and Collection
role: Admin
source-git-commit: 26ae4edacbc3591d4d3358afe009bf7831d45efb
workflow-type: tm+mt
source-wordcount: '1899'
ht-degree: 2%

---

# Exigences de sécurité pour les serveurs FTP et SFTP

Cette page couvre les exigences de sécurité des serveurs FTP et SFTP existants qui reçoivent des données diffusées par les flux de données Adobe Analytics ou Data Warehouse.

* **Serveurs FTP existants** : ils doivent être mis à niveau pour utiliser le protocole SFTP, comme décrit dans la section ci-dessous, [Mettre à niveau des serveurs FTP pour utiliser le protocole SFTP](#upgrade-ftp-servers-to-use-sftp).

  La mise à niveau de FTP vers SFTP est une exigence car le protocole SFTP offre une sécurité accrue.

  Pour un niveau de sécurité supérieur, vous pouvez également effectuer une transition vers une destination cloud moderne. (Pour plus d’informations, voir [Configuration des comptes d’import et d’export cloud](https://experienceleague.adobe.com/fr/docs/analytics/components/locations/configure-import-accounts).)

* **Serveurs SFTP existants (et nouveaux serveurs SFTP mis à niveau)** : les anciens mots de passe doivent faire l’objet d’une rotation, comme décrit dans la section ci-dessous, [rotation de votre mot de passe SFTP](#rotate-your-sftp-password).

  La rotation régulière du mot de passe SFTP est une bonne pratique en matière de sécurité qui permet de protéger vos données.

>[!IMPORTANT]
>
>Tenez compte des situations suivantes avant d’effectuer les étapes de cet article.
>
>* **Adobe recommande, si possible, de passer à une destination cloud moderne plutôt qu’à une mise à niveau vers SFTP.**
>Les FTP et SFTP sont des types de destination hérités. Plutôt que de mettre à niveau les comptes FTP vers SFTP et de faire pivoter les mots de passe SFTP comme décrit dans cet article, Adobe recommande de passer à un type de destination cloud moderne (tel qu’Amazon S3, Google Cloud Platform ou Azure). Ces destinations cloud offrent un niveau de sécurité plus élevé. Pour plus d’informations, voir [Configuration des comptes d’import et d’export cloud](https://experienceleague.adobe.com/fr/docs/analytics/components/locations/configure-import-accounts).
>
>* **Si les comptes FTP et SFTP sont utilisés exclusivement pour les classifications, migrez vers les ensembles de classifications.**
>Si votre compte FTP ou SFTP est utilisé exclusivement pour les classifications, vous devez migrer de l’**importateur de classifications** vers les **ensembles de classifications**, plutôt que de mettre à niveau les comptes FTP vers SFTP et de faire pivoter les mots de passe SFTP comme décrit dans cet article. L’importateur de classifications sera obsolète et ne sera plus accessible après le **31 août 2026**. Pour plus d’informations, voir [ Présentation des ensembles de classifications ](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview).

## Conditions préalables

### Inventaire de vos comptes FTP

Les processus décrits sur cette page lors de la mise à niveau des serveurs FTP pour utiliser le protocole SFTP doivent être terminés pour chaque site FTP utilisé pour les flux de données et Data Warehouse.

Par conséquent, vous devez identifier tous les comptes FTP qui reçoivent des données pour les flux de données ou Data Warehouse. Ces informations sont affichées dans vos paramètres de configuration FTP, comme décrit dans la section [Types de comptes hérités](/help/components/locations/configure-import-accounts.md#configure-a-location-account) de l’article [Configurer des comptes d’import et d’export cloud](/help/components/locations/configure-import-accounts.md).

Pour chaque compte, collectez les informations suivantes :

* **Hôte** : nom d’hôte du serveur FTP auquel votre compte se connecte (par exemple, `ftp.omniture.com`, `ftp2.omniture.com`, etc.).

* **Port** : lors de l’utilisation d’un serveur SFTP hébergé par Adobe, les clients SFTP se connectent sur le port 22. Les connexions FTP non sécurisées utilisent le port 21.

* **Nom d’utilisateur** : nom d’utilisateur utilisé pour se connecter au serveur FTP.

* **Secret du compte d’emplacement** : secret du compte actuel pour le compte. Il s’agit du secret de compte (mot de passe) que vous utilisez actuellement lors du téléchargement des données diffusées vers votre emplacement FTP. Ces informations ne sont pas disponibles à partir de l’interface d’Adobe Analytics.

### Confirmer que vous pouvez mettre à jour les informations d’identification dans vos outils

Assurez-vous que vous pouvez mettre à jour les mots de passe SFTP dans l’outil ou le script que vous utilisez pour vous connecter au site SFTP (par exemple, un client SFTP, un script automatisé ou une plateforme tierce).

Tous les clients doivent se connecter via SFTP avec le mot de passe comme solution de secours.

## Mettre à niveau les serveurs FTP pour utiliser le protocole SFTP

>[!IMPORTANT]
>
>Si vos données FTP sont transmises à un partenaire tiers (par exemple, un cabinet de conseil ou un fournisseur d’analyses), contactez-le avant de suivre les étapes décrites dans cet article.

### Étape 1 : générer les clés SSH de votre organisation pour télécharger les données

Cette section décrit comment générer les clés SSH de votre organisation (une paire de clés publique/privée) utilisées pour **télécharger des données** à partir du serveur SFTP.

>[!NOTE]
>
>À une étape ultérieure, vous téléchargerez une autre clé publique fournie par Adobe. Il fait partie d’une deuxième paire de clés publique/privée, utilisée par Adobe pour **charger des données** sur le serveur SFTP.

Pour configurer un transfert sécurisé pour télécharger des données à partir de votre serveur FTP :

1. Connectez-vous à la station de travail sur laquelle vous téléchargez les données à partir du serveur FTP.

1. Générez une paire de clés publique/privée à utiliser pour un transfert sécurisé.

   Lors de l’utilisation d’un serveur FTP hébergé par Adobe, Adobe prend en charge les clés RSA et ed25519.

   * **Dans un environnement Linux** : Exécutez la commande suivante pour générer la paire de clés ed25519 :

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     Si votre politique ne vous permet pas d’utiliser les clés ed25519, exécutez la commande suivante pour générer la paire de clés RSA :

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **Dans un environnement Windows** : utilisez PuTTYgen.

1. Créez un fichier nommé [!DNL `authorized_keys`] (sans extension).

1. Copiez le contenu de la clé publique dans le fichier [!DNL `authorized_keys`].

1. Dans une étape ultérieure, vous reviendrez à ce fichier [!DNL `authorized_keys`] pour ajouter la clé publique Adobe, qui est utilisée par Adobe pour charger les données sur le serveur SFTP. Vous ajoutez ensuite le fichier [!DNL `authorized_keys`] au serveur SFTP.

### Étape 2 : créer un compte d’emplacement SFTP dans Adobe Analytics

Créez un compte d’emplacement SFTP pour remplacer chaque compte FTP existant.

Lors de la création d’un compte d’emplacement SFTP, vous devez utiliser les mêmes nom d’hôte et nom d’utilisateur que ceux utilisés dans le compte FTP existant qu’il remplace.

>[!NOTE]
>
>Lors d’une étape ultérieure, vous allez configurer ce nouveau compte d’emplacement à utiliser comme destination pour vos flux de données et vos diffusions Data Warehouse.

#### Création du compte SFTP

1. Dans Adobe Analytics, accédez à [!UICONTROL **Composants**] > [!UICONTROL **Emplacements**].

1. Sélectionnez l’onglet [!UICONTROL **Comptes d’emplacement**].

1. Sélectionnez [!UICONTROL **Ajouter un compte**].

1. Dans le champ déroulant [!UICONTROL **Type de compte**], sélectionnez [!UICONTROL **SFTP (hérité)**].

1. Renseignez les champs suivants :

   | Nom du champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom d’hôte**] | Votre nom d’hôte SFTP (par exemple, `ftp.omniture.com`). |
   | [!UICONTROL **Port**] | Port du pare-feu par lequel les données seront envoyées. Il s’agit du port 22 pour les connexions SFTP hébergées par Adobe. |
   | [!UICONTROL **Nom d’utilisateur**] | Votre nom d’utilisateur SFTP. Utilisez le même nom d’utilisateur que celui de votre compte FTP. |

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Dans la boîte de dialogue [!UICONTROL **Compte créé**], téléchargez la clé publique RSA ou ed25519, puis sélectionnez **[!UICONTROL OK]**. Il s’agit de la clé publique SSH utilisée par Adobe pour charger des données sur le serveur SFTP. (Vous utiliserez cette clé dans la section suivante, [Ajout d’une clé publique SSH Adobe au serveur SFTP](#add-adobes-ssh-public-key-to-the-sftp-server).)

1. Répétez ce processus pour chaque compte SFTP que vous souhaitez créer.

1. Passez à la section suivante, [Charger la clé publique sur le serveur SFTP](#upload-the-public-key-to-the-sftp-server).

#### Ajoutez la clé publique SSH Adobe au fichier `authorized_keys` et chargez-la sur votre serveur FTP

La clé publique que vous venez de télécharger à l’étape 7 de la section précédente fait partie d’une paire de clés publique/privée utilisée par Adobe pour **charger des données** sur le serveur SFTP.

Vous devez ajouter cette clé publique au même fichier `authorized_keys` que celui où vous avez précédemment ajouté la clé de téléchargement de votre organisation (celui que vous avez généré à l’[Étape 1 : générer la clé de téléchargement de votre organisation et l’ajouter à votre serveur FTP](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)).

Pour ajouter la clé publique SSH d’Adobe au fichier `authorized_keys` et la charger sur votre serveur FTP :

1. Connectez-vous à la station de travail sur laquelle vous téléchargez les données à partir du serveur FTP.

1. Ouvrez le fichier [!DNL `authorized_keys`] et ajoutez-y la clé de chargement Adobe. Ce fichier doit déjà contenir la clé de téléchargement de votre organisation à partir de [Étape 1 : générez la clé de téléchargement de votre organisation et ajoutez-la à votre serveur FTP](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server).

1. Chargez le fichier [!DNL `authorized_keys`] sur votre serveur FTP :

   1. Connectez-vous au serveur FTP et connectez-vous avec votre nom d’utilisateur et votre mot de passe.\
      Il peut s’agir d’un serveur FTP hébergé par Adobe ou de votre propre serveur FTP.
   1. Créez un répertoire [!DNL .ssh] (s’il n’existe pas déjà).
   1. Chargez le fichier [!DNL `authorized_keys`] dans le répertoire [!DNL .ssh].

1. Mettez à jour les paramètres de votre pare-feu pour autoriser les connexions entrantes à partir du serveur SFTP. Lors de l’utilisation d’un serveur SFTP hébergé par Adobe, autorisez les connexions entrantes à partir de plages d’adresses IP d’Adobe sur le port 22.

1. Testez la connexion en vous connectant au serveur à l’aide de votre client SFTP.

1. Répétez ce processus pour chaque compte SFTP que vous avez créé dans la section précédente, [Créer le compte SFTP](#create-the-sftp-account).

1. Passez à la section suivante, [Ajouter un emplacement dans le compte](#add-a-location-within-the-account).

#### Ajouter un emplacement dans le compte

1. Sur l’onglet **Emplacements**, sélectionnez **Ajouter un emplacement**.

1. Indiquez un nom, une description et si cet emplacement sera utilisé avec les flux de données ou Data Warehouse.

1. Dans le champ [!UICONTROL **Compte d’emplacement**], sélectionnez le compte que vous venez de créer.

1. Dans le champ [!UICONTROL **Chemin du répertoire**], spécifiez le chemin d’accès au répertoire sur le serveur SFTP. Les dossiers du chemin d’accès doivent déjà exister. Dans le cas contraire, une erreur se produit. Par exemple : `/folder_name/folder_name`.

1. Sélectionnez **Enregistrer**.

1. Répétez ce processus pour chaque compte SFTP que vous avez créé.

Pour obtenir des instructions détaillées, voir [Configuration des emplacements d’importation et d’exportation cloud](https://experienceleague.adobe.com/fr/docs/analytics/components/locations/configure-import-locations).

### Étape 3 : modifier les flux de données et les requêtes Data Warehouse pour utiliser la nouvelle destination SFTP

Mettez à jour les flux de données planifiés et les requêtes Data Warehouse existants qui envoient actuellement des données aux destinations FTP afin d’utiliser les nouvelles destinations SFTP que vous avez créées.

#### Modifier les flux de données

Modifiez chaque flux de données planifié configuré avec l’ancienne destination FTP pour utiliser la nouvelle destination SFTP :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].

1. Recherchez le flux de données à modifier. Pour localiser un flux de données, vous pouvez [filtrer et rechercher la liste des flux de données](#filter-and-search-the-list-of-data-feeds).

1. Sélectionnez le flux de données dans la colonne [!UICONTROL **Nom du flux**].

   La page [!UICONTROL **Modifier _nom_flux_**] s’affiche.

1. Dans la section [!UICONTROL **Destination**], dans le champ [!UICONTROL **Compte**], utilisez le menu déroulant pour sélectionner la nouvelle destination SFTP que vous avez créée.

1. Dans le champ [!UICONTROL **Emplacement**], utilisez le menu déroulant pour sélectionner l’emplacement dans le compte SFTP.

1. Sélectionnez [!UICONTROL **Enregistrer**].

Pour plus d’informations, voir [Modifier un flux de données](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) dans [Gérer les flux de données](/help/export/analytics-data-feed/df-manage-feeds.md).

#### Modification des requêtes Data Warehouse

Modifiez chaque requête Data Warehouse planifiée configurée avec l’ancienne destination FTP afin d’utiliser la nouvelle destination SFTP :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Data Warehouse**].

1. Sur la page Data Warehouse, sélectionnez la requête à modifier.

   ![Gérer une requête](assets/dw-manage-request.png)

1. Sélectionnez [!UICONTROL **Modifier**].

1. Sélectionnez l’onglet [!UICONTROL **Destination du rapport**] .

1. Dans le champ [!UICONTROL **Compte**], utilisez le menu déroulant pour sélectionner la nouvelle destination SFTP que vous avez créée.

1. Dans le champ [!UICONTROL **Emplacement**], utilisez le menu déroulant pour sélectionner l’emplacement dans le compte SFTP.

1. Sélectionnez [!UICONTROL **Enregistrer les modifications**].

Pour plus d’informations, voir [Modifier les requêtes](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) dans [Gérer les requêtes Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

### Étape 4 : mettre à jour les paramètres de votre pare-feu

Si ce n’est pas déjà fait, vous devez mettre à jour les paramètres de votre pare-feu, comme suit :

* **Lorsque vous utilisez des serveurs FTP Adobe** : vous devez mettre à jour les paramètres de votre pare-feu pour autoriser les connexions **sortantes** sur le port 22.

* **Lorsque vous utilisez votre propre serveur FTP** : vous devez mettre à jour les paramètres de votre pare-feu pour autoriser la connexion **entrante** sur le port sur lequel vous hébergez le service, qui est généralement le port 22.

Vous devez également supprimer les anciennes règles spécifiques au FTP, telles que l’autorisation des connexions entrantes sur le port 21. (FTP utilise le port 21, ainsi qu’une gamme de ports supplémentaires pour le transfert de données. En tant que bonne pratique de sécurité, vous devez éventuellement supprimer cet accès inutile via votre pare-feu.)

### Étape 5 : vérifiez que les flux de données planifiés et les requêtes Data Warehouse sont correctement diffusés

Après la mise à jour de chaque flux de données existant et de chaque demande Data Warehouse pour utiliser le nouveau compte et emplacement SFTP, attendez la prochaine diffusion planifiée. Vérifiez que les données arrivent à la nouvelle destination comme prévu.

### Étape 6 : rotation du mot de passe sur le serveur SFTP mis à niveau

Après la mise à niveau d’un serveur FTP vers SFTP, vous devez également faire pivoter le mot de passe SFTP, comme décrit dans la section suivante, [Rotation de votre mot de passe SFTP](#rotate-your-sftp-password).

## Rotation de votre mot de passe SFTP

Un mot de passe SFTP sert de méthode d’authentification de secours en cas d’échec de l’authentification par clé.

Faites pivoter le mot de passe SFTP peu après la mise à niveau de FTP vers SFTP. Il devrait continuer d&#39;être renouvelé régulièrement, conformément à vos politiques établies.

1. Contactez l’assistance clientèle d’Adobe et demandez un nouveau mot de passe.

1. Pour chaque compte SFTP, indiquez les **nom d’hôte** et **nom d’utilisateur**.

   L’assistance clientèle générera un nouveau mot de passe pour chaque compte FTP.

1. Mettez à jour le mot de passe dans le client que vous utilisez pour vous connecter au serveur SFTP.


<!--
< **_Ignore everything after this_** >

-------

## Set up a new SFTP server or upgrade your existing FTP server

## Upgrade your FTP server to use SFTP where files are delivered or FTP account to use SFTP

Set up an SFTP server where Data Feed and Data Warehouse files can be delivered. This could beYou first need to upgrade your FTP server to use SFTP To upgrade an FTP account to use SFTP, follow the steps in [Connect to an FTP account with SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md).

## Create an SFTP account

## Rotate the passphrase on SFTP accounts


 
Adobe recommends that you periodically rotate the account secrets (passwords) on your FTP accounts that are associated with Data Feeds and Data Warehouse. 
 
Regular rotation of account secrets is a security best practice that helps protect your data. 
 
To ensure uninterrupted reception of data, follow the steps in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets) prior to changing any account secrets.  
 
>[!IMPORTANT] 
> 
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or Adobe Analytics vendor), coordinate with them before rotating account secrets. The third-party partner will need to update their own tools and scripts with the new account secrets immediately after the new account secrets are provided by your FTP host provider (either Adobe or another provider).

## When rotating account secrets is not necessary 
 
### Transition from FTP to a cloud destination 
 
FTP and SFTP are legacy destination types. Rather than rotating FTP account secrets, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure), which provide a higher level of security. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
 
### Transition from the Classifications importer to Classification sets 
 
If your FTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than rotating your FTP account secrets. The Classification importer will be deprecated and no longer accessible after **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview). 

## Prepare to rotate account secrets 
 
Complete the following steps before attempting to rotate FTP account secrets: 
 
### Step 1: Inventory your FTP accounts 
 
Identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md). 
 
For each account, gather the following information: 
 
* **Host**: The FTP destination of the host your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth). 
 
* **Port**: SFTP clients connect on port 22. FTP connections that are non-secure use port 21. 
 
* **Username**: The username used to log in to the FTP site. 
 
* **location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface. 
 
 
### Step 2: Confirm that you can update credentials in your tools 
 
Make sure you can update the FTP account secret in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform). 
 
### Step 3: Create FTP cloud location accounts with your current credentials 
 
Create new FTP cloud location accounts to replace your existing FTP location accounts. These new accounts will be used as the destination for your Data Feeds and Data Warehouse deliveries.  
 
When creating the new FTP accounts, you must use the same hostname, username, and account secret that are used in your existing FTP accounts. 
 
#### Create each FTP account 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 
 
1. Select the **Location accounts** tab. 
 
1. Select **Add account**. 
 
1. In the **Account type** drop-down field, select **FTP (legacy)**. 
 
1. Complete the following fields: 

   | Field name | Function |
   |---------|----------|
   | **Hostname** |  Your Adobe FTP hostname (for example, `ftp.omniture.com`). | 
   | **Port** | SFTP clients connect on port 22. FTP connections that are non-secure use port 21. | 
   | **Username** | Your current FTP username. |
   | **Location account secret** | Your current FTP account secrets (password).  |
 
1. Select **Save**. 
 
Repeat this process for each FTP account. 
 
For detailed instructions, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
 
#### Add a location within the account 
 
1. On the **Locations** tab, select **Add location**. 
 
1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse. 
 
1. In the [!UICONTROL **Location account**] field, select the account you just created. 
 
1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the FTP server. Folders must already exist; feeds throw an error if the specified path does not exist. For example, `/folder_name/folder_name`. 
 
1. Select **Save**. 
 
Repeat this process for each location. 
 
For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations). 
 
### Step 4: Reference the new FTP cloud accounts from any scheduled Data Feeds and Data Warehouse requests 
 
Update any existing scheduled Data Feeds and Data Warehouse requests to use the FTP cloud accounts you created.  
 
* **Data Feeds**: Go to **Admin** > **Data Feeds**, edit each scheduled  Data Feed that uses an FTP account, then change the destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md). 
 
* **Data Warehouse**: Go to **Tools** > **Data Warehouse**, edit each scheduled Data Warehouse request that uses an FTP account, then change the report destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md). 
 
### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly. 
 
After updating each existing Data Feed and Data Warehouse request to use the new FTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected. 

## Request a new account secret 
 
>[!IMPORTANT] 
>
>Before requesting a new account secret, consider the following:
>
>* The steps in this section apply only if you are using an Adobe-provided FTP account. For example, the FTP hostname is `ftp.omniture.com`, `ftp2.omniture.com` or similar.   If your FTP hostname is not provided by Adobe, please contact your FTP host provider for details on changing the account secret.
> 
>* Request a new account secret only after you complete all the preparation steps described in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets). 
>
>* After Adobe Customer Care or your third-party FTP host provider provides a new account secret, the old account secret is immediately invalidated. There is no way to revert to the previous account secret. 
>
 
To request a new account secret from Adobe: 
 
1. Contact Adobe Customer Care. 
 
1. For each FTP account, provide the **Hostname** and **Username** for each account that needs a new account secret. 
 
   Customer Care will generate a new account secret for each FTP account. 

1. Continue immediately with the following section, [After you receive the new account secret](#after-you-receive-the-new-account-secret).
 
## After you receive the new account secret 
 
Act immediately after receiving the new credentials. Any delay results in failed deliveries for active Data Feeds and Data Warehouse requests. 
 
### Step 1: Update your tools and scripts 
 
Update the FTP account secret in any tool, script, or automated process that connects to the FTP account. Make sure all team members and third-party partners who access the account are notified. 
 
### Step 2: Update your cloud location accounts 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 

1. Select the **Location accounts** tab. 

1. Find the FTP account that you created in Step 3 of section, [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets).

1. Select **Edit details**. 

1. Enter the new account secret and confirm it. 

1. Select **Save**. 
 
Repeat this process for each account that was reset. 

For more detailed information about this process, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).
 
### Step 3: Test your connections 
 
Verify that your Data Feeds or Data Warehouse requests that use the FTP account are working correctly with the new account secret. 
 
>[!TIP] 
> 
>If your current tools use SFTP with SSH keys that haven't been recently rotated, consider rotating those keys as well.

 
## Troubleshooting 
 
If something goes wrong after the account secret is rotated and you cannot restore connectivity, you can create a new FTP account. After the new account is set up, point your Data Feed or Data Warehouse request to the new account and update your cloud location accordingly. 

For information about how to create an FTP account, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).

To set up secure transfer with your FTP server: 

1. Generate a public/private key pair to use for secure transfer.

   This process differs depending on whether your FTP server is Adobe-hosted or self-hosted:

   +++ For an Adobe-hosted FTP server:

   Generate a public/private key pair: 
   
      * **In a Linux environment**: Run the following command to generate the ed25519 key pair: 

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair (**Note:** The RSA key typically applies to customers who operate under FIPS 186-4, as ed25519 is first supported in the newer FIPS 186-5):

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

      * **In a Windows environment**: Use PuTTYgen.

   +++

   +++ For a self-hosted FTP server: 
   
   If you want to set up secure transfer with your own FTP server, you must have an SFTP hostname, username, and SFTP account within Adobe Analytics that contains a valid RSA or ed25519 public key from Adobe. This key must be installed on your SFTP server. You download this public key as part of the process of [creating the SFTP account](#create-the-sftp-account).

   +++

1. Create a file named [!DNL `authorized_keys`] (no extension).



3 basic steps: Set up SFTP on customer side, then on Adobe side, then change passphrase. 

1. FTP site: ftp.omniture.com - Using username/password to connect. Adobe uses the same username/password to connect to the site.

2. user can then upload their public key to that server, then start connecting to that server with their private key using SFTP. (They also need to open Port 22 in the firewall and they would close the other ports they don't need.)

3. In Locations, create a new location, use the same username. 

4. After they create that location, we give them our public key, and they have to install it on their SFTP server.

5. Then they switch all their data feeds to use the new Location. And then we'll use SFTP to send the data. 

6. Then they call Customer Care to get new passphrase (rotate passphrase), and then they change the passphrase on their side. Passphrase is only used if SSH fails (they have the wrong keys--a bad actor could use bad keys and then use the password. But they don't have to coordinate the switching of the passphrase with installation of SFTP. )


If they're using a third-party to do this, the third-party would need to set up SFTP - This is the same as we have documented right now. It doesn't have to be immediate, though, like we were assuming before. 


If it's they're own FTP site, it would be the same. They would need to start using SFTP with their FTP server, then get our public key and install it on their server. Shouldn't matter if the FTP site is hosted by Adobe or not. 

-->

