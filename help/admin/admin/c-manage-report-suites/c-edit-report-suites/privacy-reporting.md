---
description: Activez les dimensions Gestion du consentement.
title: Compte rendu des performances sur la confidentialité
feature: Admin Tools
exl-id: 307c9ae2-2135-4a0b-9d2d-3c13a27b8361
source-git-commit: b5aba8a42f524ef3367a779e6fb1a731de680750
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 45%

---

# Compte rendu des performances sur la confidentialité

La création de rapports de confidentialité permet d’activer la fonction [Accord préalable de gestion du consentement](/help/components/dimensions/cm-opt-in.md), [Exclusion de la gestion du consentement](/help/components/dimensions/cm-opt-out.md) et [Consentement de la publicité](/help/components//dimensions/ad-consent.md) dimensions à utiliser dans les rapports.

>[!NOTE]
>
>Nous avons ajouté un nouvel indicateur Consentement de la plateforme d’annonces publicitaires. Si vous souhaitez que cette nouvelle variable prenne effet, vous devez réactiver les rapports Confidentialité des données .

Pour accéder à cette page :

1. Connectez-vous à Adobe Analytics et accédez à **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Sélectionnez une ou plusieurs suites de rapports, puis sélectionnez **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Gestion de la confidentialité]** > **[!UICONTROL Compte rendu des performances sur la confidentialité]**.

   ![Modifier les paramètres](assets/rsm-privacy-select.png)

1. Cliquez sur **[!UICONTROL Activation des rapports de confidentialité des données]**.

   >[!NOTE]
   >
   >Une fois activées, ces variables ne peuvent pas être désactivées.

   ![Activer](assets/rsm-privacy-enable.png)

1. Une fois ces variables activées, un message de confirmation s’affiche. Les dimensions sont disponibles dans les rapports.

   ![Rapport](assets/consent-management.png)

## Dimension Consentement de publicité

La variable [Dimension Consentement de publicité](/help/components/dimensions/ad-consent.md) indique si le consentement est collecté pour envoyer des données à des fournisseurs de publicité tiers, tels que Google, Meta, etc.