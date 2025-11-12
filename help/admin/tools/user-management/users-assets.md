---
description: Gérez les utilisateurs d’Analytics et leurs ressources dans Adobe Admin Console.
title: Gestion des utilisateurs et des ressources Analytics
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 4%

---

# Gestion des comptes utilisateur, ressources et expirations hérités

Vous pouvez gérer les comptes utilisateur hérités, leur statut de migration, les données d’expiration, le transfert de ressources à d’autres utilisateurs, etc. à l’aide de **[!UICONTROL Admin] > [!UICONTROL Tous les administrateurs] > [!UICONTROL Utilisateurs et administrateurs Analytics]**.

L’écran Utilisateurs affiche une liste des utilisateurs Adobe Analytics actuels, avec les colonnes suivantes :

| Colonne | Description |
|---|---|
| [!UICONTROL Identifiant utilisateur] | Identifiant utilisateur que l’utilisateur utilise pour se connecter à Adobe Analytics. |
| [!UICONTROL Nom] | Nom de l’utilisateur. |
| [!UICONTROL Statut de migration] | Statut de la migration d’un compte utilisateur hérité vers Enterprise ID ou Adobe ID.  Le statut peut être Non initié, En file d’attente ou Migré. |
| [!UICONTROL Adresse électronique] | Adresse e-mail de l’utilisateur. |
| [!UICONTROL Connexion héritée] | Statut de la connexion héritée, qui peut être Activé ou Désactivé. |
| [!UICONTROL Date de création] | Date et heure de création du compte utilisateur dans Adobe Analytics. |
| [!UICONTROL Dernier accès à Analytics] | la date et l’heure du dernier accès du compte utilisateur à Adobe Analytics, |
| [!UICONTROL Expiration] | Date d’expiration du compte d’utilisateur ou Aucun si le compte d’utilisateur n’expire pas. |

![Utilisateurs](assets/users.png)

- Pour rechercher un utilisateur spécifique, utilisez le champ ![Rechercher](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *Rechercher par titre*.
- Pour filtrer la liste selon le statut de migration, sélectionnez ![Chevron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Statut de migration]**.
- Pour filtrer la liste selon le statut de connexion hérité, sélectionnez ![Chevron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Connexion héritée]**.
- Pour modifier l’affichage des colonnes, sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) et sélectionnez les colonnes dans la fenêtre contextuelle.

Vous pouvez appliquer différentes actions lors de la sélection d&#39;un ou plusieurs utilisateurs dans la liste :

| Action | Description |
|---|---|
| ![Migrer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) **[!UICONTROL Migrer]** | Vous pouvez migrer un ou plusieurs utilisateurs vers des Enterprise ID ou des Adobe ID. |
| ![&#x200B; Calendrier verrouillé &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL Définir l’expiration]** | Vous pouvez définir une date d’expiration pour l’utilisation de la connexion Adobe Analytics héritée pour les utilisateurs sélectionnés.  Sélectionnez la date à utiliser dans une fenêtre contextuelle de calendrier pour spécifier la date. Sélectionnez **[!UICONTROL Terminé]** pour confirmer l’expiration. |
| ![Transfert de ressources](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg) **[!UICONTROL Transfert de ressources]** | Cette action n’est disponible que lors de la sélection d’un utilisateur. Si l’utilisateur dispose de ressources pouvant être transférées, vous pouvez sélectionner les éléments du compte (tels que des signets, des tableaux de bord, etc.). Sélectionnez **[!UICONTROL Transfert]** pour terminer le transfert.<br/>![Transfère des ressources](assets/transfer-assets.png) |
| ![Supprimer des comptes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Supprimer des comptes]** | Une boîte de dialogue s’affiche pour confirmer la suppression des comptes sélectionnés. Sélectionnez **[!UICONTROL OK]** pour supprimer les comptes. Sélectionnez **[!UICONTROL Annuler]** pour annuler. |
| ![Exporter au format CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL Exporter au format CSV]** | Cette action télécharge immédiatement un fichier contenant une liste de valeurs séparées par des virgules des utilisateurs sélectionnés avec leurs détails (nom, statut de migration, e-mail, etc.). |

