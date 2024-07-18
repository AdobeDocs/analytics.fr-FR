---
description: Découvrez comment effectuer la migration des règles de traitement Mobile Services vers Adobe Analytics.
title: Migration des règles de traitement Mobile Services vers Adobe Analytics
feature: Processing Rules
exl-id: ea183c1a-a85e-4f4e-a7f6-f947b939e9d9
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 90%

---

# Migration des règles de traitement Mobile Services vers Adobe Analytics

Ce document vous explique la procédure à suivre pour effectuer la migration de règles de traitement supplémentaires (au-delà des mesures de cycle de vie) que vous avez créées dans l’interface utilisateur de Mobile Services vers Adobe Analytics.

Les règles de traitement servent à déplacer des valeurs des variables Données contextuelles vers des props et des eVars. Par exemple, vous pouvez placer la valeur d’une variable de données contextuelles de « terme de recherche » dans la valeur d’une eVar de variable commerciale et remplacer cette valeur sur chaque accès. Sans règles de traitement, les variables de données contextuelles n’ont aucun sens et ne renseignent des données dans aucun rapport dans Analytics.

Ce document vous indique également comment effectuer un compte rendu des performances d’utilisation mobile dans Analysis Workspace.

## Migration des règles de traitement

Si vous utilisez Mobile Services pour des fonctionnalités gratuites telles que les règles de traitement et les fonctions de compte rendu des performances d’utilisation, vous pouvez passer facilement à l’interface utilisateur d’Analytics (interface utilisateur des règles de traitement ou Analysis Workspace) pour accomplir ces fonctions. Pour les mesures de cycle de vie ou les règles configurées dans l’interface utilisateur des règles de traitement d’AA, il n’est pas nécessaire d’effectuer de migration. Les mesures de cycle de vie sont des mesures prêtes à l’emploi qui sont automatiquement collectées lors de la première implémentation du SDK mobile dans votre application.

Cependant, si vous configurez des règles de traitement supplémentaires dans l’interface utilisateur de Mobile Services (au-delà des mesures de cycle de vie), vous devez les déplacer afin de pouvoir les modifier ou les supprimer dans Analytics après avoir perdu l’accès à Mobile Services.

1. Connectez-vous à `experience.adobe.com` et accédez à Mobile Services.
1. Cliquez sur l’icône d’engrenage d’une application mobile pour laquelle vous souhaitez déplacer les correspondances de variables contextuelles vers Adobe Analytics.
1. Cliquez sur l’élément de menu **[!UICONTROL Gérer les variables et les mesures]**, puis sur l’onglet **[!UICONTROL Variables personnalisées]**. Là, vous pouvez voir quelles correspondances de variables contextuelles (données contextuelles) ont été ajoutés à la configuration. Notez ces configurations (ou faites une copie d’écran). Exemple :

   ![Variable contextuelle](assets/context-var.png)

1. Dans Experience Cloud, passez à Adobe Analytics et vérifiez que vous vous trouvez dans la même suite de rapports mobile que celle que vous avez consultée dans Mobile Services.
1. Accédez à **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de traitement]**.
1. Cliquez sur **[!UICONTROL Ajouter une règle]**.
1. Ignorez les conditions et continuez à ajouter la ou les même(s) variable(s) contextuelle(s) existant dans Mobile Services.

   ![Règle de traitement](assets/proc-rule.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Compte rendu des performances d’utilisation mobile dans Analysis Workspace

Outre les mesures et dimensions mobiles (si la suite de rapports est activée pour Mobile Services), Analysis Workspace contient plusieurs modèles de projets mobiles qui peuvent faciliter l’analyse :

* **[!UICONTROL Messagerie]** : est axée sur les performances de la messagerie in-app et push.
* **[!UICONTROL Emplacement]** : comprend une carte représentant les données d’emplacement.
* **[!UICONTROL Mesures clés]** : sachez de quelle façon se comportent les mesures clés de votre application.
* **[!UICONTROL Utilisation de l’application]** : combien d’utilisateurs, de lancements et de premiers lancements avait l’application et quelle est la durée de session moyenne ?
* **[!UICONTROL Acquisition]** : quelles sont les performances des liens d’acquisition mobile ?
* **[!UICONTROL Performances]** : quelles sont les performances de l’application et où les utilisateurs rencontrent-ils des problèmes ?
* **[!UICONTROL Rétention]** : qui sont mes fidèles utilisateurs et que font-ils ?
* **[!UICONTROL Parcours]** : quels sont les schémas d’utilisation dominants de mon application ?

Voici un extrait du modèle d’utilisation des applications mobiles :

![Utilisation des applications mobiles](assets/mobile-app-usage.png)

Pour accéder aux modèles :

1. Connectez-vous à `experience.adobe.com` et sélectionnez Analytics.
1. Assurez-vous que vous vous trouvez dans une suite de rapports activée pour Mobile Services.
1. Cliquez sur l’onglet **[!UICONTROL Workspace]**.
1. Cliquez sur **[!UICONTROL Créer un projet]**.
1. Sélectionnez l’un des modèles mobiles et cliquez sur **[!UICONTROL Créer]**.

## Migration d’autres fonctionnalités Mobile Services

La fonctionnalité Mobile Services suivante est également liée à Adobe Analytics, mais requiert l’achat d’un SKU Adobe Analytics :

* Liens d’acquisition
* Messagerie Push
* Messagerie in-app
* Gestion des points d’intérêt de localisation

Si vous utilisez Mobile Services pour les fonctionnalités payantes, vous n’avez pas de chemin de migration viable vers d’autres outils internes/externes :

* Pour les liens d’acquisition, nous pouvons vous diriger vers des partenaires d’Adobe qui pourront répondre à vos besoins.
* Les messageries push et in-app sont disponibles dans Adobe Campaign Standard et Adobe Campaign Classic (push uniquement). Cependant, le jeu de données sous-jacent utilisé pour le ciblage est différent. Nous vous suggérons de travailler avec l’équipe qui se charge de vos comptes Adobe afin de déterminer les options de migration pour les données de messagerie.
* Pour la fonctionnalité de position, nous vous recommandons d’adopter le nouveau [service de localisation Adobe Experience Platform](https://www.adobe.com/fr/experience-platform/location-service.html), qui est gratuit pour tous les clients Adobe Experience Platform.
