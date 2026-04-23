---
description: Details on the Analysis Workspace template, and reporting in Report Builder.
title: Rapport sur les données Advertising dans Adobe Analytics
feature: Advertising Analytics
exl-id: bbc830d9-e168-471d-a1ba-308277aab415
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 47%

---

# Report on advertising data

This article provide details on the Analysis Workspace report, and the reporting in Report Builder.

>[!NOTE]
>
>Expect to wait at least 24 hours before search engine data starts populating Analytics reports. Analytics reporting does not return data for hourly granularity, because Adobe Advertising data does not support hourly granularity.

## Paid search report {#section_8173F42B2C784F41B9FD82CBB66F9ADF}

This report lets anyone who implements search engine integration get access to search engine data within Analytics. You can access it via **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Acquisition]** > **[!UICONTROL Advertising Analytics: paid search]**

>[!NOTE]
>
>The Paid search report is visible to all customers, even if you have not implemented any Advertising Accounts. If you try to open the Paid search report for a company that is not provisioned, an error message will explain that you have not configured any search engine account. Select **[!UICONTROL Configure Now]**, which takes you to the [Advertising Account Setup](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) screen.

![](assets/aa_aw.png)  ![](assets/aa_aw2.png) ![](assets/aa_aw3.png) ![](assets/aa_aw4.png)  ![](assets/aa_aw5.png) ![](assets/aa_aw6.png)

| Tableau/Visualisation | Description |
|--- |--- |
| Tendances publicitaires | Présentation des tendances quotidiennes pour les Impressions AMO, les Clics AMO et le Coût AMO. |
| Plateformes d’annonces publicitaires | Donut chart for cost of top 2 platforms (Google Ads, Microsoft Advertising). |
| Totaux des plateformes d’annonces publicitaires | Tableau à structure libre des plateformes principales ventilé selon les Impressions AMO, les Clics AMO, le Coût AMO, la position moyenne AMO et la note note de qualité moyenne. |
| Comptes | Zone empilée de coûts. |
| Totaux de comptes | Tableau à structure libre des comptes principaux ventilé selon des mesures associées. |
| Campagnes | Graphique en barres du coût de la campagne. |
| Totaux de la campagne | Tableau à structure libre des campagnes principales ventilé selon des mesures associées. |
| Groupes | Arborescence des coûts. |
| Totaux des groupes | Tableau à structure libre des principaux groupes publicitaires ventilé selon des mesures associées. |
| Publicités | Graphique en barres horizontales des impressions, des clics et des coûts. |
| Totaux des annonces publicitaires | Tableau à structure libre des principales publicités ventilé selon des mesures associées. |
| Mots-clés | Graphique de dispersion des impressions, des clics et des coûts pour toutes les combinaisons de mots-clés/types de correspondance. |
| Totaux des mots-clés | Tableau à structure libre des principales combinaisons de mots-clés/types de correspondance ventilé selon des mesures associées. |

## Report Builder {#section_8E0371CF81144C33990D909685D1726E}

As soon as you have set up an Advertising Analytics account, the Advertising Analytics report is made available.
