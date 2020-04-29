---
description: Les suites de rapports virtuelles peuvent être traitées de manière à inclure et à exclure des composants d’Analysis Workspace.
title: Traitement des composants des suites de rapports virtuelles
uuid: 6c6a4071-22ad-4e8c-b1ed-140b2aa04f76
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Traitement des composants des suites de rapports virtuelles

Les suites de rapports virtuelles peuvent être traitées de manière à inclure et à exclure des composants d’Analysis Workspace.

>[!NOTE]Des modifications ont été apportées quant aux composants visibles aux administrateurs et aux non-administrateurs dans les suites de rapports virtuelles et les projets Workspace traités. Auparavant, tout le monde pouvait voir les composants non traités en cliquant sur **[!UICONTROL Show all Components]**. La [mise à jour de l’expérience de traitement](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) permet de mieux contrôler quels composants sont visibles.

Pour activer le traitement des composants,

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]** > **[!UICONTROL Create new virtual report suite]**.
1. Après avoir défini le **[!UICONTROL Settings]**, cliquez sur l’ **[!UICONTROL Components]** onglet.

1. Cochez la case **[!UICONTROL Enable Customization of Virtual Report Suite Components]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >Si la personnalisation des composants est activée, la suite de rapports virtuelle est **accessible uniquement dans Analysis Workspace** et ne l’est pas dans :

   * [!UICONTROL Reports & Analytics]
   * [!UICONTROL Ad Hoc Analysis]
   * [!UICONTROL Data Warehouse]
   * [!UICONTROL Report Builder]
   * API de création de rapports dans Analytics
   Une fois la case activée, vous pouvez ajouter les composants que vous souhaitez inclure dans la suite de rapports virtuelle en les faisant glisser de la colonne « exclus » vers la colonne « inclus ». Les composants pouvant être inclus et exclus sont les suivants :

   * Dimensions
   * Mesures
   * Segments
   * Périodes
   >[!NOTE]
   >
   >Il n’est plus nécessaire de *partager* les composants traités (segments, mesures calculées, plages de dates). S’ils sont traités pour la suite de rapports virtuelle, ils seront visibles dans Analysis Workspace, même s’ils ne sont pas partagés.

1. Additionally, you can filter or search the components and add the entire filtered selection to the included column by clicking **[!UICONTROL Add All]**.

   ![](assets/vrs-add-all.png)

## Changement du nom des composants {#section_0F7CD9F684FE4765BC00A2AFED56550E}

Vous pouvez modifier les noms d’affichage des composants inclus spécifiques à la suite de rapports virtuelle. Par exemple, si vous souhaitez inclure le nom de page dans la suite de rapports virtuelle, mais que vous souhaitez le renommer pour un contexte plus mobile, vous pouvez le modifier en « écrans d’application ». Le nouveau nom s’affiche dans Analysis Workspace chaque fois que cette suite de rapports virtuelle est utilisée.

![](assets/vrs-rename-component.png)

Dans Analysis Workspace, cliquez sur l’icône d’information pour tout composant inclus afin de révéler le nom d’origine du composant renommé :

![](assets/vrs-aw-renamed.png)

## Groupes de composants  {#section_483BEC76F49E46ADAAA03F0A12E48426}

Utilisez les groupes de composants pour ajouter des composants en vrac à la suite de rapports virtuelle. Par exemple, si vous souhaitez importer un jeu de composants par défaut spécifique à l’analyse des applications mobiles, sélectionnez le groupe d’applications mobiles. Un jeu correspondant de dimensions et de mesures (déjà renommées) est automatiquement ajouté à la liste Inclus de la suite de rapports virtuelle.

![](assets/vrs-comp-grp.png)

## Comportement de Workspace {#section_6C32F8B642804C0097FCB14E21028D4A}

Pour plus d’informations sur le traitement dans Analysis Workspace, voir [Traitement et partage d’un projet](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/curate.translate.html).
