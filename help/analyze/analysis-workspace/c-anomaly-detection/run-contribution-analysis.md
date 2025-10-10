---
description: Découvrez comment exécuter un rapport d’analyse des contributions dans Analysis Workspace.
title: Exécution de l’analyse des contributions
role: User, Admin
exl-id: 20d1ba8d-3e4e-4702-ae28-5eb6bf00847b
feature: Anomaly Detection
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 14%

---

# Exécution de l’analyse des contributions

[L’analyse des contributions](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) est un processus intensif de machine learning, conçu pour déterminer quels facteurs sont à l’origine d’une anomalie observée dans Adobe Analytics. Elle permet à l’utilisateur ou à l’utilisatrice de repérer, bien plus rapidement qu’il ne serait normalement possible, les opportunités ou les centres d’intérêt justifiant une analyse supplémentaire.

>[!NOTE]
>
>L’analyse des contributions n’est prise en charge que pour les données avec une granularité quotidienne.

Pour exécuter l’analyse des contributions, procédez comme suit :

1. Appelez l’analyse des contributions dans un projet.

   ![Exécuter l’analyse des contributions](assets/run-contribution-analysis.png)

   1. Dans une visualisation Ligne, basée sur un tableau à structure libre avec une granularité quotidienne, sélectionnez un point de données d’anomalie. Dans la fenêtre contextuelle, sélectionnez **[!UICONTROL Analyser]**.
   1. Dans un tableau à structure libre avec une granularité quotidienne, dans le menu contextuel sur n’importe quelle ligne, sélectionnez **[!UICONTROL Exécuter l’analyse des contributions]**. Vous pouvez même exécuter l’analyse sur des lignes qui n’affichent aucune anomalie.
   1. Dans un tableau à structure libre avec une granularité quotidienne, sur une ligne qui indique une anomalie :
      1. Sélectionnez la ◥ de l’indicateur.
      1. Dans la boîte de dialogue ![Alerte](/help/assets/icons/Alert.svg) **[!UICONTROL Anomalie détectée]**, sélectionnez **[!UICONTROL Ouvrir l’analyse des contributions]**.



1. (Facultatif) Vous pouvez réduire la portée de l’analyse (et donc l’accélérer) en [excluant des dimensions](#exclude-dimensions).

   ![Exclusion de dimensions de l’analyse des contributions](assets/excluding-dimensions.png)

1. Sélectionnez **[!UICONTROL Exécuter l’analyse des contributions]**.

1. Patientez pendant le traitement de l’analyse des contributions. Le traitement peut prendre un temps considérable, selon la taille de votre suite de rapports et le nombre de dimensions. L’analyse des contributions effectue une analyse sur les 50 000 premiers éléments par dimension. Vous êtes également averti du nombre de [&#x200B; jetons d’analyse de contribution](anomaly-detection.md#contribution-analysis-tokens) restants.

   ![Analyse des contributions en cours d’exécution](assets/contribution-analysis-executing.png)

1. Analysis Workspace charge un nouveau panneau **[!UICONTROL Analyse des contributions]** directement dans ce projet.

   ![Panneau Analyse des contributions &#x200B;](assets/contribution-analysis.png)

   * Une visualisation [synthèse des chiffres](/help/analyze/analysis-workspace/visualizations/summary-number-change.md).
   * Une visualisation [ligne](/help/analyze/analysis-workspace/visualizations/line.md) des tendances mensuelles.
   * Un **[!UICONTROL Principaux éléments]** [tableau à structure libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) qui affiche les principaux éléments contribuant à cette anomalie, triés par [Score de contribution](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis). Les colonnes supplémentaires affichent la mesure en question, ainsi qu’une mesure **[!UICONTROL Visiteurs uniques]** afin de fournir un contexte.

   * Le **[!UICONTROL tableau Segments générés (clusters d’éléments principaux)]** [à structure libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) identifie les associations d’éléments principaux en fonction du score de contribution, des occurrences d’anomalie et du pourcentage global contribuant à la mesure d’anomalie. Cette association est ensuite capturée en tant que segment d’audience (segment de contribution 1, segment de contribution 2, etc.). Sélectionnez ![Infos](/help/assets/icons/Info.svg) pour afficher la définition du segment, y compris les éléments principaux dont le segment est constitué :


1. Comme l’analyse des contributions fait désormais partie d’Analysis Workspace, vous pouvez tirer parti de plusieurs de ses fonctionnalités à partir d’un menu contextuel de tableau à structure libre pour rendre votre analyse encore plus significative, par exemple :

   * [Ventilez chaque élément de dimension par une autre dimension](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [Mise en tendance d’une ou plusieurs lignes](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Ajouter de nouvelles visualisations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [Créer des alertes](/help/components/alerts/alerts-overview.md)
   * [Créer ou comparer des segments](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]
>
>L’anomalie analysée est mise en évidence par un point bleu dans l’analyse des contributions et les projets d’alerte intelligente qui lui sont associés. Cette mise en surbrillance fournit une indication plus claire de l’anomalie en cours d’analyse.


## Exclure les dimensions

Vous pouvez exclure certaines dimensions de l’analyse des contributions. Par exemple, vous pouvez ne pas attacher d’importance à des dimensions liées au navigateur ou au matériel et vous souhaitez accélérer l’analyse en les supprimant.

Pour gérer la dimension exclue :

* Faites glisser les dimensions indésirables dans le panneau **[!UICONTROL Dimensions exclues]**, puis enregistrez la liste en cliquant sur **[!UICONTROL Définir par défaut]**.

* Sélectionnez **[!UICONTROL Effacer tout]** pour recommencer.

* Sélectionnez ![Dimensions](/help/assets/icons/Dimensions.svg) pour afficher un menu contextuel et utilisez ![CrossSize400](/help/assets/icons/CrossSize400.svg) pour supprimer de la liste toute dimension exclue sélectionnée.

  ![](assets/excluded-dimensions-list.png)

Après avoir modifié les dimensions à exclure, sélectionnez **[!UICONTROL Exécuter l’analyse des contributions]** à nouveau.

