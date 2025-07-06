---
description: Découvrez comment créer une mesure calculée simple.
title: Création D’Une Mesure Calculée Simple
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 17%

---

# Créer une mesure calculée simple

Les informations suivantes expliquent comment créer une mesure *Pages vues par visite* simple.

1. Commencez à créer une mesure, comme décrit dans la section [Créer des mesures](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).
1. Nommez la mesure `Page Views per Visit` ou une autre mesure similaire.
1. Donnez à la mesure une **[!UICONTROL Description]** conviviale pour montrer à quoi sert la mesure.
1. Sélectionnez le **[!UICONTROL Format]** approprié. Pour cet exemple, choisissez **[!UICONTROL Décimal]**.
1. Déterminez combien de décimales vous souhaitez que le rapport affiche.
1. Dans le menu déroulant **[!UICONTROL Afficher la tendance à la hausse sous forme de]**, sélectionnez ▲ **[!UICONTROL Bon (Vert)]**.
1. Ajoutez une **[!UICONTROL Balise]** pour organiser vos mesures.
1. Pour cette mesure calculée, faites d’abord glisser **[!UICONTROL Pages vues]** des composants **[!UICONTROL Mesures]** vers la section **[!UICONTROL Définition]** de la zone de travail.
1. Faites ensuite glisser **[!UICONTROL Visites]** à partir des composants **[!UICONTROL Mesures]** et déposez la mesure sous **[!UICONTROL Pages vues]** (attendez que la ligne bleue apparaisse avant de déposer la mesure).
1. Sélectionnez l’opérateur divide ![Divide](/help/assets/icons/Divide.svg). (Il s’agit de l’opérateur par défaut.)
1. Vous pouvez afficher un **[!UICONTROL Aperçu]** de la mesure pendant que vous la créez.
1. [Compatibilité des produits](../../../cm-compatibility.md) indique si la mesure est compatible avec les données actives ou uniquement avec les données entièrement traitées.

   ![ Mesure calculée simple ](assets/simple-calculated-metric.png)
1. Sélectionnez **[!UICONTROL Enregistrer]**.

   Notez que la formule **[!UICONTROL Résumé]** se met à jour chaque fois que vous apportez une modification à la définition de mesure.

1. (Facultatif) Pour partager, approuver, (re)baliser, renommer ou supprimer une mesure, vous pouvez accéder au [Gestionnaire de mesures calculées](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md).

