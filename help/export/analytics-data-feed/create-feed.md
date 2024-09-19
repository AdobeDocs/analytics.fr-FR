---
title: Créer un flux de données
description: Découvrez comment créer un flux de données.
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: 8e8f59f747ddacc5462cbc177d199a5e0e91908a
workflow-type: tm+mt
source-wordcount: '4119'
ht-degree: 53%

---

# Créer un flux de données

Lors de la création d’un flux de données, vous fournissez l’Adobe avec :

* Informations sur la destination vers laquelle vous souhaitez envoyer les fichiers de données brutes.

* Les données à inclure dans chaque fichier

>[!NOTE]
>
>Avant de créer un flux de données, il est important de posséder une compréhension de base des flux de données et de vous assurer que vous remplissez toutes les conditions préalables requises. Pour plus d’informations, voir [Présentation des flux de données](data-feed-overview.md).

## Création et configuration d’un flux de données

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Sélectionnez l’icône de 9 carrés en haut à droite, puis sélectionnez [!UICONTROL **Analytics**].
1. Dans la barre de navigation supérieure, accédez à [!UICONTROL **Admin**] > [!UICONTROL **Flux de données**].
1. Sélectionnez [!UICONTROL **Ajouter**].

   ![Ajouter un flux de données](assets/datafeed-add.png)

   Une page s’affiche avec trois catégories principales : [!UICONTROL **Informations sur le flux**], [!UICONTROL **Destination**] et [!UICONTROL **Définitions des colonnes de données**].
1. Dans la section [!UICONTROL **Informations sur le flux**] , renseignez les champs suivants :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Nom**] | Nom du flux de données. Doit être unique au sein de la suite de rapports sélectionnée et peut comporter jusqu’à 255 caractères. |
   | [!UICONTROL **Suite de rapports**] | Suite de rapports sur laquelle le flux de données est basé. Si plusieurs flux de données sont créés pour une même suite de rapports, ils doivent avoir des définitions de colonne différentes. Seules les suites de rapports source prennent en charge les flux de données ; les suites de rapports virtuelles ne sont pas prises en charge. |
   | [!UICONTROL **Courrier électronique une fois terminé**] | L’adresse électronique à laquelle envoyer une notification lorsqu’un flux termine le traitement. L’adresse e-mail doit être correctement formatée. |
   | [!UICONTROL **Intervalle de flux**] | Sélectionnez **Quotidien** pour le renvoi ou les données historiques. Les flux quotidiens contiennent l’équivalent d’une journée complète de données, de minuit à minuit, dans le fuseau horaire de la suite de rapports. Sélectionnez **Horaire** pour les données continues (une fois par jour est également disponible pour les flux continus si vous préférez). Les flux horaires contiennent l’équivalent d’une seule heure de données. |
   | [!UICONTROL **Traitement du délai**] | Patientez un certain temps avant de traiter un fichier de flux de données. Il peut être utile de mettre en place un délai pour donner aux appareils hors ligne la possibilité de se connecter et d’envoyer leurs données dans le cadre d’implémentations mobiles. Il est également possible d’utiliser un délai pour adapter les processus côté serveur de votre entreprise en ce qui concerne la gestion des fichiers traités précédemment. Dans la plupart des cas aucun délai n’est nécessaire. Un flux peut être se voir attribuer un délai pouvant aller jusqu’à 120 minutes. |
   | [!UICONTROL **Dates de début et de fin**] | La date de début indique la date de début du flux de données. Pour commencer immédiatement à traiter les flux de données pour les données historiques, définissez cette date sur n’importe quelle date antérieure à laquelle les données sont collectées. Les dates de début et de fin sont définies en fonction du fuseau horaire de la suite de rapports. |
   | [!UICONTROL **Flux continu**] | Cette case à cocher supprime la date de fin, ce qui permet à un flux de s’exécuter indéfiniment. Lorsqu’un flux termine le traitement de données historiques, un flux attend la fin de la collecte des données pour une heure ou un jour donné. Une fois l’heure ou le jour en question terminé, le traitement commence après le délai indiqué. |

