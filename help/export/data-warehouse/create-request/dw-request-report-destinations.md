---
description: Description de la procédure de création d’une demande Data Warehouse.
title: Configuration d’une destination de rapport pour une requête de Data Warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: 7edee01a5a5399762f10037cf920863af35cc4d7
workflow-type: tm+mt
source-wordcount: '2235'
ht-degree: 10%

---

# Configuration d’une destination de rapport pour une requête de Data Warehouse

Plusieurs options de configuration sont disponibles lors de la création d’une requête de Data Warehouse. Les informations suivantes expliquent comment configurer une destination de rapport pour la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Tenez compte des points suivants lors de la configuration d’une destination de rapport :
>
>* Nous vous recommandons d’utiliser un compte cloud ou un e-mail pour votre destination de rapport. Les comptes FTP et SFTP hérités sont disponibles, mais ne sont pas recommandés.
>
>* Les demandes de Data Warehouse sont associées à votre compte utilisateur Adobe Analytics. Par défaut, les autres utilisateurs ne peuvent pas utiliser ni afficher les requêtes que vous configurez. Vous pouvez rendre les requêtes de Data Warehouse disponibles pour d’autres utilisateurs de votre entreprise en activant la variable **Afficher toutes les destinations** bascule, comme décrit dans la section [Paramètres généraux de la demande de Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md).
>
>* Tout compte cloud que vous avez précédemment [configuré pour les flux de données](/help/export/analytics-data-feed/create-feed.md) sont disponibles pour Data Warehouse.
>
>* Comptes cloud configurés pour [importation de données de classification Adobe Analytics](/help/components/locations/locations-manager.md) d’une destination cloud peut être utilisée lors de la configuration d’une destination de rapport. Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés.

Pour configurer la destination vers laquelle les rapports de Data Warehouse sont envoyés :

1. Commencez à créer une requête dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête de Data Warehouse , sélectionnez le [!UICONTROL **Destination du rapport**] .

   ![Onglet Destination du rapport](assets/dw-report-destination.png)

1. (Conditionnel) Si un compte (et une destination sur ce compte) a déjà été configuré et que vous souhaitez utiliser comme destination de votre rapport :

   1. (Facultatif) Si vous êtes administrateur système, la variable [!UICONTROL **Afficher toutes les destinations**] est disponible. Activez cette option si vous souhaitez avoir accès à tous les comptes et emplacements créés par un utilisateur de l’entreprise.

   1. Sélectionnez le compte dans la [!UICONTROL **Sélectionner un compte**] menu déroulant.

      Tout compte cloud que vous avez configuré pour [importation de données de classification Adobe Analytics](/help/components/locations/locations-manager.md) d’une destination cloud s’affiche ici et peut être utilisée. Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés. Ajoutez plutôt une nouvelle destination comme décrit ci-dessous.

   1. Sélectionnez la destination associée au compte à partir de la [!UICONTROL **Sélectionner la destination**] menu déroulant. <!-- Is this correct? -->

