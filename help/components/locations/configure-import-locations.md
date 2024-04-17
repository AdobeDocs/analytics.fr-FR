---
description: Configuration du compte d’importation dans le cloud et de l’emplacement où les données de classification peuvent être chargées
keywords: Analysis Workspace
title: Configuration des emplacements d’importation et d’exportation dans le cloud
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: c81f0b8dffe07789fce1dda6efcb5ce17406be71
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 40%

---

# Configuration des emplacements d’importation et d’exportation dans le cloud

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Vous pouvez configurer un compte cloud (et un emplacement sur ce compte). Un seul emplacement peut être utilisé à l’un des usages suivants (un seul emplacement ne peut pas être associé à plusieurs fins, comme les flux de données et Data Warehouse, ou les ensembles de Data Warehouse et de classifications) :

* Exportation de fichiers à l’aide de [Flux de données](/help/export/analytics-data-feed/create-feed.md)
* Exporter des rapports à l’aide de [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Import de schémas à l’aide de [Jeux de classifications](/help/components/classifications/sets/overview.md)

Vous devez configurer Adobe Analytics avec les informations nécessaires pour accéder à votre compte cloud. Ce processus consiste à ajouter et à configurer le compte (comme l’APNS de rôle Amazon S3, Google Cloud Platform, etc.), comme décrit dans la section [Configuration de comptes d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-accounts.md), puis ajouter et configurer l’emplacement dans ce compte (comme décrit dans cet article).

Pour configurer un nouvel emplacement d’importation ou d’exportation dans le cloud ou pour en modifier un existant :

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Emplacements**].
1. Sur le [!UICONTROL Emplacements] , sélectionnez [!UICONTROL **Emplacements**] .
1. Pour créer un emplacement, sélectionnez [!UICONTROL **Ajouter un emplacement**]. (Si vous n’avez pas encore ajouté de compte, ajoutez-en un, comme décrit à la section [Configuration de comptes d’importation et d’exportation dans le cloud](/help/components/locations/configure-import-accounts.md).)

   Ou

   Pour modifier un emplacement existant, sélectionnez le menu à 3 points dans le [!UICONTROL **Nom de l’emplacement**] pour l’emplacement à modifier, puis sélectionnez [!UICONTROL **Modifier**].
La boîte de dialogue Emplacement s’affiche.

1. Indiquez les informations suivantes : |Field | Fonction | |—|—| | [!UICONTROL **Nom**] | Nom de l’emplacement.  |
| [!UICONTROL **Description**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. | | [!UICONTROL **Utilisation avec**] | Indiquez si vous souhaitez utiliser cet emplacement avec [!UICONTROL **Flux de données**], [!UICONTROL **Data Warehouse**], ou [!UICONTROL **Jeux de classifications**]. <p>Tenez compte des points suivants lors d’une sélection :</p><ul><li>Un seul emplacement ne peut pas être utilisé à plusieurs fins. Par exemple, un emplacement utilisé pour les flux de données ne peut pas également être utilisé pour les jeux de Data Warehouse ou de classifications.</li><li>Pour éviter des conflits de fichiers dans un emplacement, ne modifiez pas la valeur de la variable [!UICONTROL **Utilisation avec**] une fois l’emplacement utilisé.</li></ul> | | [!UICONTROL **Compte d’emplacement**] | Sélectionnez le compte d’emplacement dans lequel vous souhaitez créer cet emplacement. Pour plus d’informations sur la création d’un compte, voir [Ajout d’un compte](#add-an-account). |

1. Dans la section [!UICONTROL **Propriétés d’emplacement**], indiquez les informations spécifiques au type de votre compte d’emplacement.

   Pour obtenir des instructions sur la configuration, développez la section ci-dessous qui correspond au type de compte que vous avez sélectionné dans le [!UICONTROL **Comptes d’emplacement**] champ . (D’autres types de compte hérités sont également disponibles, mais ne sont pas recommandés.)

   **Types de compte**

   +++APERÇU du rôle Amazon S3

   Pour configurer un emplacement d’acquisition du rôle Amazon S3, spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom du compartiment**] | Compartiment de votre compte Amazon S3 dans lequel vous souhaitez que les données Adobe Analytics soient envoyées. |
   | [!UICONTROL **Préfixe clé**] | Dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Pour configurer un emplacement Google Cloud Platform, spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom du compartiment**] | Le compartiment de votre compte GCP où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous que vous avez autorisé l’entité de sécurité fournie par Adobe pour charger des fichiers dans ce compartiment. |
   | [!UICONTROL **Préfixe clé**] | Dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Pour configurer un emplacement Azure SAS, spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom du conteneur**] | Conteneur dans le compte que vous avez spécifié où vous souhaitez que les données Adobe Analytics soient envoyées. |
   | [!UICONTROL **Préfixe de clé**] | Dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Pour configurer un emplacement Azure RBAC, spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom du conteneur**] | Conteneur dans le compte que vous avez spécifié où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous d’accorder les autorisations de chargement de fichiers vers l’application Azure que vous avez créée précédemment. |
   | [!UICONTROL **Préfixe de clé**] | Dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, `folder_name/` |
   | [!UICONTROL **Nom du compte**] | Compte de stockage Azure. |

   {style="table-layout:auto"}

