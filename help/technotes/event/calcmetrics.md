---
title: Dérivation de données affectées par les événements
description: Utilisez des mesures calculées pour corriger les données de tendance affectées par un événement.
translation-type: tm+mt
source-git-commit: 8e193de6dbb51cb640218a0c7b1b501d4f1eaa27
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 3%

---


# Dérivation de données affectées par les événements

Si des données sont [affectées par un événement](overview.md), vous pouvez utiliser des mesures calculées pour dériver des valeurs estimées pour la durée du événement. Par exemple, si un événement a provoqué une baisse de 25 % des données, vous pouvez l’utiliser comme multiplicateur dans une mesure calculée.

Ces étapes fonctionnent mieux lorsque vous comprenez l’impact d’un événement, à la fois du point de vue de la segmentation et de la comparaison de dates. Veillez à suivre la [comparaison des dates affectées par un événement aux plages](compare-dates.md) précédentes et [Exclure des dates spécifiques en analyse](segments.md) avant de suivre cette page.

>[!NOTE]
>
>Cette approche est une estimation basée sur un ensemble spécifique d&#39;entrées et de plages de dates. Il ne s&#39;agira pas d&#39;une solution globale pour tous les cas d&#39;utilisation ou tranches de données. En outre, cette approche exige que la plage de dates affectée comporte au moins 1 accès pour le calcul.

Pour créer une mesure calculée estimée pour la période affectée :

1. Créez deux segments pour &quot;Jours affectés&quot; et &quot;Exclure les jours affectés&quot;, comme indiqué dans la section [Exclure des dates spécifiques dans l’analyse](segments.md).
2. Accédez à **[!UICONTROL Composants]** > Mesures **** calculées.
3. Cliquez sur **[!UICONTROL Ajouter]**.
4. Faites glisser les deux segments ci-dessus vers le canevas de définition. Modifiez l’opérateur entre eux en un `+` pour les additionner.
5. ajoutez la mesure souhaitée dans les deux segments. Par exemple, vous pouvez utiliser la mesure Visites.

   ![Créateur de segments](assets/event_segment_builder.png)

6. Cliquez sur **[!UICONTROL Ajouter]** dans l’angle supérieur droit du conteneur &quot;Jours affectés&quot;, puis sur Nombre **** statique. Définissez le nombre statique sur le pourcentage de décalage des données, comme indiqué dans la section [Comparer les dates affectées par un événement aux plages](compare-dates.md)précédentes. Dans cet exemple, le décalage est de 25 %, soit 1,25.

   ![Nombre statique](assets/event_static_number.png)

7. Appliquez côte à côte la mesure &quot;corrigée&quot; dans un tableau à structure libre de tendance. Tous les jours en dehors du événement reflètent leur nombre de mesures normal, tandis que tous les jours affectés utilisent le décalage de multiplicateur.

   ![Mesure corrigée](assets/event_corrected.png)

8. Vue des données dans une visualisation en ligne pour voir l’effet de la mesure corrigée.

   ![Ligne corrigée](assets/event_line.png)
