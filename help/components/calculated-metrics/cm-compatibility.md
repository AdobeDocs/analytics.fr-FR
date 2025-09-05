---
description: Explique les trois options de compatibilité des produits.
title: Compatibilité des mesures
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '208'
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
| **[!UICONTROL Données actives]** | Grâce à l’option [!UICONTROL Inclure les données actives] d’Adobe Analytics, vous pouvez afficher les données d’analyse les plus récentes, souvent avant même qu’elles ne soient entièrement traitées et finalisées. Les [!UICONTROL données actives] présentent la plupart des mesures en quelques minutes, ce qui vous permet de disposer d’informations exploitables pour une prise de décisions rapide. [!UICONTROL Données actives] ne prend en charge que les mesures calculées (celles incluant la multiplication, la division, l’addition et la soustraction). [!UICONTROL Données actives] ne prend pas en charge les mesures calculées avancées (celles contenant des segments ou des fonctions). |
| **[!UICONTROL Données entièrement traitées]** | Données qui sont entièrement traitées et incluent des segments et des classifications. Si vous préférez visualiser toutes les mesures après le traitement complet des données, désactivez les [!UICONTROL données actives] en supprimant des utilisateurs du groupe Utilisateurs actuels des données. |
| **[!UICONTROL Rapports sur les canaux marketing]** | Les mesures avec une allocation de première touche sont compatibles uniquement avec les rapports Canal marketing. |