1. Dans la section [!UICONTROL **Destination**], dans le menu déroulant [!UICONTROL **Type**], sélectionnez la destination vers laquelle vous souhaitez envoyer les données.

   >[!NOTE]
   >
   >Tenez compte de ce qui suit lors de la configuration du rapport de destination :
   >
   >* Nous vous recommandons d’utiliser un compte cloud pour votre destination de rapport. [Les comptes FTP et SFTP hérités](#legacy-destinations) sont disponibles, mais ne sont pas recommandés.
   >* Tous les comptes cloud que vous avez précédemment configurés peuvent être utilisés pour les flux de données. Vous pouvez configurer des comptes cloud de l’une des manières suivantes :
   >
   >   * Lors de la configuration de comptes cloud pour [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
   >   
   >   * Lors de l’ [ import de données de classification Adobe Analytics](/help/components/locations/locations-manager.md) (aucun emplacement configuré pour importer des données de classification ne peut être utilisé.)
   >   
   >   * Dans le gestionnaire des emplacements, dans [Composants > Emplacements](/help/components/locations/configure-import-accounts.md)
   >
   >* Les comptes cloud sont associés à votre compte d’utilisateur ou d’utilisatrice Adobe Analytics. Les autres utilisateurs et utilisatrices ne peuvent pas utiliser ni afficher les comptes cloud que vous configurez.
   >
   >* Vous pouvez modifier les emplacements que vous créez à partir du gestionnaire d’emplacements dans [Composants > Emplacements](/help/components/locations/configure-import-accounts.md).

   ![Menu déroulant de destination du flux de données](assets/datafeed-destinations-dropdown.png)

   Utilisez l’un des types de destination suivants lors de la création d’un flux de données. Pour obtenir des instructions sur la configuration, développez le type de destination. (Des [destinations héritées](#legacy-destinations) supplémentaires sont également disponibles, mais ne sont pas recommandées.)

   +++Amazon S3

   Il est possible d’envoyer des flux directement vers des compartiments Amazon S3. Ce type de destination nécessite uniquement votre compte Amazon S3 et l’emplacement (compartiment).

   Adobe Analytics utilise l’authentification entre comptes pour charger des fichiers d’Adobe Analytics vers l’emplacement spécifié dans votre instance Amazon S3.

   Pour configurer un compartiment Amazon S3 comme destination d’un flux de données :

   1. Commencez à créer un flux de données comme décrit dans [Créer et configurer un flux de données](#create-and-configure-a-data-feed).

   1. Dans la section [!UICONTROL **Destination**], dans le menu déroulant [!UICONTROL **Type**], sélectionnez [!UICONTROL **Amazon S3**].

      ![Destination Amazon S3](assets/datafeed-destination-amazons3.png)

   1. Sélectionnez [!UICONTROL **Sélectionner l’emplacement**].

      La page Emplacements d’exportation Amazon S3 s’affiche.

   1. (Conditionnel) Si un compte Amazon S3 (et un emplacement sur ce compte) a déjà été configuré dans Adobe Analytics, vous pouvez l’utiliser comme destination de flux de données :

      >[!NOTE]
      >
      >Vous ne pouvez accéder aux comptes que si vous les avez configurés ou s’ils ont été partagés avec une organisation dont vous faites partie.

      1. Sélectionnez le compte dans le menu déroulant [!UICONTROL **Sélectionner un compte**].

         Tous les comptes cloud configurés dans l’une des zones suivantes d’Adobe Analytics sont disponibles :

         * Lors de l’import de données de classification Adobe Analytics, comme décrit dans [Schéma](/help/components/classifications/sets/manage/schema.md).

           Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés. Ajoutez plutôt une nouvelle destination comme décrit ci-dessous.

         * Lors de la configuration de comptes et d’emplacements dans la zone Emplacements, comme décrit dans [Configurer des comptes d’import et d’export dans le cloud](/help/components/locations/configure-import-accounts.md) et [Configurer des emplacements d’import et d’export dans le cloud](/help/components/locations/configure-import-locations.md).

      1. Sélectionnez l’emplacement dans le menu déroulant [!UICONTROL **Sélectionner l’emplacement**] .

      1. Sélectionnez [!UICONTROL **Save**] > [!UICONTROL **Save**].

      La destination est maintenant configurée pour envoyer des données à l’emplacement Amazon S3 que vous avez spécifié.

   1. (Conditionnel) Si vous n’avez pas encore ajouté de compte Amazon S3 :

      1. Sélectionnez [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom du compte**] | Nom du compte. Il peut s’agir de n’importe quel nom de votre choix. |
         | [!UICONTROL **Description du compte**] | Description du compte. |
         | [!UICONTROL **ARN de rôle**] | Vous devez fournir un ARN de rôle (nom de ressource Amazon) qu’Adobe peut utiliser pour accéder au compte Amazon S3. Pour ce faire, vous créez une politique d’autorisation IAM pour le compte source, vous la joignez à un utilisateur ou à une utilisatrice, puis vous créez un rôle pour le compte de destination. Pour plus d’informations, consultez [cette documentation AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **ARN d’utilisateur ou d’utilisatrice**] | L’ARN d’utilisateur ou d’utilisatrice (nom de ressource Amazon) est fourni par Adobe. Vous devez associer cet utilisateur ou cette utilisatrice à la politique que vous avez créée. |

         {style="table-layout:auto"}

      1. Sélectionnez [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom**] | Nom du compte. |
         | [!UICONTROL **Description**] | Description du compte. |
         | [!UICONTROL **Compartiment**] | Compartiment de votre compte Amazon S3 dans lequel vous souhaitez que les données Adobe Analytics soient envoyées. <p>Assurez-vous que l’ARN d’utilisateur ou d’utilisatrice fourni par Adobe dispose de l’autorisation `S3:PutObject` pour charger des fichiers vers ce compartiment. Cette autorisation permet à l’ARN d’utilisateur ou d’utilisatrice de charger les fichiers initiaux et de remplacer les fichiers pour les chargements suivants.</p><p>Les noms des compartiments doivent respecter des règles de nommage spécifiques. Par exemple, ils doivent avoir une longueur comprise entre 3 et 63 caractères, ne peuvent être composés que de lettres minuscules, de chiffres, de points (.) et de traits d’union (-), et doivent commencer et se terminer par une lettre ou un chiffre. [Une liste complète des règles de nommage est disponible dans la documentation AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
         | [!UICONTROL **Préfixe**] | Dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, `folder_name/` |

         {style="table-layout:auto"}

      1. Sélectionnez [!UICONTROL **Créer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Amazon S3 que vous avez spécifié.

      1. (Conditionnel) Si vous devez gérer la destination (compte et emplacement) que vous venez de créer, elle est disponible dans le [gestionnaire d’emplacements](/help/components/locations/locations-manager.md).

+++

   +++Azure RBAC

   Vous pouvez envoyer des flux directement à un conteneur Azure à l’aide de l’authentification RBAC. Ce type de destination nécessite un ID d’application, un ID de tenant et un secret.

   Pour configurer un compte Azure RBAC comme destination d’un flux de données :

   1. Si ce n’est déjà fait, créez une application Azure qu’Adobe Analytics peut utiliser pour l’authentification, puis accordez des autorisations d’accès dans le contrôle d’accès (IAM).

      Pour plus d’informations, reportez-vous à la [documentation de Microsoft Azure sur la création d’une application Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. Dans la console d’administration Adobe Analytics, dans la section [!UICONTROL **Destination**], dans le menu déroulant [!UICONTROL **Type**], sélectionnez [!UICONTROL **Azure RBAC**].

      ![Destination Azure RBAC](assets/datafeed-destination-azurerbac.png)

   1. Sélectionnez [!UICONTROL **Sélectionner l’emplacement**].

      La page Emplacements d’exportation Azure RBAC s’affiche.

   1. (Conditionnel) Si un compte Azure RBAC (et un emplacement sur ce compte) a déjà été configuré dans Adobe Analytics, vous pouvez l’utiliser comme destination de flux de données :

      >[!NOTE]
      >
      >Vous ne pouvez accéder aux comptes que si vous les avez configurés ou s’ils ont été partagés avec une organisation dont vous faites partie.

      1. Sélectionnez le compte dans le menu déroulant [!UICONTROL **Sélectionner un compte**].

      Les comptes cloud que vous avez configurés dans l’une des zones suivantes d’Adobe Analytics sont disponibles :

      * Lors de l’import de données de classification Adobe Analytics, comme décrit dans [Schéma](/help/components/classifications/sets/manage/schema.md).

        Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés. Ajoutez plutôt une nouvelle destination comme décrit ci-dessous.

      * Lors de la configuration de comptes et d’emplacements dans la zone Emplacements, comme décrit dans [Configurer des comptes d’import et d’export dans le cloud](/help/components/locations/configure-import-accounts.md) et [Configurer des emplacements d’import et d’export dans le cloud](/help/components/locations/configure-import-locations.md).

      1. Sélectionnez l’emplacement dans le menu déroulant [!UICONTROL **Sélectionner l’emplacement**] .

      1. Sélectionnez [!UICONTROL **Save**] > [!UICONTROL **Save**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Azure RBAC que vous avez spécifié.

   1. (Conditionnel) Si vous n’avez pas encore ajouté de compte Azure RBAC :

      1. Sélectionnez [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom du compte**] | Nom du compte Azure RBAC. Ce nom s&#39;affiche dans le champ déroulant [!UICONTROL **Sélectionner un compte**] et peut être n&#39;importe quel nom de votre choix. |
         | [!UICONTROL **Description du compte**] | Description du compte Azure RBAC. Cette description s’affiche dans le champ déroulant [!UICONTROL **Sélectionner un compte**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **ID de l’application**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistreement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
         | [!UICONTROL **ID de cliente ou client**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistrement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
         | [!UICONTROL **Secret**] | Copiez le secret depuis l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur l’onglet **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistrement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Sélectionnez [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom**] | Nom de l’emplacement. Ce nom s’affiche dans le champ déroulant [!UICONTROL **Sélectionner un emplacement**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **Description**] | Description de l’emplacement. Cette description s’affiche dans le champ déroulant [!UICONTROL **Sélectionner un emplacement**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **Compte**] | Compte de stockage Azure. |
         | [!UICONTROL **Conteneur**] | Conteneur dans le compte que vous avez spécifié où vous souhaitez que les données Adobe Analytics soient envoyées. Assurez-vous d’accorder les autorisations de chargement de fichiers vers l’application Azure que vous avez créée précédemment. |
         | [!UICONTROL **Préfixe**] | Dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, `folder_name/`.<p>Assurez-vous que l’ID d’application que vous avez spécifié lors de la configuration du compte Azure RBAC a reçu le rôle `Storage Blob Data Contributor` pour accéder au conteneur (dossier).</p> <p>Pour plus d’informations, consultez [Rôles intégrés Azure](https://learn.microsoft.com/fr-fr/azure/role-based-access-control/built-in-roles).</p> |

         {style="table-layout:auto"}

      1. Sélectionnez [!UICONTROL **Créer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Azure RBAC que vous avez spécifié.

      1. (Conditionnel) Si vous devez gérer la destination (compte et emplacement) que vous venez de créer, elle est disponible dans le [gestionnaire d’emplacements](/help/components/locations/locations-manager.md).

+++

   +++Azure SAS

   Vous pouvez envoyer des flux directement à un conteneur Azure à l’aide de l’authentification SAS. Ce type de destination nécessite un ID d’application, un ID de tenant, un URI de coffre de clé, un nom de secret de coffre de clé et un secret.

   Pour configurer Azure SAS comme destination d’un flux de données :

   1. Si ce n’est déjà fait, créez une application Azure qu’Adobe Analytics peut utiliser pour l’authentification.

      Pour plus d’informations, reportez-vous à la [documentation de Microsoft Azure sur la création d’une application Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. Dans la console d’administration Adobe Analytics, dans la section [!UICONTROL **Destination**], sélectionnez [!UICONTROL **Azure SAS**].

      ![Destination Azure SAS](assets/datafeed-destination-azuresas.png)

   1. Sélectionnez [!UICONTROL **Sélectionner l’emplacement**].

      La page Emplacements d’exportation Azure SAS s’affiche.

   1. (Conditionnel) Si un compte Azure SAS (et un emplacement sur ce compte) a déjà été configuré dans Adobe Analytics, vous pouvez l’utiliser comme destination de flux de données :

      >[!NOTE]
      >
      >Vous ne pouvez accéder aux comptes que si vous les avez configurés ou s’ils ont été partagés avec une organisation dont vous faites partie.

      1. Sélectionnez le compte dans le menu déroulant [!UICONTROL **Sélectionner un compte**].

         Les comptes cloud que vous avez configurés dans l’une des zones suivantes d’Adobe Analytics sont disponibles :

         * Lors de l’import de données de classification Adobe Analytics, comme décrit dans [Schéma](/help/components/classifications/sets/manage/schema.md).

           Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés. Ajoutez plutôt une nouvelle destination comme décrit ci-dessous.

         * Lors de la configuration de comptes et d’emplacements dans la zone Emplacements, comme décrit dans [Configurer des comptes d’import et d’export dans le cloud](/help/components/locations/configure-import-accounts.md) et [Configurer des emplacements d’import et d’export dans le cloud](/help/components/locations/configure-import-locations.md).

      1. Sélectionnez l’emplacement dans le menu déroulant [!UICONTROL **Sélectionner l’emplacement**] .

      1. Sélectionnez [!UICONTROL **Save**] > [!UICONTROL **Save**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Azure SAS que vous avez spécifié.

   1. (Conditionnel) Si vous n’avez pas encore ajouté de compte Azure SAS :

      1. Sélectionnez [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom du compte**] | Nom du compte Azure SAS. Ce nom s&#39;affiche dans le champ déroulant [!UICONTROL **Sélectionner un compte**] et peut être n&#39;importe quel nom de votre choix. |
         | [!UICONTROL **Description du compte**] | Description du compte Azure SAS. Cette description s’affiche dans le champ déroulant [!UICONTROL **Sélectionner un compte**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **ID de l’application**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistreement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
         | [!UICONTROL **ID de cliente ou client**] | Copiez cet ID à partir de l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur la page **Vue d’ensemble** dans votre application. Pour plus d’informations, consultez la [documentation Microsoft Azure sur la façon d’enregistrer une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |
         | [!UICONTROL **URI du coffre de clés**] | <p>Chemin d’accès à l’URI SAS dans Azure Key Vault. Pour configurer une signature d’accès partagé Azure (SAS), vous devez stocker un URI SAS en tant que secret à l’aide d’Azure Key Vault. Pour plus d’informations, consultez la [documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Une fois l’URI de coffre de clés créé :<ul><li>Ajoutez une politique d’accès sur Key Vault afin d’accorder l’autorisation à l’application Azure que vous avez créée.<p>Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’affectation d’une politique d’accès Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>Ou</p><p>Si vous souhaitez accorder un rôle d’accès directement sans créer de stratégie d’accès, consultez la [documentation de Microsoft Azure sur l’affectation de rôles Azure à l’aide du portail Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Cela ajoute l’affectation de rôle pour l’ID d’application pour accéder à l’URI de coffre-fort de clé. </p></li><li>Assurez-vous que l’ID de l’application a bien reçu le rôle intégré `Key Vault Certificate User` afin d’accéder à l’URI de coffre de clés.</br><p>Pour plus d’informations, voir [Rôles intégrés Azure](https://learn.microsoft.com/fr-fr/azure/role-based-access-control/built-in-roles).</p></li></ul> |
         | [!UICONTROL **Nom secret du coffre de clés**] | Le nom du secret que vous avez créé lors de l’ajout du secret à Azure Key Vault. Dans Microsoft Azure, ces informations se trouvent dans le coffre Key Vault que vous avez créé, sur la page de paramètres de **Key Vault**. Pour plus d’informations, voir [Documentation de Microsoft Azure sur la définition et la récupération d’un secret à partir d’Azure Key Vault](https://learn.microsoft.com/fr-fr/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Secret**] | Copiez le secret depuis l’application Azure que vous avez créée. Dans Microsoft Azure, ces informations sont situées sur l’onglet **Certificats et secrets** dans votre application. Pour plus d’informations, voir [Documentation de Microsoft Azure sur l’enregistrement d’une application avec la plateforme d’identité Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Sélectionnez [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom**] | Nom de l’emplacement. Ce nom s’affiche dans le champ déroulant [!UICONTROL **Sélectionner un emplacement**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **Description**] | Description de l’emplacement. Cette description s’affiche dans le champ déroulant [!UICONTROL **Sélectionner un emplacement**] et peut être n’importe quel nom de votre choix. |
         | [!UICONTROL **Conteneur**] | Conteneur dans le compte que vous avez spécifié où vous souhaitez que les données Adobe Analytics soient envoyées. |
         | [!UICONTROL **Préfixe**] | Dossier du conteneur dans lequel vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, `folder_name/`<p>Assurez-vous que le magasin d’URI SAS que vous avez spécifié dans le champ Nom du secret Key Vault lors de la configuration du compte Azure SAS dispose de l’autorisation `Write`. Cela permet à l’URI SAS de créer des fichiers dans votre conteneur Azure. <p>Si vous souhaitez que l’URI SAS remplace également les fichiers, assurez-vous que le magasin d’URI SAS dispose de l’autorisation `Delete`.</p><p>Pour plus d’informations, consultez [Ressources de stockage Blob](https://learn.microsoft.com/fr-fr/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) dans la documentation Azure Blob Storage.</p> |

         {style="table-layout:auto"}

      1. Sélectionnez [!UICONTROL **Créer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Azure SAS que vous avez spécifié.

      1. (Conditionnel) Si vous devez gérer la destination (compte et emplacement) que vous venez de créer, elle est disponible dans le [gestionnaire d’emplacements](/help/components/locations/locations-manager.md).

+++

   +++Google Cloud Platform

   Vous pouvez envoyer des flux directement aux compartiments Google Cloud Platform (GCP). Ce type de destination nécessite uniquement le nom de votre compte GCP et le nom de l’emplacement (compartiment).

   Adobe Analytics utilise l’authentification entre comptes pour charger des fichiers d’Adobe Analytics vers l’emplacement spécifié dans votre instance GCP.

   Pour configurer un compartiment GCP comme destination d’un flux de données :

   1. Dans la section [!UICONTROL **Destination**] de la console d’administration Adobe Analytics, sélectionnez [!UICONTROL **Google Cloud Platform**].

      ![Destination de la plateforme Google Cloud](assets/datafeed-destination-gcp.png)

   1. Sélectionnez [!UICONTROL **Sélectionner l’emplacement**].

      La page Emplacements d’exportation GCP s’affiche.

   1. (Conditionnel) Si un compte Google Cloud Platform (et un emplacement sur ce compte) a déjà été configuré dans Adobe Analytics, vous pouvez l’utiliser comme destination de vos flux de données :

      >[!NOTE]
      >
      >Vous ne pouvez accéder aux comptes que si vous les avez configurés ou s’ils ont été partagés avec une organisation dont vous faites partie.

      1. Sélectionnez le compte dans le menu déroulant [!UICONTROL **Sélectionner un compte**].

         Les comptes cloud que vous avez configurés dans l’une des zones suivantes d’Adobe Analytics sont disponibles :

         * Lors de l’import de données de classification Adobe Analytics, comme décrit dans [Schéma](/help/components/classifications/sets/manage/schema.md).

           Cependant, les emplacements configurés pour importer des données de classification ne peuvent pas être utilisés. Ajoutez plutôt une nouvelle destination comme décrit ci-dessous.

         * Lors de la configuration de comptes et d’emplacements dans la zone Emplacements, comme décrit dans [Configurer des comptes d’import et d’export dans le cloud](/help/components/locations/configure-import-accounts.md) et [Configurer des emplacements d’import et d’export dans le cloud](/help/components/locations/configure-import-locations.md).

      1. Sélectionnez l’emplacement dans le menu déroulant [!UICONTROL **Sélectionner l’emplacement**] .

      1. Sélectionnez [!UICONTROL **Save**] > [!UICONTROL **Save**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement Google Cloud Platform que vous avez spécifié.

   1. (Conditionnel) Si vous n’avez pas encore ajouté de compte GCP :

      1. Sélectionnez [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Nom du compte**] | Nom du compte. Il peut s’agir de n’importe quel nom de votre choix. |
         | [!UICONTROL **Description du compte**] | Description du compte. |
         | [!UICONTROL **Identifiant du projet**] | ID de projet Google Cloud. Consultez la [documentation de Google Cloud sur l’obtention d’un ID de projet](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=fr#identifying_projects). |

         {style="table-layout:auto"}

      1. Sélectionnez [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes :

         | Champ | Fonction |
         |---------|----------|
         | [!UICONTROL **Principal**] | L’entité de sécurité est fournie par Adobe. Vous devez accorder l’autorisation de recevoir des flux vers cette entité. |
         | [!UICONTROL **Nom**] | Nom du compte. |
         | [!UICONTROL **Description**] | Description du compte. |
         | [!UICONTROL **Compartiment**] | Compartiment de votre compte GCP où vous souhaitez que les données Adobe Analytics soient envoyées. <p>Assurez-vous que vous avez accordé l’une des autorisations suivantes au compte principal fourni par Adobe : (pour plus d’informations sur l’octroi des autorisations, voir [Ajouter un compte principal à une politique au niveau du compartiment](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=fr#bucket-add) dans la documentation de Google Cloud.)<ul><li>`roles/storage.objectCreator` : utilisez cette autorisation si vous souhaitez limiter le principal uniquement à la création de fichiers dans votre compte GCP. </br>**Important :** si vous utilisez cette autorisation avec les rapports planifiés, vous devez utiliser un nom de fichier unique pour chaque nouvel export planifié. Sinon, la génération du rapport échouera, car le principal n’a pas accès pour remplacer les fichiers existants.</li><li>(Recommandé) `roles/storage.objectUser` : utilisez cette autorisation si vous souhaitez que l’entité de sécurité ait accès à l’affichage, la liste, la mise à jour et la suppression des fichiers dans votre compte GCP.</br>Cette autorisation permet au principal d’écraser les fichiers existants pour les chargements ultérieurs, sans avoir à générer automatiquement des noms de fichier uniques pour chaque nouvel export planifié.</li></ul><p>Si votre entreprise utilise des [Contraintes applicables aux politiques des organisations](https://cloud.google.com/storage/docs/org-policy-constraints?hl=fr) pour n’autoriser que le compte Google Cloud Platform dans votre liste autorisée, vous avez besoin de cet identifiant d’organisation Google Cloud Platform détenu par Adobe : <ul><li>`DISPLAY_NAME` : `adobe.com`</li><li>`ID` : `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID` : `C02jo8puj`</li></ul> </p> |
         | [!UICONTROL **Préfixe**] | Dossier dans le compartiment où vous souhaitez placer les données. Indiquez un nom de dossier, puis ajoutez une barre oblique inverse après le nom pour créer le dossier. Par exemple, `folder_name/` |

         {style="table-layout:auto"}

      1. Sélectionnez [!UICONTROL **Créer**] > [!UICONTROL **Enregistrer**].

         La destination est maintenant configurée pour envoyer des données à l’emplacement GCP que vous avez spécifié.

      1. (Conditionnel) Si vous devez gérer la destination (compte et emplacement) que vous venez de créer, elle est disponible dans le [gestionnaire d’emplacements](/help/components/locations/locations-manager.md).

+++

1. Dans la section [!UICONTROL **Définitions des colonnes de données**] , sélectionnez le dernier modèle [!UICONTROL **Toutes les Adobe Columns**] dans la liste déroulante, puis renseignez les champs suivants :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Supprimer les caractères avec échappement**] | Lors de la collecte de données, certains caractères (comme les sauts de lignes) peuvent entraîner des problèmes. Cochez cette case si vous souhaitez retirer ces caractères des fichiers de flux. |
   | [!UICONTROL **Format de compression**] | Type de compression utilisé. **Gzip** génère des fichiers au format `.tar.gz`. **Zip** génère des fichiers au format `.zip`. |
   | [!UICONTROL **Type de module**] | Sélectionnez [!UICONTROL **Plusieurs fichiers**] pour la plupart des flux de données. Cette option pagine vos données en blocs de 2 Go non compressés. (Si l’option [!UICONTROL **Plusieurs fichiers**] est sélectionnée et que les données non compressées de la fenêtre de création de rapports sont inférieures à 2 Go, un fichier est envoyé.) Si vous sélectionnez **Un seul fichier**, le fichier `hit_data.tsv` est généré dans un seul fichier potentiellement volumineux. |
   | [!UICONTROL **Manifest**] | Détermine si l’Adobe doit envoyer un [fichier manifeste](c-df-contents/datafeeds-contents.md#feed-manifest) vers la destination lorsqu’aucune donnée n’est collectée pour un intervalle de flux. Si vous sélectionnez **Fichier de manifeste**, vous recevez un fichier de manifeste semblable à ce qui suit lorsqu’aucune donnée n’est collectée :<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Modèles de colonne**] | Lors de la création de nombreux flux de données, Adobe recommande de créer un modèle de colonne. La sélection d’un modèle de colonnes inclut automatiquement les colonnes indiquées dans le modèle. Adobe fournit également plusieurs modèles par défaut. |
   | [!UICONTROL **Colonnes disponibles**] | Toutes les colonnes de données disponibles dans Adobe Analytics. Cliquez sur [!UICONTROL Toujours ajouter] pour inclure toutes les colonnes d’un flux de données. |
   | [!UICONTROL **Colonnes incluses**] | Les colonnes à inclure dans un flux de données. Cliquez sur [!UICONTROL Tout supprimer] pour supprimer toutes les colonnes d’un flux de données. |
   | [!UICONTROL **Téléchargement de fichier CSV**] | Télécharge un fichier CSV contenant toutes les colonnes incluses. |

1. Sélectionnez [!UICONTROL **Enregistrer**] en haut à droite.

   Le traitement des données historiques commence immédiatement. Lorsque le traitement des données est terminé pour une journée, le fichier est envoyé à la destination que vous avez configurée.

   Pour plus d’informations sur l’accès au flux de données et pour une meilleure compréhension de son contenu, voir [Contenu du flux de données - Aperçu](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## Destinations héritées

>[!IMPORTANT]
>
>Les destinations décrites dans cette section sont héritées et ne sont pas recommandées. Utilisez plutôt l’une des destinations suivantes lors de la création d’un flux de données : Amazon S3, Google Cloud Platform, Azure RBAC ou Azure SAS. Voir [Création et configuration d’un flux de données](#create-and-configure-a-data-feed) pour obtenir des informations détaillées sur chacune de ces destinations recommandées.


Les informations suivantes fournissent des informations de configuration pour chacune des destinations héritées :

### FTP

Les données de flux de données peuvent être diffusées vers un emplacement FTP hébergé par un Adobe ou par le client. Nécessite un hôte FTP, un nom d’utilisateur et un mot de passe. Utilisez le champ Chemin d’accès pour placer les fichiers de flux dans un dossier. Les dossiers doivent déjà exister ; les fichiers lancent une erreur si le chemin d’accès précisé n’existe pas.

Renseignez les informations suivantes pour les champs disponibles :

* [!UICONTROL **Hôte**] : entrez l’URL de destination FTP de votre choix. Par exemple : `ftp://ftp.omniture.com`.
* [!UICONTROL **Chemin**] : peut rester vide
* [!UICONTROL **Nom d’utilisateur ou d’utilisatrice**] : saisissez le nom d’utilisateur ou d’utilisatrice pour vous connecter au site FTP.
* [!UICONTROL **Mot de passe et confirmation du mot de passe**] : saisissez le mot de passe pour vous connecter au site FTP.

### SFTP

La prise en charge SFTP des flux de données est disponible. Nécessite un hôte SFTP, un nom d’utilisateur et un site de destination contenant une clé publique RSA ou DSA. Vous pouvez télécharger la clé publique appropriée à la création du flux.

### S3

Il est possible d’envoyer des flux directement vers des compartiments Amazon S3. Ce type de destination requiert un nom de compartiment, un identifiant de clé d’accès et une clé secrète. Consultez les [exigences de nommage pour des compartiments Amazon S3](https://docs.aws.amazon.com/fr_fr/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) dans les documents Amazon S3 pour plus d’informations.

L’utilisateur pour lequel vous chargez des flux de données doit disposer des [autorisations](https://docs.aws.amazon.com/fr_fr/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html) suivantes :

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >Pour chaque téléchargement vers un compartiment Amazon S3, [!DNL Analytics] ajoute le propriétaire du compartiment à la liste de contrôle d’accès BucketOwnerFullControl, que le compartiment ait ou non une stratégie qui le requiert. Pour plus d’informations, voir &quot;[Quel est le paramètre BucketOwnerFullControl pour les flux de données Amazon S3 ?](df-faq.md#BucketOwnerFullControl)&quot;

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
