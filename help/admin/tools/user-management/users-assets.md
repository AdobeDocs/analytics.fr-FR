---
description: Gérez les utilisateurs d’Analytics et leurs ressources dans Adobe Admin Console.
title: Gestion des utilisateurs et des ressources Analytics
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
TQID: 'https://experienceleague.adobe.com/d8CK9Vf-eaEU6P9386J1eO-JpD5u4l3VoqRcMwvXcW0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
    internal-label: User management
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8badbfc74bdc95a8ab673d4f00fe13e0829e64bb
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 5%
---
# Gestion des comptes utilisateur, ressources et expirations hérités

Vous pouvez gérer les comptes utilisateur hérités, leur statut de migration, les données d’expiration, le transfert de ressources à d’autres utilisateurs, etc. à l’aide de **[!UICONTROL Admin] > [!UICONTROL Tous les administrateurs] > [!UICONTROL Utilisateurs et administrateurs Analytics]**.

L’écran Utilisateurs affiche une liste des utilisateurs Adobe Analytics actuels, avec les colonnes suivantes :

| Colonne | Description |
|---|---|
| [!UICONTROL Identifiant utilisateur] | Identifiant utilisateur que l’utilisateur utilise pour se connecter à Adobe Analytics. |
| [!UICONTROL Nom] | Nom de l’utilisateur. |
| [!UICONTROL Statut de migration] | Statut de la migration d’un compte utilisateur hérité vers Enterprise ID ou Adobe ID.  Le statut peut être Non initié, En file d’attente ou Migré. |
| [!UICONTROL Adresse électronique] | L’e-mail de l’utilisateur ou de l’utilisatrice |
| [!UICONTROL Connexion héritée] | Statut de la connexion héritée, qui peut être Activé ou Désactivé. |
| [!UICONTROL Date de création] | Date et heure de création du compte utilisateur dans Adobe Analytics. |
| [!UICONTROL Dernier accès à Analytics] | la date et l’heure du dernier accès du compte utilisateur à Adobe Analytics, |
| [!UICONTROL Expiration] | Date d’expiration du compte d’utilisateur ou Aucun si le compte d’utilisateur n’expire pas. |

![Utilisateurs](assets/users.png)

- Pour rechercher un utilisateur spécifique, utilisez le champ ![Rechercher](/help/assets/icons/Search.svg) *Rechercher par titre*.
- Pour filtrer la liste selon le statut de migration, sélectionnez ![Chevron](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Statut de migration]**.
- Pour filtrer la liste selon le statut de connexion hérité, sélectionnez ![Chevron](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Connexion héritée]**.
- Pour modifier l’affichage des colonnes, sélectionnez ![Paramètres des colonnes](/help/assets/icons/ColumnSetting.svg) et sélectionnez les colonnes dans la fenêtre contextuelle.

Vous pouvez appliquer différentes actions lors de la sélection d&#39;un ou plusieurs utilisateurs dans la liste :

| Action | Description |
|---|---|
| ![Migrer](/help/assets/icons/Briefcase.svg) **[!UICONTROL Migrer]** | Vous pouvez migrer un ou plusieurs utilisateurs vers des Enterprise ID ou des Adobe ID. |
| ![ Calendrier verrouillé ](/help/assets/icons/CalendarLocked.svg) **[!UICONTROL Définir l’expiration]** | Vous pouvez définir une date d’expiration pour l’utilisation de la connexion Adobe Analytics héritée pour les utilisateurs sélectionnés.  Sélectionnez la date à utiliser dans une fenêtre contextuelle de calendrier pour spécifier la date. Sélectionnez **[!UICONTROL Terminé]** pour confirmer l’expiration. |
| ![Transfert de ressources](/help/assets/icons/Switch.svg) **[!UICONTROL Transfert de ressources]** | Cette action n’est disponible que lors de la sélection d’un utilisateur. Si l’utilisateur dispose de ressources pouvant être transférées, vous pouvez sélectionner les éléments du compte (tels que des signets, des tableaux de bord, etc.). Sélectionnez **[!UICONTROL Transfert]** pour terminer le transfert.<br/>![Transfère des ressources](assets/transfer-assets.png) |
| ![Supprimer des comptes](/help/assets/icons/Delete.svg) **[!UICONTROL Supprimer des comptes]** | Une boîte de dialogue s’affiche pour confirmer la suppression des comptes sélectionnés. Sélectionnez **[!UICONTROL OK]** pour supprimer les comptes. Sélectionnez **[!UICONTROL Annuler]** pour annuler. |
| ![Exporter au format CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exporter au format CSV]** | Cette action télécharge immédiatement un fichier contenant une liste de valeurs séparées par des virgules des utilisateurs sélectionnés avec leurs détails (nom, statut de migration, e-mail, etc.). |

