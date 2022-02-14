---
title: Aperçu des annotations
description: Utilisation des annotations dans Workspace.
role: User, Admin
solution: Analytics
exl-id: 722d7636-f619-479a-97f1-3da23e8f7f83
source-git-commit: 38170806d0fbf6ae373ae089872f8d25306f416e
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 2%

---

# Aperçu des annotations

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de tests limités.

Les annotations vous permettent de communiquer efficacement des nuances et des informations contextuelles à votre organisation. Ils vous permettent de lier des événements de calendrier à des dimensions/mesures spécifiques. Vous pouvez annoter une période ou une période avec des problèmes de données connus, des jours fériés, des lancements de campagne, etc. Vous pouvez ensuite afficher les événements sous forme graphique afin de déterminer si des campagnes ou d’autres événements ont eu un impact sur le trafic, les recettes ou toute autre mesure de votre site.

Supposons, par exemple, que vous partagiez des projets avec votre organisation. Si un pic de trafic important est dû à un événement de vente, vous pouvez créer une annotation &quot;Date de lancement de campagne&quot; et l’étendre à l’ensemble de la suite de rapports. Lorsque vos utilisateurs visualisaient des jeux de données incluant cette date, l’annotation apparaissait dans leurs projets, ainsi que leurs données.

![](assets/multi-day.png)

N’oubliez pas ce qui suit :

* Les annotations peuvent être liées à une seule date ou à une période.

* Ils peuvent s’appliquer à l’ensemble de votre jeu de données ou à des mesures, dimensions ou segments spécifiés.

* Ils peuvent s’appliquer au projet dans lequel ils ont été créés (par défaut) ou à tous les projets.

* Elles peuvent s’appliquer à la suite de rapports dans laquelle elles ont été créées (par défaut) ou à toutes les suites de rapports.

## Autorisations

Par défaut, seuls les administrateurs peuvent créer des annotations. Les utilisateurs ont les droits d’afficher les annotations comme ils le font avec d’autres composants d’Analytics (tels que les segments, les mesures calculées, etc.).

Toutefois, les administrateurs peuvent attribuer la variable [!UICONTROL Création d’annotations] Autorisation (outils Analytics) des utilisateurs via l’ [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html?lang=en).

## Activation ou désactivation des annotations

Les annotations peuvent être activées ou désactivées à plusieurs niveaux :

* Au niveau de la visualisation : [!UICONTROL Visualisation] paramètres > [!UICONTROL Afficher les annotations]

* Au niveau du projet : [!UICONTROL Informations et paramètres du projet] > [!UICONTROL Afficher les annotations]

* Au niveau de l’utilisateur : [!UICONTROL Composants] > [!UICONTROL Préférences utilisateur] > [!UICONTROL Données] > [!UICONTROL Afficher les annotations]

![](assets/show-ann.png)

![](assets/show-ann2.png)
