---
description: Configurez une suite de rapports mappée CX Enterprise à utiliser dans Advertising Analytics.
title: Activation de la suite de rapports pour Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
TQID: 'https://experienceleague.adobe.com/sGEXiz2RiDhf9p-2df76o-XxBERTKPB-O-rZeIb4BBI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: fe0a7292-80bc-407a-b456-64170267d1cc
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 18%

---

# Activation de la suite de rapports pour Advertising Analytics

Pour afficher des données de recherche Advertising Analytics dans Analytics, vous devez configurer chaque suite de rapports CX mappée aux entreprises pour la création de rapports Advertising Analytics.

1. Accédez à **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.

1. Sélectionnez la suite de rapports mappée à votre organisation CX Enterprise.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Configuration Advertising Analytics]**.

   ![Création de rapports](assets/aa-reporting.png)

1. Sélectionnez **[!UICONTROL Vous ne connaissez pas Advertising Analytics ? Cliquez ici pour en savoir plus]** pour plus d’informations sur Advertising Analytics.

1. Définissez l’attribution et l’expiration de la variable que la variable AMO ID doit utiliser. Les variables de conversion (eVars) permettent à Adobe Analytics d’attribuer des événements de succès à des valeurs de variable spécifiques. Parfois, les variables rencontrent plusieurs valeurs avant d’atteindre un événement de succès. Dans ce cas, l’affectation détermine la valeur de variable qui obtient le crédit pour l’événement.

   | Paramètre | Définition |
   |--- |--- |
   | **[!UICONTROL Attribution]** | Sélectionner entre:<br/> **[!UICONTROL Valeur d’origine (première)]** : la première valeur vue obtient le crédit d’affectation complet, quelles que soient les valeurs suivantes pour cette variable. <br/>**[!UICONTROL La plus récente (dernière)]**: la dernière valeur vue obtient le crédit d’affectation complet pour l’événement de succès, quelles que soient les variables déclenchées avant. |
   | **[!UICONTROL Expire après]** | Permet de définir une période, ou un événement, à l’issue de laquelle ou duquel la valeur eVar expire (c’est-à-dire sans recevoir de crédit pour les événements de succès).  Si un événement de succès se produit après l’expiration de l’eVar, la valeur Aucun reçoit le crédit pour l’événement (aucune valeur eVar n’était active). |

1. Cliquez sur **[!UICONTROL Activer le reporting Advertising Analytics]** (première fois) ou **[!UICONTROL Mettre à jour le reporting Advertising Analytics]** (fois suivantes). Votre suite de rapports est maintenant prête à recevoir les données de recherche Advertising Analytics. Vous êtes maintenant prêt à [créer des comptes Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
