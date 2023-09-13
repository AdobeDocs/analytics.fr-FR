---
description: Description de la procédure de création d’une demande Data Warehouse.
title: Configuration d’une destination de rapport pour une requête de Data Warehouse
feature: Data Warehouse
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 7%

---

# Configuration d’une destination de rapport pour une requête de Data Warehouse

{{release-limited-testing}}

Plusieurs options de configuration sont disponibles lors de la création d’une requête de Data Warehouse. Les informations suivantes expliquent comment configurer une destination de rapport pour la requête.

Pour plus d’informations sur la façon de commencer à créer une requête, ainsi que des liens vers d’autres options de configuration importantes, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Tenez compte des points suivants lors de la configuration d’une destination de rapport :
>
>* Nous vous recommandons d’utiliser un compte cloud ou un e-mail pour votre destination de rapport. Les comptes FTP et SFTP hérités sont disponibles, mais ne sont pas recommandés.
>
>* Les comptes cloud sont associés à votre compte utilisateur Adobe Analytics. Les autres utilisateurs ne peuvent pas utiliser ni afficher les comptes cloud que vous configurez.
>
>* Tout compte cloud que vous avez précédemment [configuré pour les flux de données](/help/export/analytics-data-feed/create-feed.md) sont disponibles pour Data Warehouse.
>
>* Comptes cloud configurés pour [importation de données de classification Adobe Analytics](/help/components/locations/locations-manager.md) d’une destination cloud peut être utilisée lors de la configuration d’une destination de rapport. Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés.

Pour configurer la destination vers laquelle les rapports de Data Warehouse sont envoyés :

1. Commencez à créer une requête dans Adobe Analytics en sélectionnant **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Ajouter**].

   Pour plus d’informations, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Sur la page Nouvelle requête de Data Warehouse , sélectionnez le [!UICONTROL **Destination du rapport**] .

   ![Onglet Destination du rapport](assets/dw-report-destination.png)

1. (Conditionnel) Si vous avez précédemment configuré un compte (et une destination sur ce compte) que vous souhaitez utiliser comme destination de votre rapport :

   1. Sélectionnez le compte dans la [!UICONTROL **Sélectionner un compte**] menu déroulant.

      Tout compte cloud que vous avez configuré pour [importation de données de classification Adobe Analytics](/help/components/locations/locations-manager.md) d’une destination cloud s’affiche ici et peut être utilisée. Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés. Ajoutez plutôt une nouvelle destination comme décrit ci-dessous.

   1. Sélectionnez la destination associée au compte à partir de la [!UICONTROL **Sélectionner la destination**] menu déroulant. <!-- Is this correct? -->

