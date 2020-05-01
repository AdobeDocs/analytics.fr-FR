---
title: Comparer les dates affectées par un événement aux plages précédentes
description: Découvrez l’impact d’un événement, tel qu’un problème d’implémentation ou une panne, en le comparant aux tendances précédentes.
translation-type: tm+mt
source-git-commit: 74a1edadde1899c9e51019cb7e7bb120b6e04d64

---


# Comparer les dates affectées par un événement aux plages précédentes

Si un événement [a des](overview.md)répercussions sur les données, vous pouvez examiner les tendances historiques pour en évaluer l’impact. Cette comparaison s’avère utile pour comprendre l’impact d’un événement sur vos données. Vous pouvez donc décider d’exclure les données, d’ajouter une note aux rapports ou de les ignorer.

## Créer une plage de dates incluant le événement

Créez une plage de dates qui englobe le événement pour commencer à étudier l&#39;impact de ce événement.

1. Accédez à **[!UICONTROL Components]** > **[!UICONTROL Date ranges]**.
2. Cliquez sur **[!UICONTROL Add]**.
3. Sélectionnez la période au cours de laquelle le événement a eu lieu. Cliquez sur **[!UICONTROL Save]**.

   ![Créateur de plages de dates](assets/date_range_builder.png)

## Dates de événement de Vue et plages antérieures similaires côte à côte

Vous pouvez comparer n’importe quelle mesure entre la plage de dates du événement et des plages de dates antérieures similaires à l’aide d’une visualisation de tableau à structure libre.

1. Ouvrez un projet Workspace et ajoutez la dimension &quot;Jour&quot; au tableau à structure libre. Appliquez la période récemment créée empilée sur une mesure, telle que &quot;Occurrences&quot;.

   ![Mesure de plage de dates](assets/date_range_metric.png)

2. Cliquez avec le bouton droit sur la plage de dates, puis cliquez sur **[!UICONTROL Add time period column]** > **[!UICONTROL Custom date range to this date range]**.
   * Pour une comparaison semaine après semaine, sélectionnez la plage du événement moins 7 jours. Assurez-vous que les jours de la semaine entre le événement et cette plage de dates sont alignés.
   * Pour une comparaison mensuelle, sélectionnez la plage du événement du mois dernier. Vous pouvez également sélectionner la plage du événement moins 28 jours si vous souhaitez aligner les jours de la semaine.
   * Pour une comparaison d’une année à l’autre, sélectionnez la plage du événement de l’année dernière.
3. Lorsque vous sélectionnez une plage de dates, elle est ajoutée à votre tableau à structure libre. Vous pouvez cliquer avec le bouton droit de la souris et ajouter autant de plages de dates que vous le souhaitez.

   ![Tendances alignées sur les dates](assets/date_aligned_trends.png)

## Calculer les différences de pourcentage entre le événement et des plages antérieures similaires

Comparez les valeurs de dimension entre une plage de dates de événement et des plages de dates antérieures similaires à l’aide d’une visualisation de tableau à structure libre. Ces étapes illustrent un exemple semaine après semaine que vous pouvez suivre.

1. Ouvrez un projet Workspace et ajoutez une dimension **** non temporelle au tableau à structure libre. Par exemple, vous pouvez utiliser la dimension &quot;Type de périphérique mobile&quot;. Appliquez la période récemment créée empilée sur une mesure, telle que &quot;Occurrences&quot; :

   ![Type de périphérique mobile par plage de dates affectée](assets/mobile_device_type.png)

2. Cliquez avec le bouton droit sur la plage de dates, puis cliquez sur **[!UICONTROL Compare time periods]** > **[!UICONTROL Custom date range to this date range]**. Sélectionnez la plage du événement moins 7 jours. Assurez-vous que les jours de la semaine entre le événement et cette plage de dates sont alignés.

   ![Menu Comparer la période](assets/compare_time_custom.png)

3. Renommez la mesure Changement de pourcentage résultante en une mesure plus spécifique, telle que &quot;Plage affectée par WoW&quot;. Cliquez sur l&#39;icône d&#39;informations, puis sur le crayon d&#39;édition pour modifier le nom de la mesure.

   ![Semaine après semaine](assets/wow_affected_range.png)

4. Répétez les étapes 3 et 4 pour les comparaisons d’un mois à l’autre et d’une année à l’autre. Vous pouvez effectuer cette action dans le même tableau ou dans des tableaux distincts.

## Analyser côte à côte les plages de dates de comparaison sous forme de lignes

Si vous souhaitez analyser plus en détail les modifications de pourcentage ci-dessus, vous pouvez les convertir en lignes.

1. Ajouter une visualisation de tableau à structure libre et activez le créateur de tableaux. Cette action vous permet de placer les mesures de changement de pourcentage dans l’ordre souhaité.
2. Maintenez la touche `Ctrl` (Windows) ou `Cmd` (Mac) enfoncée et faites glisser les mesures de modification de 3 % dans les lignes du tableau, une par une.

   ![Générateur de tableau](assets/table_builder.png)

3. Ajouter le segment &quot;Toutes les visites&quot; dans la colonne du tableau, ainsi que tout autre segment souhaité.

   ![Segments du créateur de tableaux](assets/table_builder_segments.png)

4. Cliquez sur **[!UICONTROL Build]**. Dans le tableau qui en résulte, vous pouvez vue les plages affectées par rapport à la semaine, au mois et à l’année précédents sur l’ensemble des segments de votre choix.

   ![Table terminée](assets/table_builder_finished.png)
