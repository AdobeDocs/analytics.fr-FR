---
description: Les suites de rapports virtuelles peuvent être traitées de manière à inclure et à exclure des composants d’Analysis Workspace.
seo-description: Les suites de rapports virtuelles peuvent être traitées de manière à inclure et à exclure des composants d’Analysis Workspace.
seo-title: Traitement des composants des suites de rapports virtuelles
title: Traitement des composants des suites de rapports virtuelles
uuid: 6 c 6 a 4071-22 ad -4 e 8 c-b 1 ed -140 b 2 aa 04 f 76
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Traitement des composants des suites de rapports virtuelles

Les suites de rapports virtuelles peuvent être traitées de manière à inclure et à exclure des composants d’Analysis Workspace.

>[!NOTE]
>
>Des modifications ont été apportées quant aux composants visibles aux administrateurs et aux non-administrateurs dans les suites de rapports virtuelles et les projets Workspace traités. Auparavant, les composants non traités étaient visibles par tous en cliquant sur le bouton **[!UICONTROL Afficher tous les composants]**. La [mise à jour de l’expérience de traitement](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/curate-projects-vrs.html) permet de mieux contrôler quels composants sont visibles.

Pour activer le traitement des composants,

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Virtual Report Suites]** &gt; **[!UICONTROL Create new virtual report suite]**.
1. Après avoir défini les **[!UICONTROL Paramètres]**, cliquez sur l’onglet **Composants[!UICONTROL .]**

1. Select the checkbox **[!UICONTROL Enable Customization of Virtual Report Suite Components]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >If component customization is enabled, the virtual report suite is accessible **only in Analysis Workspace** and is not accessible in the following:

   * [!UICONTROL Reports &amp; Analytics]
   * [!UICONTROL Ad Hoc Analysis]
   * [!UICONTROL Entrepôt de données]
   * [!UICONTROL Report Builder]
   * API de création de rapports dans Analytics
   Une fois la case activée, vous pouvez ajouter les composants que vous souhaitez inclure dans la suite de rapports virtuelle en les faisant glisser de la colonne « exclus » vers la colonne « inclus ». Les composants pouvant être inclus et exclus sont les suivants :

   * Dimensions
   * Mesures
   * Segments
   * Plages de dates
   >[!NOTE]
   >
   >There is no need to *share* curated components (segments, calculated metrics, date ranges). S’ils sont traités pour la suite de rapports virtuelle, ils seront visibles dans Analysis Workspace, même s’ils ne sont pas partagés.

1. En outre, vous pouvez filtrer ou rechercher les composants et ajouter la totalité de la sélection filtrée à la colonne « inclus » en cliquant sur **[!UICONTROL Tout ajouter]**.

   ![](assets/vrs-add-all.png)

## Changement du nom des composants {#section_0F7CD9F684FE4765BC00A2AFED56550E}

Vous pouvez modifier les noms d’affichage des composants inclus spécifiques à la suite de rapports virtuelle. Par exemple, si vous souhaitez inclure le nom de page dans la suite de rapports virtuelle, mais que vous souhaitez le renommer pour un contexte plus mobile, vous pouvez le modifier en « écrans d’application ». Le nouveau nom s’affiche dans Analysis Workspace chaque fois que cette suite de rapports virtuelle est utilisée.

![](assets/vrs-rename-component.png)

Dans Analysis Workspace, cliquez sur l’icône d’information pour tout composant inclus afin de révéler le nom d’origine du composant renommé :

![](assets/vrs-aw-renamed.png)

## Groupes de composants {#section_483BEC76F49E46ADAAA03F0A12E48426}

Utilisez les groupes de composants pour ajouter des composants en vrac à la suite de rapports virtuelle. Par exemple, si vous souhaitez importer un jeu de composants par défaut spécifique à l’analyse des applications mobiles, sélectionnez le groupe d’applications mobiles. Un jeu correspondant de dimensions et de mesures (déjà renommées) est automatiquement ajouté à la liste Inclus de la suite de rapports virtuelle.

![](assets/vrs-comp-grp.png)

## Comportement de l’espace de travail {#section_6C32F8B642804C0097FCB14E21028D4A}

Pour plus d’informations sur le traitement dans Analysis Workspace, voir [Traitement et partage d’un projet](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/curate.html).