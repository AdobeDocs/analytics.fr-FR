---
title: Création d’un flux de données
description: Découvrez comment créer un flux de données.
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: d9b1caf1edf473461d176d472f6f73c04cc1dbad
workflow-type: tm+mt
source-wordcount: '3174'
ht-degree: 21%

---

# Création d’un flux de données

Lors de la création d’un flux de données, vous fournissez l’Adobe avec :

* Informations sur la destination vers laquelle vous souhaitez envoyer les fichiers de données brutes.

* Les données à inclure dans chaque fichier

>[!NOTE]
>
>Avant de créer un flux de données, il est important de posséder une compréhension de base des flux de données et de vous assurer que vous remplissez toutes les conditions préalables requises. Pour plus d’informations, voir [Flux de données - Aperçu](data-feed-overview.md).

## Création et configuration d’un flux de données

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Sélectionnez l’icône de 9 carrés dans le coin supérieur droit, puis sélectionnez [!UICONTROL **Analytics**].
1. Dans la barre de navigation supérieure, accédez à [!UICONTROL **Administration**] > [!UICONTROL **Flux de données**].
1. Sélectionner [!UICONTROL **Ajouter**].

   ![Ajout d’un flux de données](assets/datafeed-add.png)

   Une page s’affiche avec trois catégories principales : [!UICONTROL **Informations sur le flux**], [!UICONTROL **Destination**], et [!UICONTROL **Définitions des colonnes de données**].
1. Dans le [!UICONTROL **Informations sur le flux**] , renseignez les champs suivants :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom**] | Nom du flux de données. Doit être unique au sein de la suite de rapports sélectionnée et peut comporter jusqu’à 255 caractères. |
   | [!UICONTROL **Suite de rapports**] | Suite de rapports sur laquelle le flux de données est basé. Si plusieurs flux de données sont créés pour une même suite de rapports, ils doivent avoir des définitions de colonne différentes. Seules les suites de rapports source prennent en charge les flux de données ; les suites de rapports virtuelles ne sont pas prises en charge. |
   | [!UICONTROL **Envoyer un courrier électronique à la fin**] | L’adresse électronique à laquelle envoyer une notification lorsqu’un flux termine le traitement. L’adresse e-mail doit être correctement formatée. |
   | [!UICONTROL **Intervalle du flux**] | Sélectionner **Qualité** pour les données de renvoi ou historiques. Les flux quotidiens contiennent l’équivalent d’une journée complète de données, de minuit à minuit, dans le fuseau horaire de la suite de rapports.  Sélectionner **Horaire** pour les données continues (le quotidien est également disponible pour les flux continus si vous préférez). Les flux horaires contiennent l’équivalent d’une seule heure de données. |
   | [!UICONTROL **Traitement du délai**] | Patientez un certain temps avant de traiter un fichier de flux de données. Il peut être utile de mettre en place un délai pour donner aux appareils hors ligne la possibilité de se connecter et d’envoyer leurs données dans le cadre d’implémentations mobiles. Il est également possible d’utiliser un délai pour adapter les processus côté serveur de votre entreprise en ce qui concerne la gestion des fichiers traités précédemment. Dans la plupart des cas aucun délai n’est nécessaire. Un flux peut être se voir attribuer un délai pouvant aller jusqu’à 120 minutes. |
   | [!UICONTROL **Dates de début et de fin**] | La date de début indique la première date à laquelle vous souhaitez un flux de données. Définissez cette date dans le passé pour commencer immédiatement à traiter les flux de données des données historiques. Le traitement du flux se poursuit jusqu’à ce que la date de fin soit atteinte. Les dates de début et de fin sont définies en fonction du fuseau horaire de la suite de rapports. |
   | [!UICONTROL **Flux continu**] | Cette case à cocher supprime la date de fin, ce qui permet à un flux de s’exécuter indéfiniment. Lorsqu’un flux termine le traitement de données historiques, un flux attend la fin de la collecte des données pour une heure ou un jour donné. Une fois l’heure ou le jour en question terminé, le traitement commence après le délai indiqué. |

