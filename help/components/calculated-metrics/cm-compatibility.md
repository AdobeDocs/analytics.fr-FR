---
description: Explique les trois options de compatibilité des produits.
title: Compatibilité des mesures
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
TQID: https://experienceleague.adobe.com/nbLLWHYtTLKmGnUxyU2Gp9spVCtE-AZgH2MiXE4nOVY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 68%

---

# Compatibilité des mesures {#metrics-compatibility}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Compatibilité des produits"
>abstract="Un petit nombre de critères de mesure disponibles ne sont pas compatibles avec tous les outils Adobe Analytics. Les outils compatibles avec la mesure sont indiqués dans cette liste. Pour rendre une mesure compatible avec tous les outils Adobe Analytics, essayez de modifier vos critères."

Cet article explique les trois options de compatibilité du produit.

Lorsque vous créez des mesures calculées dans le créateur de mesures calculées, vos mesures s’affichent comme compatibles avec un ou plusieurs outils dans Adobe Analytics.


| Compatible avec | Description |
| --- | --- |
| **[!UICONTROL Données actives]** | Grâce à l’option [!UICONTROL Inclure les données actives] d’Adobe Analytics, vous pouvez afficher les données d’analyse les plus récentes, souvent avant même qu’elles ne soient entièrement traitées et finalisées. Les [!UICONTROL données actives] présentent la plupart des mesures en quelques minutes, ce qui vous permet de disposer d’informations exploitables pour une prise de décisions rapide. [!UICONTROL Données actives] prend uniquement en charge les mesures calculées (celles incluant la multiplication, la division, l’addition et la soustraction). [!UICONTROL Données actives] ne prend pas en charge les mesures calculées avancées (contenant des segments ou des fonctions). |
| **[!UICONTROL Données entièrement traitées]** | Données qui sont entièrement traitées et incluent des segments et des classifications. Si vous préférez visualiser toutes les mesures après le traitement complet des données, désactivez les [!UICONTROL données actives] en supprimant des utilisateurs du groupe Utilisateurs actuels des données. |
| **[!UICONTROL Rapports sur les canaux marketing]** | Les mesures avec une allocation de première touche sont compatibles uniquement avec les rapports Canal marketing. |