1. (Conditionnel) Si vous n’avez pas configuré de compte auparavant :

   1. Sélectionner [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Type de compte**] | Sélectionnez le type de compte cloud. Nous vous recommandons de disposer d’un compte unique pour chaque type de compte, avec plusieurs emplacements selon les besoins dans ce compte. <p>Après avoir choisi un type de compte, des champs spécifiques à ce type de compte s’affichent. </p> |
      | [!UICONTROL **Nom du compte**] | Attribuez un nom au compte. Ce nom apparaît lors de la création d’un emplacement. <!-- true? --> |
      | [!UICONTROL **Description du compte**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. |

      Pour obtenir des instructions sur la configuration, développez la section ci-dessous qui correspond à la variable [!UICONTROL **Type de compte**] que vous avez sélectionné.

      Utilisez l’un des types de compte suivants lors de la configuration d’une destination de rapport. Pour obtenir des instructions sur la configuration, développez le type de compte. (Additional [destinations héritées](#legacy-destinations) sont également disponibles, mais ne sont pas recommandées.)

      +++Amazon S3

      Indiquez les informations suivantes pour configurer un compte RGPD de rôle Amazon S3 :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ARN du rôle**] | Vous devez fournir un Rôle ARN (nom de ressource Amazon) que l’Adobe peut utiliser pour accéder au compte Amazon S3. Pour ce faire, vous créez une stratégie d’autorisation IAM pour le compte source, vous la joignez à un utilisateur, puis vous créez un rôle pour le compte de destination. Pour plus d’informations, voir [cette documentation AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/).<p>Pour plus d’informations sur la configuration de l’autorisation du compartiment, consultez l’article . [Comment puis-je fournir un accès entre comptes aux objets qui se trouvent dans les compartiments Amazon S3 ?](https://repost.aws/knowledge-center/cross-account-access-s3) dans le centre de connaissances Amazon. |
      | [!UICONTROL **Informations sur l’utilisateur**] | Le User ARN (nom de ressource Amazon) est fourni par Adobe. Vous devez associer cet utilisateur à la stratégie que vous avez créée. |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Indiquez les informations suivantes pour configurer un compte Google Cloud Platform :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Identifiant du projet**] | Identifiant de projet Google Cloud. Voir [Documentation de Google Cloud sur l’obtention d’un ID de projet](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Indiquez les informations suivantes pour configurer un compte Azure SAS :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ID de l’application**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Identifiant du client**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **URI du coffre-fort**] | <p>Chemin d’accès au jeton SAS dans Azure Key Vault.  Pour configurer Azure SAS, vous devez stocker un jeton SAS en tant que secret à l’aide du Key Vault Azure. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Une fois l’URI de coffre-fort de clé créé, ajoutez une stratégie d’accès à Key Vault afin d’accorder l’autorisation sur l’application Azure que vous avez créée. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’affectation d’une stratégie d’accès Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Nom du secret de sécurité**] | Le nom du secret que vous avez créé lors de l’ajout du secret au Key Vault Azure. Dans Microsoft Azure, ces informations se trouvent dans le Key Vault que vous avez créé, sur la page **Key Vault** des pages de paramètres. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Secret**] | Copiez le secret de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Indiquez les informations suivantes pour configurer un compte Azure RBAC :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ID de l’application**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Identifiant du client**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Secret**] | Copiez le secret de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Email

      Indiquez les informations suivantes pour configurer un compte de messagerie :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Destinataires**] | Des notifications électroniques peuvent être envoyées à des utilisateurs spécifiques lors de l’envoi du rapport. Spécifiez une seule adresse électronique ou une liste d’adresses électroniques séparées par des virgules. <!-- How does this differ from the Notification email tab? --> |

   1. Sélectionner [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes : |Field | Fonction | |—|—| | [!UICONTROL **Nom**] | Nom de l’emplacement.  | | [!UICONTROL **Description**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. | | [!UICONTROL **Compte d’emplacement**] | Sélectionnez le compte d’emplacement que vous avez créé dans [Ajout d’un compte](#add-an-account). |

   1. Dans le [!UICONTROL **Propriétés de l’emplacement**] , indiquez les informations spécifiques au type de compte de votre compte d’emplacement.

      Pour obtenir des instructions sur la configuration, développez la section ci-dessous qui correspond à la variable [!UICONTROL **Type de compte**] que vous avez sélectionné précédemment.

      +++Amazon S3

      Indiquez les informations suivantes pour configurer un emplacement Amazon S3 :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du compartiment**] | Le compartiment de votre compte Amazon S3 dans lequel vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous que le User ARN fourni par Adobe a accès aux fichiers de chargement vers ce compartiment. |
      | [!UICONTROL **Préfixe de clé**] | Le dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Indiquez les informations suivantes pour configurer un emplacement de la plateforme Google Cloud :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du compartiment**] | Le compartiment de votre compte GCP où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous que vous avez autorisé l’entité de sécurité fournie par Adobe pour charger des fichiers dans ce compartiment. Pour plus d’informations sur l’octroi d’autorisations, voir [Ajout d’une entité à une stratégie de niveau compartiment](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) dans la documentation de Google Cloud. |
      | [!UICONTROL **Préfixe de clé**] | Le dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Spécifiez les informations suivantes pour configurer un emplacement Azure SAS :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du conteneur**] | Conteneur dans le compte que vous avez spécifié à l’emplacement où vous souhaitez que les données Adobe Analytics soient envoyées. |
      | [!UICONTROL **Préfixe de clé**] | Le dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, `folder_name/` |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Spécifiez les informations suivantes pour configurer un emplacement Azure RBAC :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du conteneur**] | Conteneur dans le compte que vous avez spécifié à l’emplacement où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous d’accorder les autorisations de chargement de fichiers vers l’application Azure que vous avez créée précédemment. |
      | [!UICONTROL **Préfixe de clé**] | Le dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, `folder_name/` |
      | [!UICONTROL **Nom du compte**] | Compte de stockage Azure. |

      {style="table-layout:auto"}

+++

   1. Sélectionnez [!UICONTROL **Enregistrer**].

      Vous pouvez désormais importer des données dans le compte et l’emplacement que vous avez configurés.

