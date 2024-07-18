---
description: Détails sur le modèle Analysis Workspace et sur la création de rapports dans Report Builder.
title: Rapport sur les données Advertising dans Adobe Analytics
feature: Advertising Analytics
exl-id: bbc830d9-e168-471d-a1ba-308277aab415
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 49%

---

# Rapport sur les données publicitaires

Cet article fournit des détails sur le rapport Analysis Workspace et le rapport en Report Builder.

>[!NOTE]
>
>Patientez 24 heures au moins avant que les données du moteur de recherche ne commencent à apparaître dans vos rapports Analytics. Notez également que la création de rapports Analytics ne renvoie pas de données pour la granularité horaire, car les données Advertising Cloud ne prennent pas en charge la granularité horaire.

## Rapport de recherche payante {#section_8173F42B2C784F41B9FD82CBB66F9ADF}

Ce rapport permet à toute personne qui met en oeuvre l’intégration de moteur de recherche d’accéder aux données de moteur de recherche dans Analytics. Vous pouvez y accéder via **[!UICONTROL Workspace]** > **[!UICONTROL Rapports]** > **[!UICONTROL Acquisition]** > **[!UICONTROL Advertising Analytics : recherche payante]**

>[!NOTE]
>
>Le rapport de recherche payante est visible par tous les clients, même si vous n’avez implémenté aucun compte Advertising. Si vous essayez d’ouvrir le rapport de recherche payante pour une société qui n’est pas configurée, un message d’erreur vous explique que vous n’avez configuré aucun compte de moteur de recherche. Sélectionnez **[!UICONTROL Configurer maintenant]** pour accéder à l’écran [Configuration d’un compte Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).

![](assets/aa_aw.png)  ![](assets/aa_aw2.png) ![](assets/aa_aw3.png) ![](assets/aa_aw4.png)  ![](assets/aa_aw5.png) ![](assets/aa_aw6.png)

| Tableau/Visualisation | Description |
|--- |--- |
| Tendances publicitaires | Présentation des tendances quotidiennes pour les Impressions AMO, les Clics AMO et le Coût AMO. |
| Plateformes d’annonces publicitaires | Graphique en anneau pour les coûts des deux plateformes principales (Google, Bing). |
| Totaux des plateformes d’annonces publicitaires | Tableau à structure libre des plateformes principales ventilé selon les Impressions AMO, les Clics AMO, le Coût AMO, la position moyenne AMO et la note note de qualité moyenne. |
| Comptes | Zone empilée de coûts. |
| Totaux de comptes | Tableau à structure libre des comptes principaux ventilé selon des mesures associées. |
| Campagnes | Graphique à barres du coût de la campagne. |
| Totaux de la campagne | Tableau à structure libre des campagnes principales ventilé selon des mesures associées. |
| Groupes | Arborescence des coûts. |
| Totaux des groupes | Tableau à structure libre des principaux groupes publicitaires ventilé selon des mesures associées. |
| Publicités | Graphique à barres horizontales des impressions, des clics et des coûts. |
| Totaux des annonces publicitaires | Tableau à structure libre des principales publicités ventilé selon des mesures associées. |
| Mots-clés | Graphique de dispersion des impressions, des clics et des coûts pour toutes les combinaisons de mots-clés/types de correspondance. |
| Totaux des mots-clés | Tableau à structure libre des principales combinaisons de mots-clés/types de correspondance ventilé selon des mesures associées. |

## Report Builder {#section_8E0371CF81144C33990D909685D1726E}

Dès que vous avez configuré un compte Advertising Analytics, le rapport Advertising Analytics est rendu disponible.
