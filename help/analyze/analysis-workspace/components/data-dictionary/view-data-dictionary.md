---
description: Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices de cataloguer et de suivre les différents composants dans Analysis Workspace, y compris leur utilisation prévue, ceux qui sont approuvés, ceux qui sont des doublons, etc.
title: Afficher le dictionnaire de données
feature: Components
role: User, Admin
source-git-commit: 5d83d2621ee5eee7dbbc2af3793a9e1d3de0f97b
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 58%

---

# Afficher des informations sur les composants dans le dictionnaire de données

{{release-limited-testing}}

Le dictionnaire de données vous permet d’afficher des informations sur un composant, notamment sa description, des composants similaires, les autres composants fréquemment utilisés avec lui, etc.

Pour afficher des informations sur un composant dans le dictionnaire de données :

1. Accédez au projet Analysis Workspace qui contient le composant que vous souhaitez afficher.

1. Sélectionnez l’icône [!UICONTROL **Dictionnaire de données**] dans le rail gauche d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans « Accéder au dictionnaire de données » dans la [présentation du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   La fenêtre Dictionnaire de données s’affiche.

   ![data-dictionary.png.](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Assurez-vous que la suite de rapports contenant le composant que vous souhaitez afficher est sélectionnée dans le menu déroulant. Par défaut, la suite de rapports dans laquelle vous vous trouvez déjà s’affiche.

1. (Facultatif) Dans le champ de recherche, commencez à saisir le nom du composant à afficher.

   Les icônes s’affichent en regard des noms de composant pour indiquer le type de composant :

   | Icône | Signification |
   |---------|----------|
   | ![Icône Dimension](assets/dimension-icon.png) | Indique un **dimension**. Les Dimensions sont fournies par Adobe. Les dimensions existantes ne peuvent pas être modifiées et les nouvelles dimensions ne peuvent pas être créées. |
   | ![Icône Mesure](assets/default-metric-icon.png) | Indique un **mesure standard** (non calculé). Les mesures standard sont fournies par Adobe et ne peuvent pas être modifiées. |
   | ![Icône Adobe](assets/default-calc-metric-icon.png) | Indique un **modèle de mesure calculée** ou **modèle de segment**. Ces composants sont fournis par Adobe et ne peuvent pas être modifiés. |
   | ![Icône Calcul](assets/calculated-metric-icon-created.png) | Indique un **mesure calculée** qui a été créé par un administrateur Analytics de votre entreprise. |
   | ![Icône Segment](assets/segment-icon.png) | Indique un **segment**. Il peut s’agir de segments fournis par Adobe ou créés par un administrateur Analytics de votre entreprise. |
   | ![Icône Période](assets/date-range-icon.png) | Indique un **période**. Il peut s’agir de périodes fournies par Adobe ou créées par un administrateur Analytics de votre entreprise. |

{{dd-filter-criteria}}

1. Dans la liste des composants, sélectionnez le composant à afficher.

   Les informations suivantes sur le composant s’affichent :

   {{dd-component-information}}

1. (Facultatif) Faites glisser un composant du dictionnaire de données vers Analysis Workspace.