1. Dans le [!UICONTROL **Destination**] , dans la section [!UICONTROL **Type**] , sélectionnez la destination vers laquelle vous souhaitez envoyer les données.

   >[!NOTE]
   >
   >Tenez compte des points suivants lors de la configuration d’une destination de rapport :
   >
   >* Nous vous recommandons d’utiliser un compte cloud pour votre destination de rapport. [Comptes FTP et SFTP hérités](#legacy-destinations) sont disponibles, mais ne sont pas recommandées.
   >
   >* Les comptes cloud sont associés à votre compte utilisateur Adobe Analytics. Les autres utilisateurs ne peuvent pas utiliser ni afficher les comptes cloud que vous configurez.
   >

   ![Menu déroulant de destination des flux de données](assets/datafeed-destinations-dropdown.png)

   Utilisez l’un des types de destination suivants lors de la création d’un flux de données. Pour obtenir des instructions sur la configuration, développez le type de destination. (Additional [destinations héritées](#legacy-destinations) sont également disponibles, mais ne sont pas recommandées.)

   +++Amazon S3

   Il est possible d’envoyer des flux directement vers des compartiments Amazon S3. Ce type de destination nécessite uniquement votre compte Amazon S3 et l’emplacement (compartiment).

   Adobe Analytics utilise l’authentification entre comptes pour charger des fichiers d’Adobe Analytics vers l’emplacement spécifié dans votre instance Amazon S3.

   Pour configurer un compartiment Amazon S3 comme destination d’un flux de données :

   1. Dans la console d’administration d’Adobe Analytics, dans le [!UICONTROL **Destination**] , sélectionnez [!UICONTROL **Amazon S3**].

      ![Destination Amazon S3](assets/datafeed-destination-amazons3.png)

   1. Sélectionner [!UICONTROL **Sélectionner un emplacement**].

      La page Emplacements d’exportation Amazon S3 s’affiche.

   1. (Conditionnel) Si vous avez précédemment ajouté un compte et un emplacement Amazon S3 :

      1. Sélectionnez le compte dans la [!UICONTROL **Sélectionner un compte**] menu déroulant.

      1. Sélectionnez l’emplacement dans la [!UICONTROL **Sélectionner un emplacement**] menu déroulant.

      1. Sélectionner [!UICONTROL **Enregistrer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Amazon S3 que vous avez spécifié.

   1. (Conditionnel) Si vous n’avez pas encore ajouté de compte Amazon S3 :

      1. Sélectionner [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom du compte**] | Nom du compte. Il peut s’agir de n’importe quel nom de votre choix. |
         | [!UICONTROL **Description du compte**] | Description du compte. |
         | [!UICONTROL **ARN du rôle**] | Vous devez fournir un Rôle ARN (nom de ressource Amazon) que l’Adobe peut utiliser pour accéder au compte Amazon S3. Pour ce faire, vous créez une stratégie d’autorisation IAM pour le compte source, vous la joignez à un utilisateur, puis vous créez un rôle pour le compte de destination. Pour plus d’informations, voir [cette documentation AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **ARN de l’utilisateur ou de l’utilisatrice**] | Le User ARN (nom de ressource Amazon) est fourni par Adobe. Vous devez associer cet utilisateur à la stratégie que vous avez créée. |

         {style="table-layout:auto"}

         1. Sélectionner [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom**] | Nom du compte. |
         | [!UICONTROL **Description**] | Description du compte. |
         | [!UICONTROL **Compartiment**] | Le compartiment de votre compte Amazon S3 dans lequel vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous que le User ARN fourni par Adobe a accès aux fichiers de chargement vers ce compartiment. |
         | [!UICONTROL **Préfixe**] | Dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier.   Par exemple : `folder_name/` |

         {style="table-layout:auto"}

      1. Sélectionner [!UICONTROL **Créer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Amazon S3 que vous avez spécifié.

+++

   +++RBAC Azure

   Vous pouvez envoyer des flux directement à un conteneur Azure à l’aide de l’authentification RBAC. Ce type de destination nécessite un nom de compartiment, un identifiant d’application, un identifiant de tenant et une clé secrète.

   Pour configurer un compartiment Azure RBAC comme destination d’un flux de données :

   1. Si ce n’est déjà fait, créez une application Azure qu’Adobe Analytics peut utiliser pour l’authentification, puis accordez des autorisations d’accès dans le contrôle d’accès (IAM).

      Pour plus d’informations, reportez-vous au [Documentation Microsoft Azure sur la création d’une application Azure Principale Directory](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. Dans la console d’administration d’Adobe Analytics, dans le [!UICONTROL **Destination**] , sélectionnez [!UICONTROL **Azure RBAC**].

      ![Destination Azure RBAC](assets/datafeed-destination-azurerbac.png)

   1. Sélectionner [!UICONTROL **Sélectionner un emplacement**].

      La page Emplacements d’exportation Azure RBAC s’affiche.

   1. (Conditionnel) Si vous avez précédemment ajouté un compte et un emplacement Azure RBAC :

      1. Sélectionnez le compte dans la [!UICONTROL **Sélectionner un compte**] menu déroulant.

      1. Sélectionnez l’emplacement dans la [!UICONTROL **Sélectionner un emplacement**] menu déroulant.

      1. Sélectionner [!UICONTROL **Enregistrer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Azure RBAC que vous avez spécifié.

   1. (Conditionnel) Si vous n’avez pas encore ajouté de compte Azure RBAC :

      1. Sélectionner [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom du compte**] | Nom du compte Azure RBAC. Ce nom s’affiche dans la variable [!UICONTROL **Sélectionner un compte**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **Description du compte**] | Description du compte Azure RBAC. Cette description s’affiche dans la variable [!UICONTROL **Sélectionner un compte**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **ID d’application**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **ID de cliente ou client**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Secret**] | Copiez le secret de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Sélectionner [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom**] | Nom de l’emplacement. Ce nom s’affiche dans la variable [!UICONTROL **Sélectionner un emplacement**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **Description**] | Description de l’emplacement. Cette description s’affiche dans la variable [!UICONTROL **Sélectionner un emplacement**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **Compte**] | Compte de stockage Azure. |
         | [!UICONTROL **Conteneur**] | Conteneur dans le compte que vous avez spécifié à l’emplacement où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous d’accorder les autorisations de chargement de fichiers vers l’application Azure que vous avez créée précédemment. |
         | [!UICONTROL **Préfixe**] | Le dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier.   Par exemple : `folder_name/` |

         {style="table-layout:auto"}

      1. Sélectionner [!UICONTROL **Créer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Azure RBAC que vous avez spécifié.

+++

   +++SAS Azure

   Vous pouvez envoyer des flux directement à un conteneur Azure à l’aide de l’authentification SAS. Ce type de destination nécessite un nom de compartiment, un ID d’application, un ID de tenant, un URI de coffre-fort, un nom de secret de clé et une clé secrète.

   Pour configurer un compartiment Azure SAS comme destination d’un flux de données :

   1. Si ce n’est déjà fait, créez une application Azure qu’Adobe Analytics peut utiliser pour l’authentification.

      Pour plus d’informations, reportez-vous au [Documentation Microsoft Azure sur la création d’une application Azure Principale Directory](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. Dans la console d’administration d’Adobe Analytics, dans le [!UICONTROL **Destination**] , sélectionnez [!UICONTROL **Azure SAS**].

      ![Destination Azure SAS](assets/datafeed-destination-azuresas.png)

   1. Sélectionner [!UICONTROL **Sélectionner un emplacement**].

      La page Emplacements d’exportation Azure SAS s’affiche.

   1. (Conditionnel) Si vous avez précédemment ajouté un compte et un emplacement Azure SAS :

      1. Sélectionnez le compte dans la [!UICONTROL **Sélectionner un compte**] menu déroulant.

      1. Sélectionnez l’emplacement dans la [!UICONTROL **Sélectionner un emplacement**] menu déroulant.

      1. Sélectionner [!UICONTROL **Enregistrer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Azure SAS que vous avez spécifié.

   1. (Conditionnel) Si vous n’avez pas encore ajouté de compte Azure SAS :

      1. Sélectionner [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom du compte**] | Nom du compte Azure SAS. Ce nom s’affiche dans la variable [!UICONTROL **Sélectionner un compte**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **Destitution de compte**] | Description du compte Azure SAS. Cette description s’affiche dans la variable [!UICONTROL **Sélectionner un compte**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **ID d’application**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **ID de cliente ou client**] | Copiez cet identifiant de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Présentation** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **URI du coffre de clés**] | <p>Chemin d’accès au jeton SAS dans Azure Key Vault.  Pour configurer Azure SAS, vous devez stocker un jeton SAS en tant que secret à l’aide du Key Vault Azure. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Une fois l’URI de coffre-fort de clé créé, ajoutez une stratégie d’accès à Key Vault afin d’accorder l’autorisation sur l’application Azure que vous avez créée. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’affectation d’une stratégie d’accès Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
         | [!UICONTROL **Nom secret du coffre de clés**] | Le nom du secret que vous avez créé lors de l’ajout du secret au Key Vault Azure. Dans Microsoft Azure, ces informations se trouvent dans le Key Vault que vous avez créé, sur la page **Key Vault** des pages de paramètres. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Secret**] | Copiez le secret de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Sélectionner [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom**] | Nom de l’emplacement. Ce nom s’affiche dans la variable [!UICONTROL **Sélectionner un emplacement**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **Description**] | Description de l’emplacement. Cette description s’affiche dans la variable [!UICONTROL **Sélectionner un emplacement**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **Conteneur**] | Conteneur dans le compte que vous avez spécifié à l’emplacement où vous souhaitez que les données Adobe Analytics soient envoyées. |
         | [!UICONTROL **Préfixe**] | Le dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier.   Par exemple : `folder_name/` |

         {style="table-layout:auto"}

      1. Sélectionner [!UICONTROL **Créer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Azure SAS que vous avez spécifié.

+++

   +++Google Cloud Platform

   Vous pouvez envoyer des flux directement aux compartiments Google Cloud Platform (GCP). Ce type de destination nécessite uniquement le nom de votre compte GCP et le nom de l’emplacement (compartiment).

   Adobe Analytics utilise l’authentification entre comptes pour charger des fichiers d’Adobe Analytics vers l’emplacement spécifié dans votre instance GCP.

   Pour configurer un compartiment GCP comme destination d’un flux de données :

   1. Dans la console d’administration d’Adobe Analytics, dans le [!UICONTROL **Destination**] , sélectionnez [!UICONTROL **Google Cloud Platform**].

      ![Destination Google Cloud Platform](assets/datafeed-destination-gcp.png)

   1. Sélectionner [!UICONTROL **Sélectionner un emplacement**].

      La page Emplacements d’exportation GCP s’affiche.

   1. (Conditionnel) Si vous avez précédemment ajouté un compte et un emplacement GCP :

      1. Sélectionnez le compte dans la [!UICONTROL **Sélectionner un compte**] menu déroulant.

      1. Sélectionnez l’emplacement dans la [!UICONTROL **Sélectionner un emplacement**] menu déroulant.

      1. Sélectionner [!UICONTROL **Enregistrer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement GCP que vous avez spécifié.

   1. (Conditionnel) Si vous n’avez pas encore ajouté de compte GCP :

      1. Sélectionner [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom du compte**] | Nom du compte. Il peut s’agir de n’importe quel nom de votre choix. |
         | [!UICONTROL **Description du compte**] | Description du compte. |
         | [!UICONTROL **Identifiant du projet**] | Identifiant de projet Google Cloud. Voir [Documentation de Google Cloud sur l’obtention d’un ID de projet](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

         {style="table-layout:auto"}

         1. Sélectionner [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Principal**] | L’entité de sécurité est fournie par Adobe. Vous devez accorder l’autorisation de recevoir des flux vers cette entité. |
         | [!UICONTROL **Nom**] | Nom du compte. |
         | [!UICONTROL **Description**] | Description du compte. |
         | [!UICONTROL **Compartiment**] | Le compartiment de votre compte GCP où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous que vous avez autorisé l’entité de sécurité fournie par Adobe pour charger des fichiers dans ce compartiment. |
         | [!UICONTROL **Préfixe**] | Dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier.   Par exemple : `folder_name/` |

         {style="table-layout:auto"}

      1. Sélectionner [!UICONTROL **Créer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement GCP que vous avez spécifié.

+++

1. Dans le  [!UICONTROL **Définitions des colonnes de données**] , sélectionnez la dernière [!UICONTROL **Toutes les Adobe Columns**] dans la liste déroulante, puis renseignez les champs suivants :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Suppression des caractères avec échappement**] | Lors de la collecte de données, certains caractères (comme les sauts de lignes) peuvent entraîner des problèmes. Cochez cette case si vous souhaitez retirer ces caractères des fichiers de flux. |
   | [!UICONTROL **Format de compression**] | Type de compression utilisé. **** Fichiers de sortie Gzip au format `.tar.gz`. **** Fichiers de sortie Zip au format `.zip`. |
   | [!UICONTROL **Type de groupement**] | Sélectionner **Fichiers multiples** pour la plupart des flux de données. Cette option pagine vos données en blocs de 2 Go non compressés. (Si vous avez sélectionné plusieurs fichiers, mais que la taille des données non compressées pour la fenêtre de création de rapports est inférieure à 2 Go, un seul fichier est envoyé.) Sélection **Un seul fichier** génère la `hit_data.tsv` dans un seul fichier potentiellement massif. |
   | [!UICONTROL **Manifeste**] | Si l’Adobe doit ou non diffuser une [fichier manifeste](c-df-contents/datafeeds-contents.md#feed-manifest) à la destination lorsqu’aucune donnée n’est collectée pour un intervalle de flux. Si vous sélectionnez **Fichier de manifeste**, vous recevez un fichier de manifeste similaire à ce qui suit lorsqu’aucune donnée n’est collectée :<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Modèles de colonne**] | Lors de la création de nombreux flux de données, Adobe recommande de créer un modèle de colonne. La sélection d’un modèle de colonnes inclut automatiquement les colonnes indiquées dans le modèle. Adobe fournit également plusieurs modèles par défaut. |
   | [!UICONTROL **Colonnes disponibles**] | Toutes les colonnes de données disponibles dans Adobe Analytics. Cliquez sur [!UICONTROL Toujours ajouter] pour inclure toutes les colonnes d’un flux de données. |
   | [!UICONTROL **Colonnes incluses**] | Les colonnes à inclure dans un flux de données. Cliquez sur [!UICONTROL Tout supprimer] pour supprimer toutes les colonnes d’un flux de données. |
   | [!UICONTROL **Télécharger CSV**] | Télécharge un fichier CSV contenant toutes les colonnes incluses. |

1. Sélectionner [!UICONTROL **Enregistrer**] en haut à droite.

   Le traitement des données historiques commence immédiatement. Lorsque le traitement des données est terminé pour une journée, le fichier est envoyé à la destination que vous avez configurée.

   Pour plus d’informations sur l’accès au flux de données et pour une meilleure compréhension de son contenu, voir [Contenu du flux de données - Aperçu](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## Destinations héritées

>[!IMPORTANT]
>
>Les destinations décrites dans cette section sont héritées et ne sont pas recommandées. Utilisez plutôt l’une des destinations suivantes lors de la création d’un flux de données : Amazon S3, Google Cloud Platform, Azure RBAC ou Azure SAS. Voir [Création et configuration d’un flux de données](#create-and-configure-a-data-feed) pour obtenir des informations détaillées sur chacune de ces destinations recommandées.


Les informations suivantes fournissent des informations de configuration pour chacune des destinations héritées :

### FTP

Les données de flux de données peuvent être diffusées vers un emplacement FTP hébergé par un Adobe ou par le client. Nécessite un hôte FTP, un nom d’utilisateur et un mot de passe. Utilisez le champ Chemin d’accès pour placer les fichiers de flux dans un dossier. Les dossiers doivent déjà exister ; les fichiers lancent une erreur si le chemin d’accès précisé n’existe pas.

Renseignez les informations suivantes lorsque vous renseignez les champs disponibles :

* [!UICONTROL **Hôte**]: saisissez l’URL de destination FTP de votre choix. Par exemple : `ftp://ftp.omniture.com`.
* [!UICONTROL **Chemin**]: peut rester vide.
* [!UICONTROL **Nom d’utilisateur**]: saisissez le nom d’utilisateur pour vous connecter au site FTP.
* [!UICONTROL **Mot de passe et confirmation du mot de passe**]: saisissez le mot de passe de connexion au site FTP.

### SFTP

La prise en charge SFTP des flux de données est disponible. Nécessite un hôte SFTP, un nom d’utilisateur et un site de destination contenant une clé publique RSA ou DSA. Vous pouvez télécharger la clé publique appropriée à la création du flux.

### S3

Il est possible d’envoyer des flux directement vers des compartiments Amazon S3. Ce type de destination requiert un nom de compartiment, un identifiant de clé d’accès et une clé secrète. Consultez les [conditions d’attribution de noms pour des compartiments Amazon S3](https://docs.aws.amazon.com/fr_fr/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) dans les documents Amazon S3 pour plus d’informations.

L’utilisateur pour lequel vous chargez des flux de données doit disposer des [autorisations](https://docs.aws.amazon.com/fr_fr/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html) suivantes :

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >Pour chaque chargement vers un compartiment Amazon S3, [!DNL Analytics] ajoute le propriétaire du compartiment à la liste de contrôle d’accès BucketOwnerFullControl, que le compartiment ait ou non une politique qui le requiert. Pour plus d’informations, voir &quot;[Qu’est-ce que le paramètre BucketOwnerFullControl pour les flux de données Amazon S3 ?](df-faq.md#BucketOwnerFullControl)&quot;

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

Les flux de données prennent en charge les destinations Azure Blob. Nécessite un conteneur, un compte et une clé. Amazon chiffre automatiquement les données au repos. Les données que vous téléchargez sont automatiquement déchiffrées. Pour en savoir plus, consultez [Création d’un compte Azure Storage](https://docs.microsoft.com/fr-fr/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) dans la documentation Microsoft Azure.

>[!NOTE]
>
>Vous devez mettre en œuvre votre propre processus pour gérer l’espace disque sur la destination de flux. Adobe ne supprime pas les données du serveur.
