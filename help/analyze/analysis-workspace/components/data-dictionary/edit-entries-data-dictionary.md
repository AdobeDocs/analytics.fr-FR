---
description: Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices de cataloguer et de suivre les différents composants dans Analysis Workspace, y compris leur utilisation prévue, ceux qui sont approuvés, ceux qui sont des doublons, etc.
title: Modifier des entrées dans le dictionnaire de données
feature: Components
role: Admin
source-git-commit: 04f7b3f4b543619cd4a8af418ce583e73ce65b9f
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 75%

---

# Modifier les entrées de composant dans le dictionnaire de données

Les administrateurs et administratrices d’Analytics peuvent modifier les entrées de composant dans le dictionnaire de données pour une suite de rapports donnée. Toutes les modifications apportées sont visibles par tous les utilisateurs et utilisatrices de la suite de rapports.

Pour modifier un composant dans le dictionnaire de données :

1. Accédez au projet Analysis Workspace qui contient le composant que vous souhaitez modifier.

1. Sélectionnez l’icône **Dictionnaire de données** dans le rail gauche d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans « Accéder au dictionnaire de données » dans la [présentation du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   La fenêtre Dictionnaire de données s’affiche.

   ![Vue d’administration du dictionnaire de données.](assets/data-dictionary-admin.png)

1. Assurez-vous que la bonne suite de rapports est sélectionnée dans le menu déroulant. Par défaut, la suite de rapports dans laquelle vous vous trouvez déjà s’affiche.

1. (Facultatif) Dans le champ de recherche, commencez à saisir le nom du composant à modifier.

   Le type de composant peut être identifié à la fois par couleur et par icône. **Dimensions** ![Icône Dimension](assets/dimension-icon.png) sont orange, **Segments** ![Icône Segment](assets/segment-icon.png) sont bleues, **Périodes** ![Icône Période](assets/date-range-icon.png) sont violets et **Mesures** ![Icône Mesure](assets/default-metric-icon.png) sont vertes. Icône Adobe ![Icône Adobe](assets/default-calc-metric-icon.png) indique soit un modèle de mesure calculée, soit un modèle de segment, et l’icône du calculateur ![Icône Calcul](assets/calculated-metric-icon-created.png) indique une mesure calculée qui a été créée par un administrateur Analytics de votre entreprise.

{{dd-filter-criteria}}

1. Dans la liste des composants, sélectionnez le composant à modifier.

1. Sélectionnez l’icône **Modifier** ![icône Modifier le dictionnaire de données](assets/data-dictionary-edit-icon.png) en regard du nom du composant.

1. Modifiez l’une des informations suivantes sur le composant :

   {{dd-component-information}}

1. Cliquez sur l’icône **Enregistrer** ![icône Enregistrer le dictionnaire de données](assets/data-dictionary-save-icon.png) pour enregistrer vos modifications.
