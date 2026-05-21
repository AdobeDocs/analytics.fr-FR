---
description: Les suites de rapports virtuelles peuvent être traitées de manière à inclure et à exclure des composants d’Analysis Workspace.
title: Traitement des composants des suites de rapports virtuelles
feature: VRS
exl-id: 19163829-328a-4064-b1be-8c09d1d94a0d
TQID: https://experienceleague.adobe.com/j86dD5Yzd6GIoQOzhHsU8YbShQiODtbU8aCdM3UxRMg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 434
ht-degree: 89%

---

# Traitement des composants des suites de rapports virtuelles

Les suites de rapports virtuelles peuvent être traitées de manière à inclure et à exclure des composants d’Analysis Workspace.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Traitement des composants](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/components/virtual-report-suites/component-curation-in-virtual-report-suites){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Des modifications ont été apportées quant aux composants visibles aux personnes administratrices et non administratrices dans les suites de rapports virtuelles et les projets Workspace traités. Auparavant, les composants non traités étaient visibles par tous en cliquant sur le bouton **[!UICONTROL Afficher tous les composants]**. La [mise à jour de l’expérience de traitement](/help/analyze/analysis-workspace/curate-share/curate.md) permet de mieux contrôler quels composants sont visibles.

Pour activer le traitement des composants,

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Suites de rapports virtuelles]** > **[!UICONTROL Créer une suite de rapports virtuelle]**.
1. Après avoir défini les **[!UICONTROL Paramètres]**, cliquez sur l’onglet **[!UICONTROL Composants]**.

1. Cochez la case **[!UICONTROL Activer la personnalisation des composants de la suite de rapports virtuelle]** :

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >Si la personnalisation des composants est activée, la suite de rapports virtuelle est **accessible uniquement dans Analysis Workspace** et ne l’est pas dans :
   >
   >* [!UICONTROL Data Warehouse]
   >* [!UICONTROL Report Builder]
   >* [!UICONTROL Activity Map]
   >* API de création de rapports dans Analytics

   Une fois la case activée, vous pouvez ajouter les composants que vous souhaitez inclure dans la suite de rapports virtuelle en les faisant glisser de la colonne « exclus » vers la colonne « inclus ». Les composants pouvant être inclus et exclus sont les suivants :

   * Dimensions
   * Mesures
   * Segments
   * Périodes

   >[!NOTE]
   >
   >Il n’est plus nécessaire de *partager* les composants traités (segments, mesures calculées, périodes). S’ils sont traités pour la suite de rapports virtuelle, ils seront visibles dans Analysis Workspace, même s’ils ne sont pas partagés.

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

## Comportement de Workspace {#section_6C32F8B642804C0097FCB14E21028D4A}

Pour plus d’informations sur le traitement dans Analysis Workspace, voir [Traitement et partage d’un projet](/help/analyze/analysis-workspace/curate-share/curate.md).