1. Poursuivez la configuration de votre requête de Data Warehouse sur le [!UICONTROL **Options de rapport**] . Pour plus d’informations, voir [Configuration des options de rapport pour une requête de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Destinations héritées

>[!IMPORTANT]
>
>Les destinations décrites dans cette section sont héritées et ne sont pas recommandées. Utilisez plutôt l’une des destinations suivantes lors de la création d’une destination d’entrepôt de données : Amazon S3, Google Cloud Platform, Azure RBAC, Azure SAS ou Email. Consultez les informations ci-dessus pour plus d’informations sur chacune de ces destinations recommandées.

Les informations suivantes fournissent des informations de configuration pour chacune des destinations héritées :

### FTP

Les données de l’entrepôt de données peuvent être diffusées vers un emplacement FTP hébergé par un Adobe ou par le client. Nécessite un hôte FTP, un nom d’utilisateur et un mot de passe. Utilisez le champ Chemin d’accès pour placer les fichiers de flux dans un dossier. Les dossiers doivent déjà exister ; les fichiers lancent une erreur si le chemin d’accès précisé n’existe pas.

Renseignez les informations suivantes lorsque vous renseignez les champs disponibles :

#### Champs du compte

* [!UICONTROL **Nom du compte**]: nom du compte FTP.

* [!UICONTROL **Description du compte**]: description du compte FTP.

* [!UICONTROL **Hostname**]: saisissez l’URL de destination FTP de votre choix. Par exemple : `ftp.company.com`.

  >[!NOTE]
  >
  >  Ne pas inclure `ftp://` au début de l’URL.

* [!UICONTROL **Nom d’utilisateur**]: saisissez le nom d’utilisateur pour vous connecter au site FTP.

* [!UICONTROL **Mot de passe et confirmation du mot de passe**]: saisissez le mot de passe de connexion au site FTP.

#### Champs d’emplacement

* [!UICONTROL **Nom de l’emplacement**]: nom de l’emplacement sur le compte FTP où vous souhaitez envoyer les fichiers.

* [!UICONTROL **Description de l’emplacement**]: description de l’emplacement sur le compte FTP.

* [!UICONTROL **Chemin du répertoire**]: chemin d’accès à l’emplacement sur le compte FTP.

### SFTP

La prise en charge SFTP de l’entrepôt de données est disponible. Nécessite un hôte SFTP, un nom d’utilisateur et un site de destination contenant une clé publique RSA ou DSA. Vous pouvez télécharger la clé publique appropriée lors de la création de la destination de l’entrepôt de données.

Renseignez les informations suivantes lorsque vous renseignez les champs disponibles :

#### Champs du compte

* [!UICONTROL **Nom du compte**]: nom du compte FTP.

* [!UICONTROL **Description du compte**]: description du compte FTP.

* [!UICONTROL **Hostname**]: saisissez l’URL de destination SFTP de votre choix. Par exemple : `sftp.company.com`.

  >[!NOTE]
  >
  >  Ne pas inclure `sftp://` au début de l’URL.

* [!UICONTROL **Nom d’utilisateur**]: saisissez le nom d’utilisateur pour vous connecter au site SFTP.

* [!UICONTROL **Utilisation d’extensions de fichier temporaires lors du transfert**]: lorsqu’elle est activée, la variable `.part` L’extension de fichier est utilisée pendant le processus de chargement. Laissez cette option activée, sauf si votre serveur SFTP empêche la modification des noms de fichier une fois le transfert terminé.

* [!UICONTROL **Clés publiques**]: téléchargez la clé publique appropriée lors de la création de la destination de l’entrepôt de données.

#### Champs d’emplacement

* [!UICONTROL **Nom de l’emplacement**]: nom de l’emplacement sur le compte SFTP où vous souhaitez envoyer les fichiers.

* [!UICONTROL **Description de l’emplacement**]: description de l’emplacement sur le compte SFTP.

* [!UICONTROL **Chemin du répertoire**]: chemin d’accès à l’emplacement sur le compte SFTP.

Pour plus d’informations sur la configuration SFTP, voir [Envoi de requêtes de Data Warehouse aux serveurs SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

Vous pouvez envoyer des données d’entrepôt directement aux compartiments Amazon S3. Ce type de destination requiert un nom de compartiment, un identifiant de clé d’accès et une clé secrète. Consultez les [conditions d’attribution de noms pour des compartiments Amazon S3](https://docs.aws.amazon.com/fr_fr/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) dans les documents Amazon S3 pour plus d’informations.

L’utilisateur que vous fournissez pour charger des données de l’entrepôt de données doit disposer des éléments suivants : [permissions](https://docs.aws.amazon.com/fr_fr/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

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

L’entrepôt de données prend en charge les destinations Azure Blob. Nécessite un conteneur, un compte et une clé. Amazon chiffre automatiquement les données au repos. Les données que vous téléchargez sont automatiquement déchiffrées. Pour en savoir plus, consultez [Création d’un compte Azure Storage](https://docs.microsoft.com/fr-fr/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) dans la documentation Microsoft Azure.

>[!NOTE]
>
>Vous devez mettre en oeuvre votre propre processus pour gérer l’espace disque sur la destination de l’entrepôt de données. Adobe ne supprime pas les données du serveur.
