---
description: Cette rubrique décrit les étapes d’administration pour configurer les rapports en temps réel.
solution: Analytics
title: Configuration de rapports en temps réel
topic: Admin tools
uuid: a2c3c515-55f2-4c64-ac92-a86d75e78a86
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Configuration de rapports en temps réel

Cette rubrique décrit les étapes d’administration pour configurer les rapports en temps réel.

Setting up real-time reports within [!UICONTROL Reports &amp; Analytics] consists of selecting the report suite and configuring up to 3 reports for it.

1. Sélectionnez la suite de rapports pour laquelle activer les rapports en temps réel.

   Navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** &gt; **[!UICONTROL View All Reports &gt; Site Metrics]** &gt; **[!UICONTROL Real-Time]** and select the report suite from the drop-down at the top:

   ![](assets/report_suite_selector.png)

   Si vous essayez d’afficher des rapports en temps réel pour une suite de rapports qui n’a pas été configurée pour la création de rapports en temps réel, un message s’affiche. Celui-ci vous permet de configurer la suite de rapports.

   ![](assets/rep_suite_not_set_up.png)

1. Click **[!UICONTROL Configure]** (gear icon) to run the [!UICONTROL Report Suite Manager].

   (Also available under **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Real-Time]**.)

1. Turn on the **[!UICONTROL Enable Real-Time]** setting.
1. Configurez la collecte de données en temps réel pour trois rapports au maximum, avec une mesure et trois dimensions ou classifications par rapport.

   ![](assets/real_time_admin.png)

   Pour plus d’informations sur les mesures et dimensions en temps réel prises en charge, voir Mesures et dimensions [prises en charge](/help/components/c-real-time-reporting/realtime-metrics.md).

   Si vous avez créé des classifications, elles apparaissent en retrait sous la dimension pour laquelle elles ont été définies :

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >Pour un rapport en temps réel unique, nous ne prenons pas actuellement en charge l’activation de dimensions en double, même si une classification différente est sélectionnée pour chaque dimension.

   Pour plus d’informations sur les classifications, voir [A propos des classifications](/help/components/c-classifications2/c-classifications.md).

   >[!NOTE]
   >
   >Certaines dimensions, telles que "Mot-clé de recherche" ou "Produit", ne sont pas conservées en temps réel comme c’est le cas ailleurs dans Adobe Analytics. Lorsque vous sélectionnez une mesure non permanente, cet avertissement s’affiche :

   ![](assets/warning_dimensions.png)

1. Click **[!UICONTROL Save]** or **[!UICONTROL Save and View Report]**.

   Après cette configuration initiale du rapport, comptez jusqu’à 20 minutes pour que les données commencent à se diffuser. À partir de ce moment, les données sont immédiatement disponibles. Pour en savoir plus sur l’affichage des rapports Temps réel, voir [Exécution d’un rapport Temps réel](https://marketing.adobe.com/resources/help/en_US/sc/user/reports_realtime.html).

1. Par défaut, tous les utilisateurs ont accès aux rapports Temps réel.
