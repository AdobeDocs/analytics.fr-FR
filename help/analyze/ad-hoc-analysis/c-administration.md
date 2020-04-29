---
description: Cette section vous explique comment configurer des utilisateurs et vous en apprend davantage sur l’échantillonnage des données.
title: Administration
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Administration

Cette section vous explique comment configurer des utilisateurs et vous en apprend davantage sur l’échantillonnage des données.

Pour obtenir de l’aide sur [!DNL Admin Console], voir la [référence sur les analyses](https://docs.adobe.com/content/help/fr-FR/analytics/landing/home.html).

## Licences d’utilisateur {#concept_C1440741C77C471EB38A243B013EA620}

Pour qu’un utilisateur puisse se connecter, il doit recevoir une licence d’utilisation. Les licences d’utilisation sont des licences d’utilisation simultanée. Les utilisateurs peuvent partager des licences, mais le nombre d’utilisateurs actifs à un moment donné est limité au nombre de licences achetées.

<!-- 

c_user_license.html

 -->

Lorsque le nombre d’utilisateurs connectés dépasse le nombre de licences disponibles, une boîte de dialogue avertit l’utilisateur que toutes les licences disponibles sont en cours d’utilisation. La position de l’utilisateur dans la file d’attente s’affiche, ainsi qu’un lien permettant de vérifier sa progression. Lorsqu’une licence devient disponible, l’utilisateur en est informé par courriel et une boîte de dialogue contextuelle indiquant que les Ad Hoc Analysis sont disponibles s’affiche. L’utilisateur dispose alors de 15 minutes pour réagir avant de perdre son tour dans la file d’attente.

## Octroi de licences d’utilisateur {#task_22AE669703EC48BA9685414538D8B1FA}

Procédure décrivant comment les administrateurs des Reports and Analytics locaux peuvent accorder des licences d’utilisateur par le biais du système d’autorisations.

<!-- 

t_user_licenses.xml

 -->

1. Connectez-vous à [!DNL Experience Cloud].
1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Cliquez sur **[!UICONTROL Edit Groups]**.

   Si votre a acheté des licences d’utilisateur, le [!UICONTROL Ad Hoc Analysis License Users] groupe apparaît dans la [!UICONTROL Group Name] colonne. Le nombre de licences disponibles pour la connexion des utilisateurs est également indiqué.

1. Cliquez sur **[!UICONTROL Edit]**.
1. Under [!UICONTROL Assign User Logins], select the users you want to add to the group, then click **[!UICONTROL Add.]**
1. Cliquez sur **[!UICONTROL Save Group]**.

   Le système d’octroi de licences n’impose pas de limite quant au nombre d’utilisateurs pouvant être ajoutés à un groupe. L’utilisation simultanée est limitée au nombre de licences d’utilisateur achetées.

## Gestion des sessions d’utilisateur {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

Cette procédure explique comment un administrateur peut mettre fin à la session d’un utilisateur. Cette fonctionnalité n’empêche toutefois pas un utilisateur de se reconnecter.

<!-- 

t_managing_users.xml

 -->

1. Cliquez sur **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**, puis sur **[!UICONTROL Manage Users]**.
1. Locate the user, then click **[!UICONTROL Terminate.]**

   On the [!UICONTROL Active Ad Hoc Analysis Sessions] page, the user who has been idle the longest displays at the top of list.

## Autorisations {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

Vous pouvez configurer l’accès aux suites de rapports dans [!DNL Administration Console]. Vous pouvez configurer une autorisation au niveau de la suite de rapports. Supposons, par exemple, que plusieurs de vos suites de rapports soient activées, mais que vous ne souhaitiez pas accorder à tous les utilisateurs l’accès à l’ensemble des suites. Dans ce cas, vous pouvez créer des groupes avec des suites de rapports spécifiques, puis affecter ces utilisateurs au groupe concerné.

## Ajouter un utilisateur au groupe Accès à tous les rapports {#task_E821BF3B4FDB434D844A98AAB15487A9}

Cette procédure décrit comment accorder à un utilisateur non administrateur l’accès à toutes les suites de rapports.

<!-- 

t_permissions.xml

 -->

1. Connectez-vous à **[!UICONTROL Experience Cloud]**.
1. Cliquez sur **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. Cliquez sur **[!UICONTROL All Report Access]**.
1. Dans [!UICONTROL Available Users], sélectionnez l’utilisateur, puis cliquez sur **[!UICONTROL Add.]**
1. Cliquez sur **[!UICONTROL Save Group]**.

## Créer des groupes d’autorisations {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

Vous pouvez créer des groupes d’autorisations pour les utilisateurs non administrateurs de suites de rapports spécifiques.

<!-- 

t_permission_groups.xml

 -->

1. Connectez-vous à **[!UICONTROL Experience Cloud]**.
1. Cliquez sur **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. Créez un groupe d’autorisations pour les utilisateurs non administrateurs dans lequel seront stockées les suites de rapports activées par les Ad Hoc Analysis que vous souhaitez mettre à la disposition des utilisateurs.

   The report suites available to the user are displayed in the [!UICONTROL Report Cloud] menu when you create a new project.

## Configurer des stratégies de proxy en langage Java {#task_3B03F58519544025B55CF54FACF8F4F5}

Procédure décrivant la configuration des stratégies de proxy si vous recevez une erreur de connexion au serveur.

<!-- 

t_proxy_policies.xml

 -->

Les Ad Hoc Analysis utilisent HTTP pour communiquer avec le serveur. Il est soumis aux mêmes stratégies de proxy que tout autre trafic HTTP.

1. Dans le [!DNL Windows Control Panel], lancez le [!UICONTROL Java Control Panel].
1. Sur l’ **[!UICONTROL General]** onglet, cliquez sur **[!UICONTROL Network Settings]**.
1. Sélectionnez **[!UICONTROL Use browser settings]** ou configurez manuellement les paramètres du proxy.
1. Cliquez sur **[!UICONTROL OK]**, puis sur **[!UICONTROL OK]** le [!UICONTROL Java Control Panel].

## Échantillonnage des données {#concept_8433CFD38E0243849E92DF4F1E743AC3}

Les échantillons de données du visiteur servent à créer des rapports pertinents et précis. La plage de dates est utilisée comme période des données pour un projet chargé. Une période correspond généralement au mois actuel et aux deux mois précédents.

<!-- 

c_overview_data_sampling.xml

 -->

Pour un traitement optimal, les Ad Hoc Analysis utilisent une valeur équivalant approximativement à 750 millions en tant que nombre de visites maximum par période. (Visites = page vues + événements.)

Pour obtenir l’estimation d’un taux d’échantillonnage, les visites estimées sont calculées par ensemble de données, puis divisées par 750 millions, comme illustré ici :

* (Moy. des visites quotidiennes x nbre de jours de la période) / 750 millions

Si, par exemple, vous avez 10 millions de visites par jour avec une période de données de 90 jours :

* (10 000 000 x 90) / 750 000 000 = 1,2

Pour maintenir le nombre de visites pour cette période de 90 jours en dessous de 750 000 000, le taux d’échantillonnage des données peut être de 1,2:1. Cependant, puisque les échantillonnages sur la base de nombres entiers sont utilisés, le taux d’échantillonnage est de 2:1.

Si, par exemple, vous avez 10 millions de visites par jour avec une période de données de 365 jours :

* (10 000 000 x 365) / 750 000 000 = 4,8

Pour que le nombre de visites pour cette période de 365 jours reste inférieur à 750 000 000, le taux d’échantillonnage des données peut être de 4,8:1. En utilisant des chiffres entiers, le taux d’échantillonnage est de 5:1.