1. (Conditionnel) Si vous n’avez pas configuré de compte auparavant :

   1. Sélectionner [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Type de compte**] | Sélectionnez le type de compte cloud. Nous vous recommandons de disposer d’un compte unique pour chaque type de compte, avec plusieurs emplacements selon les besoins dans ce compte. <p>Après avoir choisi un type de compte, des champs spécifiques à ce type de compte s’affichent. Pour obtenir des instructions de configuration pour chaque type de compte, développez la section ci-dessous correspondant au que vous avez sélectionné. </p> |
      | [!UICONTROL **Nom du compte**] | Attribuez un nom au compte. Ce nom apparaît lors de la création d’un emplacement. <!-- true? --> |
      | [!UICONTROL **Description du compte**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. |

      Pour obtenir des instructions sur la configuration, développez la section ci-dessous qui correspond à la variable [!UICONTROL **Type de compte**] que vous avez sélectionné.

      Utilisez l’un des types de compte suivants lors de la configuration d’une destination de rapport. Pour obtenir des instructions sur la configuration, développez le type de compte. (Autres destinations héritées) <!-- add link --> sont également disponibles, mais ne sont pas recommandées.)

      +++Amazon S3

      Indiquez les informations suivantes pour configurer un compte RGPD de rôle Amazon S3 :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ARN du rôle**] | Vous devez fournir un Rôle ARN (nom de ressource Amazon) que l’Adobe peut utiliser pour accéder au compte Amazon S3. Pour ce faire, vous créez une stratégie d’autorisation IAM pour le compte source, vous la joignez à un utilisateur, puis vous créez un rôle pour le compte de destination. Pour plus d’informations, voir [cette documentation AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
      | [!UICONTROL **ARN de l’utilisateur ou de l’utilisatrice**] | Le User ARN (nom de ressource Amazon) est fourni par Adobe. Vous devez associer cet utilisateur à la stratégie que vous avez créée. |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Indiquez les informations suivantes pour configurer un compte Google Cloud Platform :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Identifiant du projet**] | Identifiant de projet Google Cloud. Voir [Documentation de Google Cloud sur l’obtention d’un ID de projet](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++SAS Azure

      Indiquez les informations suivantes pour configurer un compte Azure SAS :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ID d’application**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID de cliente ou client**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **URI du coffre de clés**] | <p>Chemin d’accès au jeton SAS dans Azure Key Vault.  Pour configurer Azure SAS, vous devez stocker un jeton SAS en tant que secret à l’aide du Key Vault Azure. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Une fois l’URI de coffre-fort de clé créé, ajoutez une stratégie d’accès à Key Vault afin d’accorder l’autorisation sur l’application Azure que vous avez créée. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’affectation d’une stratégie d’accès Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Nom secret du coffre de clés**] | Le nom du secret que vous avez créé lors de l’ajout du secret au Key Vault Azure. Dans Microsoft Azure, ces informations se trouvent dans le Key Vault que vous avez créé, sur la page **Key Vault** des pages de paramètres. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Secret**] | Copiez le secret de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++RBAC Azure

      Indiquez les informations suivantes pour configurer un compte Azure RBAC :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **ID d’application**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID de cliente ou client**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Secret**] | Copiez le secret de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Adresse électronique

      Indiquez les informations suivantes pour configurer un compte de messagerie :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Destinataires**] | Des notifications par e-mail peuvent être envoyées à des personnes spécifiques lorsque le rapport est envoyé. Spécifiez une seule adresse e-mail ou une liste d’adresses e-mail séparées par des virgules. <!-- How does this differ from the Notification email tab? --> |

   1. Sélectionner [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes : |Field | Fonction | |—|—| | [!UICONTROL **Nom**] | Nom de l’emplacement.  | | [!UICONTROL **Description**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. | | [!UICONTROL **Compte d’emplacement**] | Sélectionnez le compte d’emplacement que vous avez créé dans [Ajout d’un compte](#add-an-account). |

   1. Dans le [!UICONTROL **Propriétés de l’emplacement**] , indiquez les informations spécifiques au type de compte de votre compte d’emplacement.

      Pour obtenir des instructions sur la configuration, développez la section ci-dessous qui correspond au type de compte que vous avez sélectionné précédemment.

      +++Amazon S3

      Indiquez les informations suivantes pour configurer un emplacement Amazon S3 :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du compartiment**] | Le compartiment de votre compte Amazon S3 dans lequel vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous que le User ARN fourni par Adobe a accès aux fichiers de chargement vers ce compartiment. |
      | [!UICONTROL **Préfixe clé**] | Le dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Indiquez les informations suivantes pour configurer un emplacement de la plateforme Google Cloud :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du compartiment**] | Le compartiment de votre compte GCP où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous que vous avez autorisé l’entité de sécurité fournie par Adobe pour charger des fichiers dans ce compartiment. Pour plus d’informations sur l’octroi d’autorisations, voir [Ajout d’une entité à une stratégie de niveau compartiment](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) dans la documentation de Google Cloud. |
      | [!UICONTROL **Préfixe clé**] | Le dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

      {style="table-layout:auto"}

+++

      +++SAS Azure

      Spécifiez les informations suivantes pour configurer un emplacement Azure SAS :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du conteneur**] | Conteneur dans le compte que vous avez spécifié à l’emplacement où vous souhaitez que les données Adobe Analytics soient envoyées. |
      | [!UICONTROL **Préfixe clé**] | Le dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier.   Par exemple : `folder_name/` |

      {style="table-layout:auto"}

+++

      +++RBAC Azure

      Spécifiez les informations suivantes pour configurer un emplacement Azure RBAC :

      | Champ | Fonction |
      |---------|----------|
      | [!UICONTROL **Nom du conteneur**] | Conteneur dans le compte que vous avez spécifié à l’emplacement où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous d’accorder les autorisations de chargement de fichiers vers l’application Azure que vous avez créée précédemment. |
      | [!UICONTROL **Préfixe clé**] | Le dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier.   Par exemple : `folder_name/` |
      | [!UICONTROL **Nom du compte**] | Compte de stockage Azure. |

      {style="table-layout:auto"}

+++

   1. Sélectionnez [!UICONTROL **Enregistrer**].

      Vous pouvez désormais importer des données dans le compte et l’emplacement que vous avez configurés.

1. Poursuivez la configuration de votre requête de Data Warehouse sur le [!UICONTROL **Options de rapport**] . Pour plus d’informations, voir [Configuration des options de rapport pour une requête de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).