---
description: Gérez les utilisateurs d’Analytics et leurs ressources dans Adobe Admin Console.
title: Gestion des utilisateurs et des ressources Analytics
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
source-git-commit: 869b44b826de5cb35d13000133092397cb16ccaa
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 3%

---

# Gestion des comptes d’utilisateurs, des ressources et des expirations hérités

Vous pouvez gérer les comptes d’utilisateurs hérités, leur état de migration, les données d’expiration, le transfert de ressources vers d’autres utilisateurs, etc. à l’aide de **[!UICONTROL Administration] > [!UICONTROL Tous les administrateurs] >  [!UICONTROL Utilisateurs et administrateur d’Analytics]**.

L’écran Utilisateurs affiche la liste des utilisateurs Adobe Analytics actuels, avec les colonnes suivantes :

| Colonne | Description |
|---|---|
| [!UICONTROL Identifiant utilisateur] | ID utilisateur utilisé par l’utilisateur pour se connecter à Adobe Analytics. |
| [!UICONTROL Nom] | Nom de l’utilisateur. |
| [!UICONTROL État de migration] | État de la migration d’un compte utilisateur hérité vers un Enterprise ID ou Adobe ID.  L’état ne peut pas être lancé, mis en file d’attente ou migré. |
| [!UICONTROL Adresse électronique] | Adresse électronique de l’utilisateur. |
| [!UICONTROL Connexion héritée] | État de la connexion héritée, qui peut être activé ou désactivé. |
| [!UICONTROL Date de création] | Horodatage de création du compte utilisateur dans Adobe Analytics. |
| [!UICONTROL Dernier accès Analytics] | Horodatage du dernier accès du compte utilisateur à Adobe Analytics, |
| [!UICONTROL Expiration] | Date d’expiration du compte utilisateur ou Aucun si le compte utilisateur n’arrive pas à expiration. |

![Utilisateurs](assets/users.png)

- Pour rechercher un utilisateur spécifique, utilisez la méthode ![Rechercher](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *Recherche par titre* champ .
- Pour filtrer la liste selon l’état de migration, sélectionnez ![Chevron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL État de migration]**.
- Pour filtrer la liste selon l’état de connexion hérité, sélectionnez ![Chevron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Connexion héritée]**.
- Pour modifier l&#39;affichage des colonnes, sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) et sélectionnez les colonnes dans la fenêtre contextuelle.

Vous pouvez appliquer différentes actions lorsque vous sélectionnez un ou plusieurs utilisateurs dans la liste :

| Action | Description |
|---|---|
| ![Migrer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) **[!UICONTROL Migrer]** | Vous pouvez migrer un ou plusieurs utilisateurs vers des Enterprise ID ou des Adobe ID. |
| ![Calendrier verrouillé](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL Définir l’expiration]** | Vous pouvez définir une date d’expiration pour l’utilisation de la connexion Adobe Analytics héritée pour les utilisateurs sélectionnés.  Sélectionnez la date à utiliser dans une fenêtre contextuelle de calendrier pour spécifier la date. Sélectionner **[!UICONTROL Terminé]** pour confirmer l’expiration. |
| ![Transfert de ressources](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg) **[!UICONTROL Transfert de ressources]** | Cette action n’est disponible que lorsque vous sélectionnez un utilisateur. Si l’utilisateur dispose de ressources qui peuvent être transférées, vous pouvez sélectionner les éléments du compte (signets, tableaux de bord, etc.). Sélectionner **[!UICONTROL Transférer]** pour terminer le transfert.<br/>![Transfert de ressources](assets/transfer-assets.png) |
| ![Suppression de comptes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Suppression de comptes]** | Une boîte de dialogue s’affiche pour confirmer la suppression des comptes sélectionnés. Sélectionner **[!UICONTROL OK]** pour supprimer les comptes. Sélectionner **[!UICONTROL Annuler]** pour annuler. |
| ![Exportation au format CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL Exportation au format CSV]** | Cette action télécharge immédiatement un fichier contenant une liste de valeurs séparées par des virgules des utilisateurs sélectionnés avec leurs détails (nom, état de migration, courrier électronique, etc.). |

