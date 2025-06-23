---
title: Exclusion de dates spécifiques dans l’analyse
description: Conseils pour exclure des dates ou des périodes si vous ne souhaitez pas les inclure dans les rapports.
exl-id: 744666c0-17f3-443b-9760-9c8568bec600
feature: Curate and Share, Segmentation
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 2%

---

# Exclusion de dates spécifiques dans l’analyse

Si des données [affectées par un événement](overview.md) sont présentes, vous pouvez utiliser un segment pour exclure les périodes que vous ne souhaitez pas inclure dans vos rapports. La segmentation des dates affectées par l’événement peut empêcher votre organisation de prendre des décisions sur des données partielles.

## Isoler les jours affectés {#isolate}

Créez un segment qui isole le jour ou la période concernés. Ce segment est utile si vous souhaitez vous concentrer uniquement sur les jours problématiques pour obtenir plus d’informations sur leur impact.

1. Ouvrez le créateur de segments en accédant à **[!UICONTROL Composants]** > **[!UICONTROL Segments]**, puis cliquez sur **[!UICONTROL Ajouter]**.
2. Faites glisser la dimension « Jour » vers le canevas de définition et définissez-la sur le jour à isoler.
3. Répétez l’étape ci-dessus pour chaque jour que vous souhaitez isoler dans votre rapport.

![Segment des jours affectés](assets/affected_days.jpg)

>[!TIP]
>
>Pour remplacer l&#39;instruction OR par une instruction AND, cliquez sur la flèche vers le bas en regard de OR et sélectionnez AND.

Adobe recommande d’utiliser les composants de dimension orange, et non les composants de période violets. Si vous utilisez des composants de période violets, ils remplacent la période du projet :

![Exclure le type de jour du segment](assets/exclude_segment_day_type.jpg)

## Exclure les jours affectés {#exclude}

Créez un segment qui exclut le jour ou la période concernés. Ce segment est utile si vous souhaitez exclure les jours ayant rencontré des problèmes afin de minimiser l’impact sur le reporting global.

1. Ouvrez le créateur de segments en accédant à **[!UICONTROL Composants]** > **[!UICONTROL Segments]**, puis cliquez sur **[!UICONTROL Ajouter]**.
2. Dans le coin supérieur droit de la zone de travail de définition de segment, cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Exclure]**.
3. Faites glisser la dimension « Jour » vers le canevas de définition et définissez-la sur le jour à supprimer.
4. Répétez l’étape ci-dessus pour chaque jour que vous souhaitez supprimer de votre rapport.

![Exclure les jours concernés](assets/exclude_affected_days.jpg)

## Utilisation de ces segments dans les rapports

Une fois le segment à exclure créé, vous pouvez l’utiliser exactement comme vous le feriez avec d’autres segments.

### Comparaison de segments dans un rapport de tendance {#compare}

Vous pouvez appliquer les segments « Jours affectés » et « Exclure les jours affectés » d’un rapport pour les comparer. Faites glisser les deux segments au-dessus ou au-dessous d’une mesure pour les comparer :

![Les deux segments](assets/affected_and_exclude.png)

Si vous ne souhaitez pas afficher de zéros dans votre tableau ou vos visualisations (ce qui entraîne des creux), activez **[!UICONTROL Interpréter zéro comme n’étant pas une valeur]** sous les paramètres de colonne.

![Interpréter zéro](assets/interpret_zero.png)

Si vous ne souhaitez pas afficher de zéros dans votre tableau ou vos visualisations (ce qui entraîne des creux), activez **[!UICONTROL Interpréter zéro comme n’étant pas une valeur]** sous les paramètres de colonne.

![Interpréter zéro](assets/interpret_zero.png)

### Appliquer le segment d’exclusion à un projet {#apply}

Vous pouvez appliquer le segment « Exclure les jours affectés » à un projet Workspace. Faites glisser le segment d’exclusion vers la section Zone de travail de Workspace intitulée *Déposez un segment ici*.

>[!TIP]
>
>Insérez une note sur les données exclues dans la description du panneau pour aider les personnes qui consultent le rapport. Cliquez avec le bouton droit sur le titre d’un panneau, puis cliquez sur **[!UICONTROL Modifier la description]**.

![Segment appliqué à un panneau](assets/exclude_segment_panel.jpg)

### Utiliser le segment d’exclusion dans une suite de rapports virtuelle {#use-vrs}

Vous pouvez utiliser le segment dans une [suite de rapports virtuelle](/help/components/vrs/vrs-about.md) pour exclure plus facilement les données. Cette option est idéale dans la mesure où vous n’avez pas à penser à appliquer le segment pour chaque rapport qui inclut la période concernée. Si vous utilisez déjà des suites de rapports virtuelles comme source principale de données, vous pouvez ajouter le segment à une suite de rapports virtuelle existante.

1. Accédez à **[!UICONTROL Composants]** > **[!UICONTROL Suites de rapports virtuelles]**.
2. Cliquez sur **[!UICONTROL Ajouter]**.
3. Saisissez le nom et la description de la suite de rapports virtuelle.
4. Faites glisser le segment d’exclusion vers la zone intitulée **[!UICONTROL Ajouter un segment]**.
5. Cliquez sur **[!UICONTROL Continuer]** en haut à droite, puis sur **[!UICONTROL Enregistrer]**.

![Segment appliqué à une suite de rapports virtuelle](assets/exclude_segment_vrs.png)
