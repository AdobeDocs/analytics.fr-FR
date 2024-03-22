---
description: Description de la procédure de création d’une requête Data Warehouse.
title: Configurer une destination de rapport pour une requête Data Warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '2430'
ht-degree: 99%

---

# Configurer une destination de rapport pour une requête Data Warehouse

Plusieurs options de configuration sont disponibles lors de la création d’une requête Data Warehouse. Les informations suivantes expliquent comment configurer une destination de rapport pour la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Tenez compte de ce qui suit lors de la configuration du rapport de destination :
>
>* Nous vous recommandons d’utiliser un compte cloud ou un e-mail pour votre destination de rapport. Les comptes FTP et SFTP hérités sont disponibles, mais ne sont pas recommandés.
>
>* Tout compte cloud que vous avez précédemment configuré pour les [flux de données](/help/export/analytics-data-feed/create-feed.md) ou l’[import de données de classification Adobe Analytics](/help/components/locations/locations-manager.md) est disponible pour Data Warehouse. Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés.
>
>* Les comptes cloud sont associés à votre compte d’utilisateur ou d’utilisatrice Adobe Analytics. Les autres utilisateurs et utilisatrices ne peuvent pas utiliser ni afficher les comptes cloud que vous configurez.
>

Pour configurer la destination vers laquelle les rapports de Data Warehouse sont envoyés :

1. Si ce n’est déjà fait, commencez à créer une requête dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Créer une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête de Data Warehouse, sélectionnez l’onglet [!UICONTROL **Destination du rapport**].

   ![Onglet de destination du rapport](assets/dw-report-destination.png)

1. (Conditionnel) Si un compte (et une destination sur ce compte) a déjà été configuré et que vous souhaitez l’utiliser comme destination de votre rapport :

   1. (Facultatif) Si vous êtes administrateur ou administratrice système, l’option [!UICONTROL **Afficher toutes les destinations**] est disponible. Activez cette option si vous souhaitez avoir accès à tous les comptes et emplacements créés par un utilisateur ou une utilisatrice de l’entreprise.

   1. Sélectionnez le compte dans le menu déroulant [!UICONTROL **Sélectionner un compte**].

      Tout compte cloud que vous avez configuré pour [importer des données de classification Adobe Analytics](/help/components/locations/locations-manager.md) depuis une destination cloud s’affiche ici et peut être utilisé. Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés. Ajoutez plutôt une nouvelle destination comme décrit ci-dessous.

   1. Sélectionnez la destination associée au compte à partir du menu déroulant [!UICONTROL **Sélectionner la destination**]. <!-- Is this correct? -->

