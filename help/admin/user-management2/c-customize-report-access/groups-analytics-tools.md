---
description: Activez les autorisations d’utilisateurs pour les éléments généraux (facturation, journaux, etc.), la gestion des entreprises, l’accès aux services web, le Report Builder et l’intégration des Data Connectors.
keywords: groups;permissions
subtopic: Users and groups
title: Personnalisation des autorisations liées aux outils Analytics
topic: Admin tools
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Personnalisation des autorisations liées aux outils Analytics

>[!IMPORTANT]
>
>La gestion des utilisateurs et des produits a désormais lieu dans [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Adobe vous avertira lorsqu’il sera temps de migrer les utilisateurs. After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** will be retired.

Activez les autorisations d’utilisateurs pour les éléments généraux (facturation, journaux, etc.), la gestion des entreprises, l’accès aux services web, le Report Builder et l’intégration des Data Connectors.

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL All Report Access]** > **[!UICONTROL Analytics Tools]** > **[!UICONTROL Customize]**

>[!NOTE] La gestion des groupes a été modifiée dans la version d’automne 2016 (20 octobre). Reportez-vous à la section [Changements administratifs – Automne 2016](/help/admin/user-management2/c-user-management/permissions-changes.md) pour consulter un récapitulatif des changements.

## Accès aux rapports – Outils Analytics

![](assets/report-access-analytics-tools.png)

Click **[!UICONTROL Customize]** to select items to which this group will have access.

## Descriptions des champs

Les paramètres de cette page concernent les suites de rapports sélectionnées sur la [!UICONTROL Define User Groups] page.

| Elément | Description |
|--- |--- |
| **Général** |  |
| [Gestionnaire de code](/help/admin/admin/code-manager-admin.md) | Permet d’autoriser le téléchargement du code de collecte de données pour les plateformes Web et mobiles. |
| Code Manager – Web Services | Permet à un utilisateur non-administrateur d’accéder au Gestionnaire de code par le biais des services Web. |
| [Journaux](/help/admin/admin/logs.md) | Permet d’autoriser les fichiers journaux, ce qui vous permet de déterminer le moment où les utilisateurs se connectent, leur utilisation, l’accès, les suites de rapports et les modifications apportées par l’administrateur. |
| Logs – Web Services | Permet à un utilisateur non-administrateur d’accéder aux journaux des outils d’administration via les services Web. |
| [Gestion du trafic](/help/admin/c-traffic-management/traffic-management.md) | La page Gestion du trafic vous permet de spécifier les changements prévus du volume de trafic. |
| Gestion des autorisations | Permet aux utilisateurs non administrateurs d’accéder aux pages Gestion des utilisateurs dans les outils d’administration. Ces utilisateurs disposent d’autorisations de lecture, mais pas d’autorisations d’écriture. |
| Autorisations (écriture) - Services Web | Octroie aux utilisateurs non administrateurs des autorisations de lecture et d’écriture sous Gestion des utilisateurs dans les services Web.<br>Ce paramètre fait spécifiquement référence aux actions d’autorisations indiquées dans l’API Admin. |
| Autorisations (lecture) – Services web | Permet à un utilisateur non-administrateur d’de paramètres d’autorisation sous Gestion des utilisateurs dans les services Web.<br>Ce paramètre fait spécifiquement référence aux actions d’autorisations indiquées dans l’API Admin. |
| **Gestion des entreprises** |  |
| [Sécurité](/help/admin/company/security-manager.md) | Donne accès à la page Gestionnaire de sécurité d’où vous pouvez contrôler l’accès aux données de création de rapports. Les options incluent les mots de passe difficiles à deviner, l’expiration du mot de passe, ainsi que les restrictions d’adresses IP et de domaines de courriel. |
| Informations sur l’assistance | Permet d’autoriser l’accès aux Informations sur l’assistance dans les Paramètres de la société. |
| [Services web](/help/admin/company/web-services-admin.md) | Permet d’accéder à la page Services Web dans l’interface Outils d’administration ([!UICONTROL Company Settings] > [!UICONTROL Web Services]).<br>L’API Services web fournit un accès par programmation aux services Adobe Analytics grâce auxquels vous pouvez dupliquer et amplifier les fonctionnalités disponibles dans l’interface utilisateur. |
| Authentification unique (héritée) | Accorde l’accès à la page de connexion unique dans les outils d’administration.<br>**Remarque :**dans Adobe Experience Cloud, l’authentification unique est mise en œuvre en[associant les comptes](https://marketing.adobe.com/resources/help/fr_FR/mcloud/organizations.html)d’Experience Cloud et des solutions. |
| [Actions en attente](/help/admin/company/pending-actions-admin.md) | Grants permission to manage pending actions in [!UICONTROL Company Settings]. |
| [Alliance de marques](/help/admin/company/co-branding-admin.md) | Permet d’autoriser l’alliance des marques Analytics. |
| [Préférences](/help/admin/admin/preferences-manager.md) | Permet d’octroyer l’autorisation au [!UICONTROL Preference Manager]. |
| [Masquage des suites de rapports](/help/admin/company/c-hide-report-suites.md) | Permet d’autoriser le masquage des suites de rapports dans l’interface utilisateur d’Adobe Analytics. |
| **Outils** | Ces paramètres donnent accès aux outils Analytics (interfaces et applications) et aux fonctionnalités avancées telles que la segmentation et les mesures calculées. |
| [Données actives](https://marketing.adobe.com/resources/help/fr_FR/reference/data_latency.html) | Permet d’autoriser l’utilisation de la fonction Données actives dans les  de. |
| [Utilisateurs de la licence d’Ad Hoc Analysis](https://marketing.adobe.com/resources/help/fr_FR/dsc/) | Permet d’autoriser l’accès [!UICONTROL Ad Hoc Analysis]. |
| Accès aux services Web | Active l’accès aux services Web pour les non-administrateurs. Génère les informations d’identification du service Web. |
| [Report Builder](https://marketing.adobe.com/resources/help/fr_FR/arb/setup.html) | Accorde aux membres de ce groupe l’accès aux [!UICONTROL Report Builder] licences. |
| [Accès à Analysis Workspace](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/) | Octroie aux utilisateurs un accès à Analysis Workspace, l’interface de création de rapports recommandée pour [!DNL Adobe Analytics]. |
| [Reports &amp; Analytics](https://marketing.adobe.com/resources/help/fr_FR/sc/user/) | Octroie aux utilisateurs l’accès aux Reports &amp; Analytics. |
| [Création de mesure calculée](https://marketing.adobe.com/resources/help/fr_FR/analytics/calcmetrics/) | Octroie aux utilisateurs l’autorisation de créer des mesures calculées. |
| [Création de segment](https://marketing.adobe.com/resources/help/fr_FR/analytics/segment/) | Octroie aux utilisateurs l’autorisation de créer des segments. |
| **Data Connectors** |  |
| Intégrations (Créer, Mettre à jour ou Supprimer) | Octroie aux utilisateurs l’autorisation de créer, de mettre à jour et de supprimer des intégrations du connecteur de données. |
