---
description: valeur nulle
title: Activation de la suite de rapports pour Advertising Analytics
uuid: 934f0e02-b5d7-4eca-93d8-92f95bd7014a
translation-type: tm+mt
source-git-commit: a492de4ccbcd6f3f8ca81c9fecbcca4780e0f589
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 100%

---


# Activation de la suite de rapports pour Advertising Analytics

Afin d’afficher toutes les données de recherche Advertising Analytics dans Analytics, vous devez configurer chaque suite de rapports mappée à Experience Cloud pour le reporting Advertising Analytics.

1. [Mappez votre suite de rapports à une organisation](https://docs.adobe.com/content/help/fr-FR/core-services/interface/about-core-services/report-suite-mapping.html).
1. Accédez à **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.

1. Sélectionnez la suite de rapports qui est mappée à votre organisation Experience Cloud.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Configuration Advertising Analytics]**.

   ![Création de rapports](assets/aa_reporting.png)

   >[!IMPORTANT] AMO ID renvoie à la variable Adobe Advertising Cloud dans laquelle les données de recherche seront insérées.

1. Définissez la variable d’attribution et d’expiration que la variable AMO ID doit utiliser. Les variables de conversion (eVars) permettent à Adobe Analytics d’affecter des événements de succès à des valeurs de variables spécifiques. Parfois, les variables rencontrent plusieurs valeurs avant d’accéder à un événement de succès. Dans ce cas, l’affectation détermine la valeur de variable qui obtient un crédit pour l’événement.

   | Paramètre | Définition |
   |--- |--- |
   | Valeur d’origine (première) | La première valeur vue obtient un crédit complet, quelles que soient les valeurs suivantes de cette variable. |
   | La plus récente (dernière) | La dernière valeur vue obtient un crédit complet pour l’événement de succès, quelles que soient les variables lancées avant elle. |
   | Expire après | Permet d’indiquer une période, ou un événement, à l’issue de laquelle (ou duquel) la valeur eVar arrive à expiration (c.-à-d. elle ne reçoit plus de crédit pour les événements de succès).  Si un événement de succès se produit après l’expiration de l’eVar, la valeur Aucun reçoit le crédit pour l’événement (aucune valeur eVar n’était active). |

1. Cliquez sur **[!UICONTROL Activer la création de rapports Advertising Analytics]** (la première fois) ou sur **[!UICONTROL Mise à jour de la création de rapports Advertising Analytics]** (les fois suivantes). La suite de rapports est maintenant prête à recevoir des données de recherche Advertising Analytics. Vous pouvez maintenant [créer des comptes Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).

