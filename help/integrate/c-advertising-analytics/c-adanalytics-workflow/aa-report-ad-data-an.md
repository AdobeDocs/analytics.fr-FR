---
description: Détails sur le modèle Analysis Workspace et le reporting dans Report Builder.
title: Rapport sur les données Advertising dans Adobe Analytics
feature: Advertising Analytics
exl-id: bbc830d9-e168-471d-a1ba-308277aab415
TQID: https://experienceleague.adobe.com/BOly6gaT1ybHWDppJzhi9ILClvJ9UoLzkGFua1gS1lo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 350
ht-degree: 47%

---

# Rapport sur les données publicitaires

Cet article fournit des détails sur le rapport Analysis Workspace et le reporting dans Report Builder.

>[!NOTE]
>
>Patientez au moins 24 heures avant que les données des moteurs de recherche ne commencent à remplir les rapports Analytics. La création de rapports Analytics ne renvoie pas de données avec une granularité horaire, car les données Adobe Advertising ne prennent pas en charge la granularité horaire.

## Rapport de référencement payant {#section_8173F42B2C784F41B9FD82CBB66F9ADF}

Ce rapport permet à toute personne implémentant l’intégration du moteur de recherche d’accéder aux données du moteur de recherche dans Analytics. Vous pouvez y accéder via **&#x200B;**&#x200B;> **[!UICONTROL Reports]** > **[!UICONTROL Acquisition]** > **[!UICONTROL Advertising Analytics : référencement payant]**

>[!NOTE]
>
>Le rapport de référencement payant est visible par tous les clients, même si vous n’avez implémenté aucun compte Advertising. Si vous essayez d’ouvrir le rapport de référencement payant pour une société qui n’est pas configurée, un message d’erreur vous expliquera que vous n’avez configuré aucun compte de moteur de recherche. Sélectionnez **[!UICONTROL Configurer maintenant]** pour accéder à l’écran [Configuration du compte Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).

![](assets/aa_aw.png)  ![](assets/aa_aw2.png) ![](assets/aa_aw3.png) ![](assets/aa_aw4.png)  ![](assets/aa_aw5.png) ![](assets/aa_aw6.png)

| Tableau/Visualisation | Description |
|--- |--- |
| Tendances publicitaires | Présentation des tendances quotidiennes pour les Impressions AMO, les Clics AMO et le Coût AMO. |
| Plateformes d’annonces publicitaires | Graphique en anneau pour le coût des 2 principales plateformes (Google Ads, Microsoft Advertising). |
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

Dès que vous avez configuré un compte Advertising Analytics, le rapport Advertising Analytics est disponible.
