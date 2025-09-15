---
description: Description de la procédure de création d’une requête Data Warehouse.
title: Configurer une destination de rapport pour une requête Data Warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: f0a5f72667fd6fc7847ede82d5196d9159fc558c
workflow-type: tm+mt
source-wordcount: '1980'
ht-degree: 82%

---

# Configurer une destination de rapport pour une requête Data Warehouse

Plusieurs options de configuration sont disponibles lors de la création d’une requête Data Warehouse. Les informations suivantes expliquent comment configurer une destination de rapport pour la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Tenez compte de ce qui suit lors de la configuration du rapport de destination :
>
>* Nous vous recommandons d’utiliser un compte cloud ou un e-mail pour votre destination de rapport. Les [comptes FTP et SFTP hérités](#legacy-destinations) sont disponibles, mais ne sont pas recommandés.
>
>* Tous les comptes cloud que vous avez configurés précédemment sont disponibles pour Data Warehouse. Vous pouvez configurer des comptes cloud de l’une des manières suivantes :
>
>   * Lors de la configuration de [flux de données](/help/export/analytics-data-feed/create-feed.md).
>   
>   * Lors de [l’import de données de classification Adobe Analytics](/help/components/locations/locations-manager.md) (les comptes peuvent être utilisés, mais pas les emplacements configurés sur ces comptes).
>   
>   * Dans le gestionnaire des emplacements, dans [Composants > Emplacements](/help/components/locations/configure-import-accounts.md).
>
>* Les comptes cloud sont associés à votre compte d’utilisateur ou d’utilisatrice Adobe Analytics. Les autres utilisateurs et utilisatrices ne peuvent pas utiliser ni afficher les comptes cloud que vous configurez.
>
>* Vous pouvez modifier les emplacements que vous créez à partir du gestionnaire d’emplacements dans [Composants > Emplacements](/help/components/locations/configure-import-accounts.md).

Pour configurer la destination vers laquelle les rapports de Data Warehouse sont envoyés :

1. Si vous ne l’avez pas déjà fait, commencez à créer une requête dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête de Data Warehouse, sélectionnez l’onglet [!UICONTROL **Destination du rapport**].

   ![Onglet de destination du rapport](assets/dw-report-destination.png)

1. (Le cas échéant) Si un compte cloud (et une destination sur ce compte) a déjà été configuré dans Adobe Analytics, vous pouvez l’utiliser comme destination de votre rapport :

   >[!NOTE]
   >
   >Vous ne pouvez accéder aux comptes que si vous les avez configurés ou s’ils ont été partagés avec une organisation dont vous faites partie.
   >
   >Si vous êtes administrateur ou administratrice système, l’option [!UICONTROL **Afficher toutes les destinations**] est disponible. Activez cette option si vous souhaitez avoir accès à tous les comptes et emplacements créés par un utilisateur ou une utilisatrice de l’entreprise.

   1. Sélectionnez le compte dans le menu déroulant [!UICONTROL **Compte**].

      Les comptes cloud que vous avez configurés dans l’une des zones suivantes d’Adobe Analytics sont disponibles :

      * Lors de l’import de données de classification Adobe Analytics, comme décrit dans [Schéma](/help/components/classifications/sets/manage/schema.md).

        Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés. Ajoutez plutôt une nouvelle destination comme décrit ci-dessous.

      * Lors de la configuration de comptes et d’emplacements dans la zone Emplacements, comme décrit dans [Configurer des comptes d’import et d’export dans le cloud](/help/components/locations/configure-import-accounts.md) et [Configurer des emplacements d’import et d’export dans le cloud](/help/components/locations/configure-import-locations.md).

   1. Sélectionnez la destination associée au compte à partir du menu déroulant [!UICONTROL **Sélectionner la destination**]. <!-- Is this correct? -->

1. (Le cas échéant) Si vous n’avez pas accès à un compte cloud déjà configuré dans Adobe Analytics, vous pouvez en configurer un :

   1. Sélectionnez le menu déroulant [!UICONTROL **Compte**], puis sélectionnez [!UICONTROL **Ajouter un compte**].

   1. Dans la boîte de dialogue Ajouter un compte , spécifiez les informations suivantes :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du compte d’emplacement**] | Nom du compte d’emplacement. Ce nom apparaît lors de la création d’un emplacement. |
      | [!UICONTROL **Description du compte d’emplacement**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. |
      | [!UICONTROL **Rendre le compte disponible pour tous les utilisateurs de votre organisation**] | Activez cette option pour permettre à d’autres utilisateurs de votre organisation d’utiliser le compte.<p>Tenez compte des points suivants lors du partage de comptes :</p><ul><li>Les comptes que vous partagez ne peuvent pas être annulés.</li><li>Les comptes partagés ne peuvent être modifiés que par le propriétaire du compte.</li><li>Tout le monde peut créer un emplacement pour le compte partagé.</li></ul> |
      | [!UICONTROL **Type de compte**] | Sélectionnez le type de compte cloud. Nous vous recommandons de disposer d’un compte unique pour chaque type de compte, avec plusieurs emplacements selon les besoins dans ce compte.<p>Les administrateurs système peuvent limiter les types de compte que les utilisateurs peuvent créer, comme décrit dans la section [Configurer si les utilisateurs peuvent créer des comptes](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Si vous ne pouvez pas créer de comptes comme décrit dans cette section, contactez votre administrateur système.</p> |

   1. Dans la section [!UICONTROL **Propriétés du compte**], spécifiez des informations spécifiques au type de compte que vous avez sélectionné.

      Pour obtenir des instructions de configuration, développez la section ci-dessous qui correspond au [!UICONTROL **type de compte**] que vous avez sélectionné. (D’autres types de comptes hérités sont également disponibles, mais ne sont pas recommandés.)

      **Types de compte**

      +++Amazon S3 Role ARN

      **REMARQUE :** lorsque vous utilisez Amazon S3 avec Data Warehouse, seul le chiffrement SSE-S3 est pris en charge.

      Pour configurer un compte ARN de rôle Amazon S3, spécifiez les informations suivantes :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ARN de rôle**] | Vous devez fournir un ARN de rôle (nom de ressource Amazon) qu’Adobe peut utiliser pour accéder au compte Amazon S3. Pour ce faire, vous créez une politique d’autorisation IAM pour le compte source, vous la joignez à un utilisateur ou à une utilisatrice, puis vous créez un rôle pour le compte de destination. Pour plus d’informations, consultez [cette documentation AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

      {style="table-layout:auto"}

      +++

      +++Google Cloud Platform

      Pour configurer un compte Google Cloud Platform, spécifiez les informations suivantes :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Identifiant du projet**] | ID de projet Google Cloud. Consultez la [documentation de Google Cloud sur l’obtention d’un ID de projet](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=fr#identifying_projects). |

      {style="table-layout:auto"}

      +++

      +++SAS Azure

      Pour configurer un compte Azure SAS, spécifiez les informations suivantes :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ID de l’application**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistreement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **ID de cliente ou client**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, consultez la [documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **URI du coffre de clés**] | <p>Chemin d’accès au jeton SAS dans Azure Key Vault.  Pour configurer Azure SAS, vous devez stocker un jeton SAS en tant que secret à l’aide d’Azure Key Vault. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Une fois l’URI du coffre de clés créé, ajoutez une politique d’accès au coffre de clés pour accorder l’autorisation à l’application Azure que vous avez créée. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’affectation d’une politique d’accès Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>Ou</p><p>Si vous souhaitez accorder un rôle d’accès directement sans créer de politique d’accès, consultez la documentation Azure [Microsoft sur l’attribution de rôles Azure à l’aide du portail Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Cela ajoute l’affectation de rôle pour que l’ID d’application accède à l’URI de coffre de clés. </p> |
      | [!UICONTROL **Nom secret du coffre de clés**] | Nom du secret que vous avez créé lors de l’ajout du secret au coffre de clés Azure. Dans Microsoft Azure, ces informations se trouvent dans le coffre Key Vault que vous avez créé, sur la page des paramètres **coffre Key Vault**. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Secret du compte d’emplacement**] | Copiez le secret depuis l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur l’onglet **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistrement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |

      {style="table-layout:auto"}

      +++   

      +++RBAC Azure

      Pour configurer un compte Azure RBAC, spécifiez les informations suivantes :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ID de l’application**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistreement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **ID de cliente ou client**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistreement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **Secret du compte d’emplacement**] | Copiez le secret depuis l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur l’onglet **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistrement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |

      {style="table-layout:auto"}

      +++

      +++Adresse électronique

      >[!NOTE]
      >
      >Les comptes de messagerie ne peuvent être utilisés qu’avec les [Flux de données](/help/export/analytics-data-feed/create-feed.md). (Les comptes de messagerie ne sont pas pris en charge avec [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) ou [ensembles de classifications](/help/components/classifications/sets/overview.md)).

      Pour configurer un compte Azure RBAC, spécifiez les informations suivantes :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Personnes destinataires**] | Des notifications par e-mail peuvent être envoyées à des personnes spécifiques lorsque le rapport est envoyé. Spécifiez une seule adresse e-mail ou une liste d’adresses e-mail séparées par des virgules. |

      {style="table-layout:auto"}

      +++

