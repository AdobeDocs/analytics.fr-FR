---
description: Configurez le compte d’importation cloud et l’emplacement où les données de classification peuvent être chargées
keywords: Analysis Workspace
title: Configuration des comptes d’import et d’export cloud
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: f0a5f72667fd6fc7847ede82d5196d9159fc558c
workflow-type: tm+mt
source-wordcount: '1489'
ht-degree: 56%

---

# Configuration des comptes d’import et d’export cloud

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>Tenez compte des points suivants lors de la création et de la modification de comptes : <ul><li>Les administrateurs système peuvent empêcher les utilisateurs de créer des comptes, comme décrit dans la section [Configurer si les utilisateurs peuvent créer des comptes](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Si vous ne pouvez pas créer de comptes comme décrit dans cette section, contactez votre administrateur système.</li><li>Un compte ne peut être modifié que par l’utilisateur qui l’a créé ou par un administrateur système.</li></ul>

Vous pouvez configurer un compte cloud utilisé à l’une ou à l’autre des fins suivantes, ou à toutes les fins suivantes :

* Exportation de fichiers à l’aide de [Flux de données](/help/export/analytics-data-feed/create-feed.md)
* Exportation de rapports à l&#39;aide de [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Exportation de fichiers lors de l’utilisation de [Report Builder](/help/analyze/report-builder/report-builder-export.md)
* Importation de schémas à l’aide de [ensembles de classifications](/help/components/classifications/sets/overview.md)

Vous devez configurer Adobe Analytics avec les informations nécessaires pour accéder à votre compte cloud. Ce processus consiste à ajouter et à configurer le compte (tel que le rôle Amazon S3 ARN, Google Cloud Platform, etc.) comme décrit dans cet article, puis à ajouter et à configurer l’emplacement au sein de ce compte (tel qu’un dossier dans le compte) comme décrit dans [Configurer les emplacements d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-locations.md).

Pour plus d’informations sur l’affichage et la suppression des comptes existants, voir [Gestionnaire d’emplacements](/help/components/locations/locations-manager.md).

Pour configurer un compte d’import ou d’export cloud :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Emplacements**].
1. Sur la page [!UICONTROL Emplacements], sélectionnez l’onglet [!UICONTROL **Comptes d’emplacement**].
1. (Conditionnel) Si vous êtes un administrateur système, vous pouvez activer l’option [!UICONTROL **Afficher les comptes de tous les utilisateurs**] pour afficher les comptes créés par tous les utilisateurs de votre organisation.
   ![afficher les comptes de tous les utilisateurs](assets/accounts-all-users.png)
1. Pour créer un compte, sélectionnez [!UICONTROL **Ajouter un compte**].

   La boîte de dialogue [!UICONTROL **Détails du compte d’emplacement**] s’affiche.

   Ou

   Pour modifier un compte existant, recherchez le compte à modifier, puis cliquez sur le bouton [!UICONTROL **Modifier les détails**].

   La boîte de dialogue [!UICONTROL **Ajouter un compte**] s’affiche.

1. Indiquez les informations suivantes :

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

   **REMARQUE :** lors de l’utilisation d’Amazon S3 avec des flux de données et Data Warehouse, seul le chiffrement SSE-S3 est pris en charge.

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
   | [!UICONTROL **URI du coffre de clés**] | <p>Chemin d’accès au jeton SAS dans Azure Key Vault.  Pour configurer Azure SAS, vous devez stocker un jeton SAS en tant que secret à l’aide d’Azure Key Vault. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Une fois l’URI du coffre de clés créé, ajoutez une politique d’accès au coffre de clés pour accorder l’autorisation à l’application Azure que vous avez créée. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’affectation d’une politique d’accès Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
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
   >Les comptes de messagerie peuvent être utilisés uniquement avec [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). (Les comptes de messagerie ne sont pas pris en charge avec les [Flux de données](/help/export/analytics-data-feed/create-feed.md) ou [Ensembles de classifications](/help/components/classifications/sets/overview.md)).

   Pour configurer un compte Azure RBAC, spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Personnes destinataires**] | Des notifications par e-mail peuvent être envoyées à des personnes spécifiques lorsque le rapport est envoyé. Spécifiez une seule adresse e-mail ou une liste d’adresses e-mail séparées par des virgules. |

   {style="table-layout:auto"}

   +++

   **Types de compte hérités**

   Ces types de compte hérités ne sont disponibles que lors de l’exportation de données avec [Flux de données](/help/export/analytics-data-feed/create-feed.md) et [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Ces options ne sont pas disponibles lors de l’importation de données avec des [ensembles de classifications](/help/components/classifications/sets/manage/schema.md).

   +++FTP

   Les données des flux de données peuvent être diffusées vers un emplacement Adobe ou FTP hébergé par le client. Nécessite un hôte FTP, un nom d’utilisateur et un mot de passe. Utilisez le champ Chemin d’accès pour placer les fichiers de flux dans un dossier. Les dossiers doivent déjà exister ; les fichiers lancent une erreur si le chemin d’accès précisé n’existe pas.

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Hôte**] | Saisissez l’URL de destination FTP souhaitée. Par exemple : `ftp.adobe.com`. |
   | [!UICONTROL **Chemin d’accès**] | Peut être laissé vide. |
   | [!UICONTROL **Nom d’utilisateur**] | Saisissez le nom d’utilisateur pour vous connecter au site FTP. |
   | [!UICONTROL **Mot de passe et confirmer le mot de passe**] | Saisissez le mot de passe de connexion au site FTP. |

   {style="table-layout:auto"}

   +++

   +++SFTP

   La prise en charge SFTP des flux de données est disponible. Nécessite un hôte SFTP, un nom d’utilisateur et un site de destination contenant une clé publique RSA ou DSA. Vous pouvez télécharger la clé publique appropriée à la création du flux.

   +++

   +++S3

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

   +++

   +++Azure Blob

   Data Warehouse prend en charge les destinations Azure Blob. Nécessite un conteneur, un compte et une clé. Amazon chiffre automatiquement les données au repos. Les données que vous téléchargez sont automatiquement déchiffrées. Pour en savoir plus, consultez [Création d’un compte Azure Storage](https://docs.microsoft.com/fr-fr/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) dans la documentation Microsoft Azure.

   >[!NOTE]
   >
   >Vous devez mettre en œuvre votre propre processus pour gérer l’espace disque sur la destination d’entrepôt de données. Adobe ne supprime pas les données du serveur.

   +++

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Continuez avec [Configuration des emplacements d’import et d’export cloud](/help/components/locations/configure-import-locations.md).
