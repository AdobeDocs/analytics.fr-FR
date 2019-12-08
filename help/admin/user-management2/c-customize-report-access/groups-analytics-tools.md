---
description: Activez les autorisations d’utilisateurs pour les éléments généraux (facturation, journaux, etc.), la gestion des entreprises, l’accès aux services web, le Report Builder et l’intégration des Data Connectors.
keywords: groups;permissions
subtopic: Users and groups
title: Personnalisation des autorisations liées aux outils Analytics
topic: Admin tools
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Personnalisation des autorisations liées aux outils Analytics

>[!IMPORTANT]
>
>La gestion des utilisateurs et des produits a désormais lieu dans [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe vous avertira lorsqu’il sera temps de migrer les utilisateurs. Une fois tous les utilisateurs migrés, le contenu d’aide **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Gestion des utilisateurs]** sera retiré.

Activez les autorisations d’utilisateurs pour les éléments généraux (facturation, journaux, etc.), la gestion des entreprises, l’accès aux services web, le Report Builder et l’intégration des Data Connectors.

**[!UICONTROL Gestion des utilisateurs]** &gt; **[!UICONTROL Groupes]** &gt; **[!UICONTROL Accès à tous les rapports]** &gt; **[!UICONTROL Outils Analytics]** &gt; **[!UICONTROL Personnaliser]**

> [!NOTE] La gestion des groupes a été modifiée dans la version de l’automne 2016 (20 octobre). Reportez-vous à la section [Changements administratifs – Automne 2016](/help/admin/user-management2/c-user-management/permissions-changes.md) pour consulter un récapitulatif des changements.

## Accès aux rapports – Outils Analytics

![](assets/report-access-analytics-tools.png)

Cliquez sur **[!UICONTROL Personnaliser]** pour sélectionner les fonctionnalités auxquelles ce groupe aura accès.

## Descriptions des champs

Les paramètres sur cette page se rapportent aux suites de rapports sélectionnées sur la page [!UICONTROL Définir un groupe d’utilisateurs].

| Élément | Description |
|--- |--- |
| **Général** |  |
| [Gestionnaire de code](/help/admin/admin/code-manager-admin.md) | Permet d’autoriser le téléchargement du code de collecte de données pour les plateformes web et mobiles. |
| Code Manager – Web Services | Permet à un utilisateur non-administrateur d’accéder au gestionnaire de code par l’intermédiaire des services web. |
| [Journaux](/help/admin/admin/logs.md) | Permet d’accéder aux fichiers journaux, grâce auxquels il est possible de savoir quand se connectent les utilisateurs, leur utilisation, l’accès, les suites de rapports et les changements administratifs. |
| Logs – Web Services | Permet à un utilisateur non-administrateur d’accéder aux fichiers journaux des outils d’administration par l’intermédiaire des services web. |
| [Gestion du trafic](/help/admin/c-traffic-management/traffic-management.md) | Sur la page Gestion du trafic, vous pouvez spécifier les changements prévus en termes de volume de trafic. |
| Gestion des autorisations | Donne aux utilisateurs non-administrateurs l’accès aux pages de gestion des utilisateurs dans les outils d’administration. Ces utilisateurs ont des autorisations en lecture, mais pas en écriture. |
| Permissions (Write) – Web Services | Accorde aux utilisateurs non administrateurs des paramètres d’autorisation de lecture et d’écriture dans l’option Gestion utilisateur des services web.<br>Ce paramètre fait spécifiquement référence aux actions d’autorisations indiquées dans l’API Admin. |
| Autorisations (lecture) – Services web | Permet à un utilisateur non-administrateur d’afficher les paramètres d’autorisation sous Gestion des utilisateurs dans les services web.<br>Ce paramètre fait spécifiquement référence aux actions d’autorisations indiquées dans l’API Admin. |
| **Gestion des entreprises** |  |
| [Sécurité](/help/admin/company/security-manager.md) | Donne accès à la page Gestionnaire de sécurité d’où vous pouvez contrôler l’accès aux données de création de rapports. Les options incluent les mots de passe difficiles à deviner, l’expiration du mot de passe, ainsi que les restrictions d’adresses IP et de domaines de courriel. |
| Informations sur l’assistance | Permet d’autoriser l’accès aux Informations sur l’assistance dans les Paramètres de la société. |
| [Services web](/help/admin/company/web-services-admin.md) | Autorise l’accès à la page Services web dans l’interface Outils d’administration ([!UICONTROL Paramètres de la société] &gt; [!UICONTROL Services web]).<br>L’API Services web fournit un accès par programmation aux services Adobe Analytics grâce auxquels vous pouvez dupliquer et amplifier les fonctionnalités disponibles dans l’interface utilisateur. |
| Connexion unique (héritée) | Permet d’octroyer l’accès à la page d’authentification unique dans les outils d’administration.<br>**Remarque :** dans Adobe Experience Cloud, l’authentification unique est mise en œuvre en [associant les comptes](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html) d’Experience Cloud et des solutions. |
| [Actions en attente](/help/admin/company/pending-actions-admin.md) | Permet d’autoriser la gestion des actions en attente dans les [!UICONTROL Paramètres de la société]. |
| [Alliance de marques](/help/admin/company/co-branding-admin.md) | Permet d’autoriser l’alliance des marques Analytics. |
| [Préférences](/help/admin/admin/preferences-manager.md) | Permet d’autoriser l’accès au [!UICONTROL Gestionnaire des préférences]. |
| [Masquage des suites de rapports](/help/admin/company/c-hide-report-suites.md) | Permet d’autoriser le masquage des suites de rapports dans l’interface utilisateur d’Adobe Analytics. |
| **Outils** | Ces paramètres donnent accès aux outils Analytics (interfaces et applications) et aux fonctionnalités avancées telles que la segmentation et les mesures calculées. |
| [Données actives](https://marketing.adobe.com/resources/help/en_US/reference/data_latency.html) | Permet d’autoriser l’utilisation de la fonction Données actives dans les rapports. |
| [Utilisateurs de la licence d’Ad Hoc Analysis](https://marketing.adobe.com/resources/help/en_US/dsc/) | Octroie l’autorisation d’accéder aux [!UICONTROL Ad Hoc Analysis]. |
| Accès aux services Web | Permet aux non-administrateurs d’accéder aux services web. Génère les informations de connexion des services web. |
| [Report Builder](https://marketing.adobe.com/resources/help/en_US/arb/setup.html) | Octroie aux membres de ce groupe un accès aux licences du [!UICONTROL Report Builder]. |
| [Accès à Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) | Octroie aux utilisateurs un accès à Analysis Workspace, l’interface de création de rapports recommandée pour [!DNL Adobe Analytics]. |
| [Reports &amp; Analytics](https://marketing.adobe.com/resources/help/en_US/sc/user/) | Octroie aux utilisateurs l’accès aux Reports &amp; Analytics. |
| [Création de mesure calculée](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) | Octroie aux utilisateurs l’autorisation de créer des mesures calculées. |
| [Création de segment](https://marketing.adobe.com/resources/help/en_US/analytics/segment/) | Octroie aux utilisateurs l’autorisation de créer des segments. |
| **Data Connectors** |  |
| Intégrations (créer, mettre à jour ou supprimer) | Octroie aux utilisateurs l’autorisation de créer, de mettre à jour et de supprimer des intégrations du connecteur de données. |