1. (Conditionnel) Si vous n’avez pas configuré de compte auparavant :

   1. Sélectionnez [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Type de compte**] | Sélectionnez le type de compte cloud. Nous vous recommandons de disposer d’un compte unique pour chaque type de compte, avec plusieurs emplacements selon les besoins dans ce compte. <p>Après avoir choisi un type de compte, des champs spécifiques à ce type de compte s’affichent. </p> |
      | [!UICONTROL **Nom du compte**] | Spécifiez le nom du compte. Ce nom apparaît lors de la création d’un emplacement. <!-- true? --> |
      | [!UICONTROL **Description du compte**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. |

      Pour obtenir des instructions sur la configuration, développez la section ci-dessous qui correspond au [!UICONTROL **type de compte**] que vous avez sélectionné.

      Utilisez l’un des types de compte suivants lors de la configuration d’une destination de rapport. Pour obtenir des instructions sur la configuration, développez le type de compte. (Des [destinations héritées](#legacy-destinations) supplémentaires sont également disponibles, mais ne sont pas recommandées.)

      +++Amazon S3

      Indiquez les informations suivantes pour configurer un compte ARN de rôle Amazon S3 :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ARN de rôle**] | Vous devez fournir un ARN de rôle (nom de ressource Amazon) qu’Adobe peut utiliser pour accéder au compte Amazon S3. Pour ce faire, vous créez une politique d’autorisation IAM pour le compte source, vous la joignez à un utilisateur ou à une utilisatrice, puis vous créez un rôle pour le compte de destination. Pour plus d’informations, consultez [cette documentation AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/).<p>Pour plus d’informations sur la configuration de l’autorisation du compartiment, consultez l’article [Comment fournir un accès entre comptes aux objets stockés dans des compartiments Amazon S3 ?](https://repost.aws/knowledge-center/cross-account-access-s3) dans le centre de connaissances Amazon. |
      | [!UICONTROL **ARN d’utilisateur ou d’utilisatrice**] | L’ARN d’utilisateur ou d’utilisatrice (nom de ressource Amazon) est fourni par Adobe. Vous devez associer cet utilisateur ou cette utilisatrice à la politique que vous avez créée. |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Indiquez les informations suivantes pour configurer un compte Google Cloud Platform :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Identifiant du projet**] | ID de projet Google Cloud. Consultez la [documentation de Google Cloud sur l’obtention d’un ID de projet](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=fr#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Indiquez les informations suivantes pour configurer un compte Azure SAS :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ID de l’application**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistreement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **ID de cliente ou client**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, consultez la [documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **URI du coffre de clés**] | <p>Chemin d’accès au jeton SAS dans Azure Key Vault.  Pour configurer une SAS Azure (shared access signature), vous devez stocker un jeton SAS en tant que secret à l’aide d’Azure Key Vault. Pour plus d’informations, consultez la [documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Une fois l’URI de coffre de clés créé :<ul><li>Ajoutez une politique d’accès sur Key Vault afin d’accorder l’autorisation à l’application Azure que vous avez créée.</li><li>Assurez-vous que l’ID de l’application a bien reçu le rôle intégré `Key Vault Certificate User` afin d’accéder à l’URI de coffre de clés.</br><p>Pour plus d’informations, voir [Rôles intégrés Azure](https://learn.microsoft.com/fr-fr/azure/role-based-access-control/built-in-roles).</p></li></ul><p>Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’affectation d’une politique d’accès Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Nom secret du coffre de clés**] | Le nom du secret que vous avez créé lors de l’ajout du secret à Azure Key Vault. Dans Microsoft Azure, ces informations se trouvent dans le coffre Key Vault que vous avez créé, sur la page de paramètres de **Key Vault**. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Secret**] | Copiez le secret depuis l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur l’onglet **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistrement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Indiquez les informations suivantes pour configurer un compte Azure RBAC :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ID de l’application**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistreement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **ID de cliente ou client**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistrement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
      | [!UICONTROL **Secret**] | Copiez le secret depuis l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur l’onglet **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistrement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++E-mail

      Indiquez les informations suivantes pour configurer un compte de messagerie :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Personnes destinataires**] | Des notifications par e-mail peuvent être envoyées à des personnes spécifiques lorsque le rapport est envoyé. Spécifiez une seule adresse e-mail ou une liste d’adresses e-mail séparées par des virgules. <!-- How does this differ from the Notification email tab? --> |

   1. Sélectionnez [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes :
|Champ | Fonction |
|---------|----------|
| [!UICONTROL **Nom**] | Nom de l’emplacement.  |
| [!UICONTROL **Description**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. |
| [!UICONTROL **Compte d’emplacement**] | Sélectionnez le compte d’emplacement que vous avez créé dans [Ajouter un compte](#add-an-account). |

   1. Dans la section [!UICONTROL **Propriétés d’emplacement**], indiquez les informations spécifiques au type de votre compte d’emplacement.

      Pour obtenir des instructions sur la configuration, développez la section ci-dessous qui correspond au [!UICONTROL **type de compte**] que vous avez sélectionné précédemment.

      +++Amazon S3

      Indiquez les informations suivantes pour configurer un emplacement Amazon S3 :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du compartiment**] | Compartiment de votre compte Amazon S3 dans lequel vous souhaitez que les données Adobe Analytics soient envoyées. <p>Assurez-vous que l’ARN d’utilisateur ou d’utilisatrice fourni par Adobe dispose de l’autorisation `S3:PutObject` pour charger des fichiers vers ce compartiment. Cette autorisation permet à l’ARN d’utilisateur ou d’utilisatrice de charger les fichiers initiaux et de remplacer les fichiers pour les chargements suivants.</p> |
      | [!UICONTROL **Préfixe clé**] | Dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Indiquez les informations suivantes pour configurer un emplacement de la plateforme Google Cloud :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du compartiment**] | Compartiment de votre compte GCP où vous souhaitez que les données Adobe Analytics soient envoyées. <p>Assurez-vous que vous avez accordé l’une des autorisations suivantes au principal fourni par Adobe :<ul><li>`roles/storage.objectCreator` : utilisez cette autorisation si vous souhaitez limiter le principal uniquement à la création de fichiers dans votre compte GCP. </br>**Important :** si vous utilisez cette autorisation avec les rapports planifiés, vous devez utiliser un nom de fichier unique pour chaque nouvel export planifié. Sinon, la génération du rapport échouera, car le principal n’a pas accès pour remplacer les fichiers existants.</li><li>`roles/storage.objectUser` : utilisez cette autorisation si vous souhaitez que le principal ait accès à l’affichage, à la liste, à la mise à jour et à la suppression des fichiers dans votre compte GCP.</br>Cette autorisation permet au principal d’écraser les fichiers existants pour les chargements ultérieurs, sans avoir à générer automatiquement des noms de fichier uniques pour chaque nouvel export planifié.</li></ul><p>Pour plus d’informations sur l’octroi d’autorisations, consultez [Ajouter un compte principal à une stratégie au niveau du compartiment](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=fr#bucket-add) dans la documentation de Google Cloud.</p> |
      | [!UICONTROL **Préfixe de clé**] | Dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Spécifiez les informations suivantes pour configurer un emplacement Azure SAS :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du conteneur**] | Conteneur dans le compte que vous avez spécifié où vous souhaitez que les données Adobe Analytics soient envoyées. |
      | [!UICONTROL **Préfixe de clé**] | Dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, `folder_name/`<p>Assurez-vous que le magasin de jetons SAS que vous avez spécifié dans le champ Nom du secret Key Vault lors de la configuration du compte Azure SAS dispose de l’autorisation `Write`. Cela permet au jeton SAS de créer des fichiers dans votre conteneur Azure. <p>Si vous souhaitez que le jeton SAS remplace également les fichiers, assurez-vous que le magasin de jetons SAS dispose de l’autorisation `Delete`.</p><p>Pour plus d’informations, consultez [Ressources de stockage Blob](https://learn.microsoft.com/fr-fr/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) dans la documentation Azure Blob Storage.</p> |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Spécifiez les informations suivantes pour configurer un emplacement Azure RBAC :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du conteneur**] | Conteneur dans le compte que vous avez spécifié où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous d’accorder les autorisations de chargement de fichiers vers l’application Azure que vous avez créée précédemment. |
      | [!UICONTROL **Préfixe de clé**] | Dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, `folder_name/`.<p>Assurez-vous que l’ID d’application que vous avez spécifié lors de la configuration du compte Azure RBAC a reçu le rôle `Storage Blob Data Contributor` pour accéder au conteneur (dossier).</p> <p>Pour plus d’informations, consultez [Rôles intégrés Azure](https://learn.microsoft.com/fr-fr/azure/role-based-access-control/built-in-roles).</p> |
      | [!UICONTROL **Nom du compte**] | Compte de stockage Azure. |

      {style="table-layout:auto"}

+++

1. Poursuivez la configuration de votre requête Data Warehouse sur l’onglet [!UICONTROL **Options de rapport**]. Pour plus d’informations, voir [Configurer des options de rapport pour une requête Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Destinations héritées

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
