---
title: 'Exclure des dates spécifiques dans  '
description: Conseils pour exclure les dates ou les plages de dates si vous ne souhaitez pas les inclure dans les rapports.
translation-type: tm+mt
source-git-commit: e2ddfc7fb7ced2d7f480bec3b50cb2657d779646

---


# Exclure des dates spécifiques dans  

Si des données sont [affectées par une](/help/technotes/event-impacted.md), vous pouvez utiliser un segment pour exclure les plages de dates que vous ne souhaitez pas inclure dans vos rapports. La segmentation des dates affectées par les  peut empêcher votre entreprise de prendre des décisions sur des données partielles.

## Isoler les jours affectés

Créez un segment qui isole le jour ou la période affectés. Ce segment s’avère utile si vous souhaitez vous concentrer sur les jours problématiques pour afficher plus d’informations sur son impact.

1. Ouvrez le créateur de segments en sélectionnant **[!UICONTROL Components]** > **[!UICONTROL Segments]**, puis cliquez sur **[!UICONTROL Add]**.
2. Faites glisser la dimension &quot;Jour&quot; sur le canevas de définition et définissez-la sur le jour à isoler.
3. Répétez l’étape ci-dessus pour chaque jour que vous souhaitez isoler dans votre rapport.

![Segment Jours concernés](../assets/affected_days.jpg)

Adobe recommande d’utiliser les composants de dimension orange, et non les composants de plage de dates violets. Si vous utilisez des composants de plage de dates violets, ils remplacent la plage de calendrier du projet :

![Exclure le type de jour du segment](../assets/exclude_segment_day_type.jpg)

## Exclure les jours affectés

Créez un segment qui exclut le jour ou la période affectés. Ce segment est utile si vous souhaitez exclure les jours qui ont rencontré des problèmes afin de minimiser l’impact sur les  d’ensemble des.

1. Ouvrez le créateur de segments en sélectionnant **[!UICONTROL Components]** > **[!UICONTROL Segments]**, puis cliquez sur **[!UICONTROL Add]**.
2. Dans le coin supérieur droit du canevas de définition de segment, cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Exclude]**.
3. Faites glisser la dimension &quot;Jour&quot; sur le canevas de définition et définissez-la sur le jour à supprimer.
4. Répétez l’étape ci-dessus pour chaque jour que vous souhaitez supprimer dans votre rapport.

![Exclure les jours affectés](../assets/exclude_affected_days.jpg)

## Utilisation de ces segments dans les rapports

Une fois le segment d’exclusion créé, vous pouvez l’utiliser exactement comme vous le feriez pour d’autres segments.

### Comparaison de segments dans un rapport de tendances

Vous pouvez appliquer les segments &quot;Jours affectés&quot; et &quot;Exclure les jours affectés&quot; dans un rapport pour les comparer côte à côte. Faites glisser les deux segments au-dessus ou au-dessous d’une mesure pour les comparer :

![Les deux segments](../assets/affected_and_exclude.png)

### Appliquer le segment d’exclusion à un projet

Vous pouvez appliquer le segment &quot;Exclure les jours affectés&quot; à un projet Workspace. Faites glisser le segment d’exclusion vers la section Zone de travail intitulée *Déposer un segment ici*.

>[!TIP] Insérez une note sur les données exclues dans la description du panneau pour aider les personnes qui consultent le rapport. Cliquez avec le bouton droit sur le titre d’un panneau, puis cliquez sur **[!UICONTROL Edit description]**.

![Segment appliqué à un panneau](../assets/exclude_segment_panel.jpg)

### Utiliser le segment d’exclusion dans une suite de rapports virtuelle

Vous pouvez utiliser le segment dans une suite [de rapports](../../vrs/vrs-about.md) virtuelle pour exclure plus facilement les données. Cette option est idéale en ce sens que vous n’avez pas besoin de vous rappeler d’appliquer le segment pour chaque rapport qui inclut la plage de dates affectée. Si vous utilisez déjà des suites de rapports virtuelles comme source principale de données, vous pouvez ajouter le segment à une suite de rapports virtuelle existante.

1. Accédez à **[!UICONTROL Components]** > **[!UICONTROL Virtual report suites]**.
2. Cliquez sur **[!UICONTROL Add]**.
3. Entrez le nom et la description de la suite de rapports virtuelle.
4. Faites glisser le segment d’exclusion vers la zone étiquetée **[!UICONTROL Add segment]**.
5. Cliquez sur **[!UICONTROL Continue]** dans l’angle supérieur droit, puis sur **[!UICONTROL Save]**.

![Segment appliqué à VRS](../assets/exclude_segment_vrs.png)