1. Poursuivez la configuration de votre requête Data Warehouse sur l’onglet [!UICONTROL **Options de rapport**]. Pour plus d’informations, voir [Configurer des options de rapport pour une requête Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Types de compte hérités

>[!IMPORTANT]
>
>Les destinations décrites dans cette section sont héritées et ne sont pas recommandées. Utilisez plutôt l’une des destinations suivantes lors de la création d’une destination d’entrepôt de données : Amazon S3, Google Cloud Platform, Azure RBAC, Azure SAS ou E-mail. Consultez les informations ci-dessus pour plus d’informations sur chacune de ces destinations recommandées.

Les informations suivantes fournissent des informations de configuration pour chacune des destinations héritées :

### FTP

Les données d’entrepôt de données peuvent être distribuées vers un emplacement FTP hébergé par Adobe ou par le client ou la cliente. Nécessite un hôte FTP, un nom d’utilisateur et un mot de passe. Utilisez le champ Chemin d’accès pour placer les fichiers de flux dans un dossier. Les dossiers doivent déjà exister ; les fichiers lancent une erreur si le chemin d’accès précisé n’existe pas.

Renseignez les informations suivantes pour les champs disponibles :

#### Champs de compte

* [!UICONTROL **Nom du compte**] : nom du compte FTP.

* [!UICONTROL **Description du compte**] : description du compte FTP.

* [!UICONTROL **Nom d’hôte**] : saisissez l’URL de destination FTP de votre choix. Par exemple : `ftp.company.com`.

  >[!NOTE]
  >
  >  Ne pas inclure `ftp://` au début de l’URL.

* [!UICONTROL **Nom d’utilisateur ou d’utilisatrice**] : saisissez le nom d’utilisateur ou d’utilisatrice pour vous connecter au site FTP.

* [!UICONTROL **Mot de passe et confirmation du mot de passe**] : saisissez le mot de passe pour vous connecter au site FTP.

#### Champs d’emplacement

* [!UICONTROL **Nom de l’emplacement**] : nom de l’emplacement sur le compte FTP où vous souhaitez envoyer les fichiers.

* [!UICONTROL **Description de l’emplacement**] : description de l’emplacement sur le compte FTP.

* [!UICONTROL **Chemin du répertoire**] : chemin d’accès à l’emplacement sur le compte FTP.

### SFTP

La prise en charge SFTP de l’entrepôt de données est disponible. Nécessite un hôte SFTP, un nom d’utilisateur ou d’utilisatrice et un site de destination contenant une clé publique RSA ou DSA. Vous pouvez télécharger la clé publique appropriée lors de la création de la destination de l’entrepôt de données.

Renseignez les informations suivantes pour les champs disponibles :

#### Champs de compte

* [!UICONTROL **Nom du compte**] : nom du compte FTP.

* [!UICONTROL **Description du compte**] : description du compte FTP.

* [!UICONTROL **Nom d’hôte**] : saisissez l’URL de destination SFTP de votre choix. Par exemple : `sftp.company.com`.

  >[!NOTE]
  >
  >  Ne pas inclure `sftp://` au début de l’URL.

* [!UICONTROL **Nom d’utilisateur ou d’utilisatrice**] : saisissez le nom d’utilisateur ou d’utilisatrice pour vous connecter au site SFTP.

* [!UICONTROL **Utiliser des extensions de fichier temporaires lors du chargement**] : lorsque cette option est activée, l’extension de fichier `.part` est utilisée pendant le processus de chargement. Laissez cette option activée, sauf si votre serveur SFTP empêche la modification des noms de fichier une fois le chargement terminé.

* [!UICONTROL **Clés publiques**] : téléchargez la clé publique appropriée lors de la création de la destination de l’entrepôt de données.

#### Champs d’emplacement

* [!UICONTROL **Nom de l’emplacement**] : nom de l’emplacement sur le compte SFTP où vous souhaitez envoyer les fichiers.

* [!UICONTROL **Description de l’emplacement**] : description de l’emplacement sur le compte SFTP.

* [!UICONTROL **Chemin du répertoire**] : chemin d’accès à l’emplacement sur le compte SFTP.

Pour plus d’informations sur la configuration SFTP, voir [Envoi de requêtes Data Warehouse aux serveurs SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

Vous pouvez envoyer des données d’entrepôt de données directement vers des compartiments Amazon S3. Ce type de destination requiert un nom de compartiment, un identifiant de clé d’accès et une clé secrète. Consultez les [exigences de nommage pour des compartiments Amazon S3](https://docs.aws.amazon.com/fr_fr/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) dans les documents Amazon S3 pour plus d’informations.

L’utilisateur ou l’utilisatrice que vous désignez pour charger des données d’entrepôt de données doit disposer des [autorisations](https://docs.aws.amazon.com/fr_fr/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html) suivantes :

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

Les 16 régions standard AWS suivantes sont prises en charge (en utilisant l’algorithme de signature approprié si nécessaire) :

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>La région cn-north-1 n’est pas prise en charge.

### Azure Blob

Les entrepôts de données prennent en charge les destinations Azure Blob. Nécessite un conteneur, un compte et une clé. Amazon chiffre automatiquement les données au repos. Les données que vous téléchargez sont automatiquement déchiffrées. Pour en savoir plus, consultez [Création d’un compte Azure Storage](https://docs.microsoft.com/fr-fr/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) dans la documentation Microsoft Azure.

>[!NOTE]
>
>Vous devez mettre en œuvre votre propre processus pour gérer l’espace disque sur la destination d’entrepôt de données. Adobe ne supprime pas les données du serveur.
