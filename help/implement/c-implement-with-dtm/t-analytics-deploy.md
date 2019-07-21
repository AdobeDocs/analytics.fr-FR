---
description: Créez un outil Adobe Analytics pour le déploiement à l’aide de Dynamic Tag Management. Cette procédure décrit une mise en œuvre (héritée) manuelle.
keywords: Dynamic Tag Management
seo-description: Créez un outil Adobe Analytics pour le déploiement à l’aide de Dynamic Tag Management. Cette procédure décrit une mise en œuvre (héritée) manuelle.
seo-title: Mise en œuvre manuelle d’Adobe Analytics (héritée)
solution: Marketing Cloud, Analytics, Target, gestion dynamique des balises
title: Mise en œuvre manuelle d’Adobe Analytics (héritée)
uuid: d 3 ad 2035-393 d -4 a 77-81 f 6-e 749 ee 717 c 09
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Mise en œuvre manuelle d’Adobe Analytics (héritée)

Create an Adobe Analytics tool for deployment using [!UICONTROL Dynamic Tag Management]. Cette procédure décrit une implémentation (héritée) manuelle.

Pour plus d’informations sur la gestion de l’implémentation automatique, voir [Ajout de l’outil Adobe Analytics](../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8).

Si vous souhaitez passer une configuration manuelle sur automatique, modifiez un outil et cliquez sur **[!UICONTROL Activer la configuration automatique]**.

1. Téléchargez le code de mesure Analytics : 
   1. In Analytics, click **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.
   1. Click **[!UICONTROL JavaScript (new)]** to download the code locally.
1. In [!UICONTROL Dynamic Tag Management], [create a web property](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123).

   ![](assets/dtm-property.png)

   Une fois la propriété web créée, elle peut être modifiée sous l’onglet [!UICONTROL Propriétés web] du [!UICONTROL tableau de bord]. Il n’est pas nécessaire d’activer la propriété web..

1. Ajoutez un outil Analytics à la propriété :
   1. On the **[!UICONTROL Web Properties]** tab, click the property.
   1. On the **[!UICONTROL Overview]** tab, click **[!UICONTROL Add a Tool]**.
   1. From the **[!UICONTROL Tool Type]** menu, select **[!UICONTROL Adobe Analytics]**.

      ![](assets/dtm-add-analytics-tool.png)

   1. Renseignez les champs suivants :

      | Élément | Description |
      |---|---|
      | Type d’outil | Solution Experience Cloud telle qu’Analytics, Target, Social, etc. |
      | Nom de l’outil | Nom de cet outil. Ce nom apparaît dans la section [!UICONTROL Outils installés] de l’onglet [!UICONTROL Aperçu]. |
      | ID du compte de production | Numéro de votre compte de production pour la collecte de données. Dynamic Tag Management installe automatiquement le compte correct dans l’environnement de production et d’évaluation. |
      | ID du compte d’évaluation | Numéro utilisé dans votre environnement de développement ou de test. Un compte d’évaluation permet de séparer vos données de test de l’environnement de production. |

1. Cliquez sur **[!UICONTROL Créer l’outil]**.

   L’outil installé s’affiche sous l’onglet [!UICONTROL Aperçu].

1. To configure the code, click **[!UICONTROL Settings]** ![](assets/settings_gear.png).

   Cliquez sur **[!UICONTROL Cookies], puis configurez le serveur de suivi et le serveur de suivi SSL au minimum.**

1. Click **[!UICONTROL General]** and [insert the core AppMeasurement code](../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658).
1. Define a [page load rule](../../implement/c-implement-with-dtm/c-rules/t-rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB) to collect [!DNL Analytics]data.

   Vous pouvez à présent définir des règles pour collecter les données d’analyse. Il est possible que vous souhaitiez définir d’abord quelques éléments de données. Les éléments de données permettent d’extraire les données de la page que vous pouvez utiliser pour configurer une règle. Pour commencer, vous pouvez définir une règle de chargement de page sans conditions pour collecter les données [!DNL Analytics] de chaque page.
1. [Ajoutez le code d’en-tête et de pied de page](../../implement/c-implement-with-dtm/c-headers-footers/t-header-footer-code.md#task_43C8DD699A514638B0620775C06423E5) sous l’onglet Incorporer.

   Pour un déploiement d’évaluation, vous pouvez conserver l’option d’hébergement Amazon par défaut. Vous pouvez la modifier, si nécessaire, avant le déploiement en production.
1. (Optional) Click **[!UICONTROL Settings]** ![](assets/settings_gear.png) on the Options tab, and configure the Adobe Analytics code.

   >[!NOTE]
   >
   >The settings on the [!UICONTROL Adobe Analytics] page (General, Cookies, and so on) override settings in your `s_code`. Si ces paramètres existent dans le `s_code`, il n’est pas nécessaire de les réitérer.

