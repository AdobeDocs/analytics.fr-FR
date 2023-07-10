---
description: Configuration du compte d’importation dans le cloud et de l’emplacement où les données de classification peuvent être chargées
keywords: Analysis Workspace
title: Configuration des emplacements d’importation dans le cloud
feature: Classifications
source-git-commit: 8d6ee33e867da274334c8adc557105af4942c894
workflow-type: tm+mt
source-wordcount: '1356'
ht-degree: 6%

---

# Configuration des emplacements d’importation dans le cloud

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Avant de pouvoir importer des données de classification Adobe Analytics à partir d’une destination cloud, vous devez ajouter et configurer l’emplacement où vous souhaitez que les données de classification soient collectées.

Ce processus consiste à ajouter et à configurer le compte (par exemple, APNS de rôle Amazon S3, Google Cloud Platform, etc.) et l’emplacement dans le compte (par exemple, un dossier dans le compte).

## Ajout d’un compte

Vous devez configurer Adobe Analytics avec les informations nécessaires pour accéder à votre compte de destination cloud.

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Emplacements**].
1. Sur le [!UICONTROL Emplacements] , sélectionnez [!UICONTROL **Informations d’identification de l’emplacement**] .
1. Sélectionner [!UICONTROL **Ajouter un compte**]. <!-- add screenshot? -->

   La boîte de dialogue Ajouter un compte s’affiche.
1. Indiquez les informations suivantes : |Field | Fonction | |—|—| | [!UICONTROL **Nom du compte d’emplacement**] | Nom du compte de l’emplacement. Ce nom apparaît lors de la création d’un emplacement. | | [!UICONTROL **Description du compte d’emplacement**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. | | [!UICONTROL **Type de compte**] | Sélectionnez le type de compte cloud. Nous vous recommandons de disposer d’un compte unique pour chaque type de compte, avec plusieurs emplacements selon les besoins dans ce compte. |
1. Dans le [!UICONTROL **Propriétés du compte**] , indiquez les informations spécifiques au type de compte sélectionné.

   Pour obtenir des instructions sur la configuration, développez la section ci-dessous qui correspond à la variable [!UICONTROL **Type de compte**] que vous avez sélectionné.

   +++Amazon S3 Role ARN

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
   | [!UICONTROL **Clé du compte d’emplacement**] | Copiez le secret de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++RBAC Azure

   Indiquez les informations suivantes pour configurer un compte Azure RBAC :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **ID d’application**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID de cliente ou client**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Clé du compte d’emplacement**] | Copiez le secret de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

1. Sélectionnez [!UICONTROL **Enregistrer**].

1. Passez à la [Ajouter un emplacement](#add-a-location).

## Ajouter un emplacement

1. Vous devez ajouter un compte avant de pouvoir ajouter un emplacement. [Ajout d’un compte](#add-an-account) si vous ne l&#39;avez pas déjà fait.
1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Emplacements**].
1. Sur le [!UICONTROL Emplacements] , sélectionnez [!UICONTROL **Emplacements**] .
1. Sélectionner [!UICONTROL **Ajouter un emplacement**]. <!-- add screenshot? -->

   La boîte de dialogue Emplacement s’affiche.
1. Indiquez les informations suivantes : |Field | Fonction | |—|—| | [!UICONTROL **Nom**] | Nom de l’emplacement.  | | [!UICONTROL **Description**] | Fournissez une brève description du compte pour le différencier des autres comptes du même type de compte. | | [!UICONTROL **Compte d’emplacement**] | Sélectionnez le compte d’emplacement que vous avez créé dans [Ajout d’un compte](#add-an-account). |

1. Dans le [!UICONTROL **Propriétés de l’emplacement**] , indiquez les informations spécifiques au type de compte de votre compte d’emplacement.

   Pour obtenir des instructions sur la configuration, développez la section ci-dessous qui correspond au type de compte que vous avez sélectionné dans le [!UICONTROL **Comptes d’emplacement**] champ .

   +++Amazon S3 Role ARN

   Indiquez les informations suivantes pour configurer un emplacement d’acquisition du rôle Amazon S3 :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom du compartiment**] | Le compartiment de votre compte Amazon S3 dans lequel vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous que le User ARN fourni par Adobe a accès aux fichiers de chargement vers ce compartiment. |
   | [!UICONTROL **Préfixe clé**] | Dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Indiquez les informations suivantes pour configurer un emplacement de la plateforme Google Cloud :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom du compartiment**] | Le compartiment de votre compte GCP où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous que vous avez autorisé l’entité de sécurité fournie par Adobe pour charger des fichiers dans ce compartiment. |
   | [!UICONTROL **Préfixe clé**] | Dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, folder_name/ |

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