+++

   **Types de compte hérités**

   Ces types de compte hérités ne sont disponibles que lors de l’exportation de données avec [Flux de données](/help/export/analytics-data-feed/create-feed.md) et [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Ces options ne sont pas disponibles lors de l’importation de données avec [Jeux de classifications](/help/components/classifications/sets/manage/schema.md).

   +++FTP

   Les données de flux de données peuvent être diffusées vers un emplacement FTP hébergé par un Adobe ou par le client. Spécifiez le répertoire Utilisez le champ de chemin pour placer les fichiers de flux dans un dossier.

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Chemin du répertoire**] | Saisissez le chemin d’accès au répertoire sur le serveur FTP. Les dossiers doivent déjà exister ; les flux génèrent une erreur si le chemin spécifié n’existe pas. </br>Par exemple : `/folder_name/folder_name`. |

   {style="table-layout:auto"}

+++

   +++SFTP

   Les données de flux de données peuvent être diffusées vers un emplacement SFTP hébergé par un Adobe ou par le client. Le site de destination doit contenir une clé publique RSA ou DSA valide. Vous pouvez télécharger la clé publique appropriée à la création du flux.

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Chemin du répertoire**] | Saisissez le chemin d’accès au répertoire sur le serveur FTP. Les dossiers doivent déjà exister ; les flux génèrent une erreur si le chemin spécifié n’existe pas. </br>Par exemple : `/folder_name/folder_name`. |

   {style="table-layout:auto"}

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

   Les entrepôts de données prennent en charge les destinations Azure Blob. Nécessite un conteneur, un compte et une clé. Amazon chiffre automatiquement les données au repos. Les données que vous téléchargez sont automatiquement déchiffrées. Pour en savoir plus, consultez [Création d’un compte Azure Storage](https://docs.microsoft.com/fr-fr/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) dans la documentation Microsoft Azure.

   >[!NOTE]
   >
   >Vous devez mettre en œuvre votre propre processus pour gérer l’espace disque sur la destination d’entrepôt de données. Adobe ne supprime pas les données du serveur.

+++

1. Sélectionnez [!UICONTROL **Enregistrer**].

   Vous pouvez désormais importer ou exporter des données vers ou depuis le compte et l’emplacement que vous avez configurés.

   Les données importées ne sont pas supprimées de la destination cloud après leur importation.

   >[!NOTE]
   >
   >   Si vous avez précédemment utilisé [FTP pour importer des classifications](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) dans Adobe Analytics, vous devez télécharger un fichier FIN. Ce fichier FIN n’est pas nécessaire lors de l’importation à partir de comptes cloud.

