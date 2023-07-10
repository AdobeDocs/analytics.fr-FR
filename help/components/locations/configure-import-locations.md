---
description: Configuration du compte d’importation dans le cloud et de l’emplacement où les données de classification peuvent être chargées
keywords: Analysis Workspace
title: Configuration des emplacements d’importation dans le cloud
feature: Classifications
source-git-commit: 4efb0623d734419c376ca5f2bf2bbd94097ee4e4
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 8%

---

# Configuration des emplacements d’importation dans le cloud

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Avant de pouvoir importer des données de classification Adobe Analytics à partir d’une destination cloud, vous devez ajouter et configurer le compte et l’emplacement dans ce compte où vous souhaitez que les données de classification soient collectées.

Ce processus consiste à ajouter et à configurer le compte (par exemple, APNS de rôle Amazon S3, Google Cloud Platform, etc.) et l’emplacement dans le compte (par exemple, un dossier dans le compte).

Pour configurer un emplacement d’importation dans le cloud :

1. Vous devez ajouter un compte avant de pouvoir ajouter un emplacement. Si ce n’est déjà fait, ajoutez un compte comme décrit à la section [Configuration des comptes d’importation dans le cloud](/help/components/locations/configure-import-accounts.md).
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