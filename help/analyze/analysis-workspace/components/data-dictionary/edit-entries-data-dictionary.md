---
description: Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices de cataloguer et de suivre les différents composants dans Analysis Workspace, y compris leur utilisation prévue, ceux qui sont approuvés, ceux qui sont des doublons, etc.
title: Modifier des entrées dans le dictionnaire de données
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: a6805f0944570bee265d5db9a159ae24e0694837
workflow-type: ht
source-wordcount: '375'
ht-degree: 100%

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

   Le type de composant peut être identifié à la fois par couleur et par icône. **Les dimensions** ![icône Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sont orange, **les segments** ![icône Segment](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sont bleus, **les périodes** ![icône Période](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sont violettes et **les mesures** ![icône Mesure](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sont vertes. L’icône Adobe indique soit un modèle de mesure calculée, soit un modèle de segment. L’icône du calculateur ![icône Calculateur](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indique une mesure calculée qui a été créée par un administrateur ou une administratrice Analytics de votre entreprise.

{{dd-filter-criteria}}

1. (Facultatif) Sélectionnez l’icône **Trier** ![icône Trier les composants](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), puis sélectionnez l’une des options de filtre suivantes pour trier la liste des composants :

   {{components-sort-options}}

1. Dans la liste des composants, sélectionnez le composant à modifier.

1. Sélectionnez l’icône **Modifier** ![icône Modifier le dictionnaire de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) en regard du nom du composant.

1. Modifiez l’une des informations suivantes sur le composant :

   {{dd-component-information}}

1. Cliquez sur l’icône **Enregistrer** ![icône Enregistrer le dictionnaire de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) pour enregistrer vos modifications.
