---
description: Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices de cataloguer et de suivre les différents composants dans Analysis Workspace, y compris leur utilisation prévue, ceux qui sont approuvés, ceux qui sont des doublons, etc.
title: Afficher le dictionnaire de données
feature: Components
role: User, Admin
exl-id: 68f68ea4-f0a6-4937-bf8f-aecfa28572bb
source-git-commit: 74ef4e73b6ed1e2a4ad498e2314af704acb6d8cb
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 98%

---

# Afficher des informations sur les composants dans le dictionnaire de données

Le dictionnaire de données vous permet d’afficher des informations sur un composant, notamment sa description, des composants similaires, les autres composants fréquemment utilisés avec lui, etc.

Pour afficher des informations sur un composant dans le dictionnaire de données :

1. Accédez au projet Analysis Workspace qui contient le composant que vous souhaitez afficher.

1. Sélectionnez l’icône [!UICONTROL **Dictionnaire de données**] dans le rail gauche d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans la section [Accéder au dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md#access-the-data-dictionary).)

   La fenêtre Dictionnaire de données s’affiche.

   ![data-dictionary.png.](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Assurez-vous que la suite de rapports contenant le composant que vous souhaitez afficher est sélectionnée dans le menu déroulant. Par défaut, la suite de rapports dans laquelle vous vous trouvez déjà s’affiche.

1. (Facultatif) Dans le champ de recherche, commencez à saisir le nom du composant à afficher.

   Le type de composant peut être identifié à la fois par couleur et par icône. **Les dimensions** ![icône Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sont orange, **les segments** ![icône Segment](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sont bleus, **les périodes** ![icône Période](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sont violettes et **les mesures** ![icône Mesure](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sont vertes. L’icône Adobe indique soit un modèle de mesure calculée, soit un modèle de segment. L’icône du calculateur ![icône Calculateur](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indique une mesure calculée qui a été créée par un administrateur ou une administratrice Analytics de votre entreprise.

1. (Facultatif) Sélectionnez l’icône **Filtrer** ![icône du filtre du dictionnaire de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), puis sélectionnez l’une des options de filtre suivantes pour filtrer la liste des composants :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Approuvés**] | Afficher uniquement les composants marqués comme approuvés par l’administration. |
   | [!UICONTROL **Favoris**] | Affichez uniquement les composants figurant dans votre liste de favoris. Pour plus d’informations sur l’ajout de composants à votre liste de favoris, consultez la section [Présentation des composants](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensions**] | Afficher uniquement les composants qui sont des dimensions. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Mesures**] | Afficher uniquement les composants qui sont des mesures. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Segments**] | Afficher uniquement les composants qui sont des segments. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Périodes**] | Afficher uniquement les composants qui sont des périodes. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Tout afficher**] | Permet d’afficher tous les composants. Cette option est réservée à l’administration. |
   | [!UICONTROL **Non approuvé**] | Permet de n’afficher que les composants qui n’ont pas encore été marqués comme approuvés par l’administration. Cette option est utile pour l’administration pour identifier les composants qui doivent être examinés et approuvés. Cette option est réservée à l’administration. |
   | [!UICONTROL **Description manquante**] | Afficher uniquement les composants qui n’ont pas encore de description dans le champ de description. Cette option est réservée à l’administration. |
   | [!UICONTROL **Afficher les doublons**] | <p>Permet de n’afficher que les composants ayant le même nom ou la même définition qu’un autre composant de la suite de rapports sélectionnée. Les noms ou définitions doivent correspondre exactement pour apparaître comme des doublons.</p><p>Cette option est réservée à l’administration.</p><p>**Remarque :** pour les définitions, cela inclut les composants que vous créez ainsi que ceux fournis par Adobe. Pour les noms, seuls les composants que vous créez et non ceux fournis par Adobe sont actuellement concernés. L’affichage de noms en double pour les composants fournis par Adobe sera intégré dans une version ultérieure.</p> |
   | [!UICONTROL **Aucune donnée récente**] | Afficher uniquement les composants qui n’ont collecté aucune donnée au cours des 90 derniers jours. Cette option est réservée à l’administration. |
   | [!UICONTROL **Création Adobe**] <!-- I don't see this option--> | Afficher uniquement les composants créés par Adobe. Les composants créés par l’administration ou une autre personne de votre organisation ne s’affichent pas. |

   {style="table-layout:auto"}

1. (Facultatif) Sélectionnez l’icône **Trier** ![icône Trier les composants](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), puis sélectionnez l’une des options de filtre suivantes pour trier la liste des composants :

   {{components-sort-options}}

1. Dans la liste des composants, sélectionnez le composant à afficher.

   Les informations suivantes sur le composant s’affichent :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Approuvés**] | <p>Indique que le composant a été révisé et approuvé par l’administration.</p><p>Une fois qu’un composant est approuvé, l’administration peut supprimer l’approbation en cliquant sur le bouton **Approuvé**.</p> |
   | [!UICONTROL **Approbation requise**] | <p>Indique que le composant n’a pas encore été révisé et approuvé par l’administration.</p><p>Un bouton dédié permet à l’administration d’[!UICONTROL **Approuver**] le composant. Celui-ci est alors marqué comme « Approuvé » pour les utilisateurs et utilisatrices.</p> |
   | [!UICONTROL **Description**] | Décrit la fonction prévue du composant. (Ces informations sont ajoutées par l’administration Analytics, comme décrit dans la section [Ajouter des descriptions de composant](/help/analyze/analysis-workspace/components/add-component-descriptions.md)). |
   | [!UICONTROL **Fréquemment utilisé avec**] | <p>Affiche les composants les plus couramment utilisés avec le composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants peuvent s’afficher parmi les 5 types de composants principaux : mesure, mesure calculée, Dimension, segment et période.</p><p>Cette liste est basée sur les données des 90 derniers jours. Seuls les composants que vous êtes en droit de consulter s’affichent.</p><p>L’administration peut personnaliser les composants visibles par les utilisateurs et utilisatrices au sein de cette section en sélectionnant les composants souhaités dans les champs déroulants [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**]. Appliquez le filtre **Tout afficher** avant de procéder à la sélection des composants visibles par les utilisateurs et utilisatrices afin de vous assurer de voir tous les composants, même ceux qui ne sont pas partagés avec vous.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
   | [!UICONTROL **Similaire à**] | <p>Permet d’afficher les composants dotés de noms similaires au composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants peuvent s’afficher parmi les 5 types de composants principaux : mesure, mesure calculée, Dimension, segment et période.</p><p>Seuls les composants que vous êtes autorisé à consulter s’affichent.</p><p>Tous les composants en double de votre suite de rapports s’affichent également ici. L’administration d’Analytics doit identifier et supprimer tous les composants en double, comme décrit dans la section [Surveiller l’intégrité du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>L’administration peut personnaliser les composants visibles par les utilisateurs et utilisatrices au sein de cette section en sélectionnant les composants souhaités dans les champs déroulants [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**]. Appliquez le filtre **Tout afficher** avant de procéder à la sélection des composants visibles par les utilisateurs et utilisatrices afin de vous assurer de voir tous les composants, même ceux qui ne sont pas partagés avec vous.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**Remarque :** actuellement, la section **Similaire à** comprend uniquement les composants que vous créez, et non ceux fournis par Adobe. Les composants fournis par Adobe seront ajoutés dans une version ultérieure.</p> |
   | [!UICONTROL **Balises**] | Affiche toutes les balises associées au composant. L’administration peut ajouter des balises lors de la modification du composant. |
   | [!UICONTROL **Type de composant**] | Indique le type du composant : dimension, mesure, segment ou période. |
   | [!UICONTROL **Créé par**] | Affiche le nom de l’utilisateur ou de l’utilisatrice ayant créé le composant. |
   | [!UICONTROL **Aperçu**] | Affiche un aperçu de l’apparence du composant dans Analysis Workspace. |
   | [!UICONTROL **Date de la dernière modification**] | Affiche le jour de la dernière modification du composant. Cette section s’affiche lorsque vous affichez des segments, des mesures calculées et des périodes. |

   {style="table-layout:auto"}

1. (Facultatif) Faites glisser un composant du dictionnaire de données vers Analysis Workspace.
