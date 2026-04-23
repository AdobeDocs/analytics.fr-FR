---
description: Configuration d’une suite de rapports mappée à Experience Cloud à utiliser dans Advertising Analytics.
title: Activation de la suite de rapports pour Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 27%

---

# Activation de la suite de rapports pour Advertising Analytics

To see any Advertising Analytics search data in Analytics, you need to configure each Experience Cloud-mapped report suite for Advertising Analytics reporting.

1. Accédez à **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.

1. Sélectionnez la suite de rapports qui est mappée à votre organisation Experience Cloud.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Configuration Advertising Analytics]**.

   ![Création de rapports](assets/aa-reporting.png)

1. Select **[!UICONTROL Unfamiliar with Advertising Analytics? Click here to learn more]** for more information on Advertising Analytics.

1. Set the variable allocation and expiration that you want the AMO ID variable to use. Conversion variables (eVars) allow Adobe Analytics to attribute success events to specific variable values. Sometimes, variables encounter more than one value before hitting a success event. For these cases, allocation determines which variable value gets credit for the event.

   | Paramètre | Définition |
   |--- |--- |
   | **[!UICONTROL Attribution]** | Select between:<br/> **[!UICONTROL Original Value (First)]**: The first value seen gets full allocation credit, no matter what subsequent values for that variable are. <br/>**[!UICONTROL Most Recent (Last)]**: The last value seen gets full allocation credit for the success event, no matter what variables were fired before it. |
   | **[!UICONTROL Expire après]** | Lets you specify a time period, or event, after which the eVar value expires (that is, no longer receives credit for success events).  Si un événement de succès se produit après l’expiration de l’eVar, la valeur Aucun reçoit le crédit pour l’événement (aucune valeur eVar n’était active). |

1. Click **[!UICONTROL Enable Advertising Analytics Reporting]** (first time), or **[!UICONTROL Update Advertising Analytics Reporting]** (subsequent times). Your report suite is now ready to receive Advertising Analytics Search data. You are now ready to [create Advertising Accounts](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
