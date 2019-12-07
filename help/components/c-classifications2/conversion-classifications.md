---
description: Les classifications permettent de catégoriser des valeurs dans des groupes et de générer des rapports au niveau d’un groupe. Vous pouvez, par exemple, classifier toutes les campagnes de recherche payante dans une catégorie comme termes de pop music et générer des rapports sur le succès de la catégorie par rapport à des mesures de type Instances (ou clics publicitaires), ainsi que la conversion en événements de succès.
subtopic: Classifications
title: Classifications des conversions
topic: Admin tools
uuid: 4c8726c9-f527-44e1-be01-8c7b3b5c20f0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Classifications des conversions

Les classifications permettent de catégoriser des valeurs dans des groupes et de générer des rapports au niveau d’un groupe. Vous pouvez, par exemple, classifier toutes les campagnes de recherche payante dans une catégorie comme termes de pop music et générer des rapports sur le succès de la catégorie par rapport à des mesures de type Instances (ou clics publicitaires), ainsi que la conversion en événements de succès.

## Classifications des conversions {#concept_B4B1478A8CB540599AC9D4A58CA4B6FE}

Les classifications permettent de catégoriser des valeurs dans des groupes et de générer des rapports au niveau d’un groupe. Vous pouvez, par exemple, classifier toutes les campagnes de recherche payante dans une catégorie comme *termes de pop music* et générer des rapports sur le succès de la catégorie par rapport à des mesures de type Instances (ou clics publicitaires), ainsi que la conversion en événements de succès.

Les classifications de conversion vous permettent de classer des variables de conversion. Une fois classé, tout rapport pouvant être généré en utilisant les données clés peut également l’être à l’aide des propriétés de données associées.

Après avoir activé les classifications, utilisez [l’importateur de classifications](/help/components/c-classifications2/c-classifications-importer/c-working-with-saint.md) pour affecter des valeurs spécifiques à la classification appropriée.

## Descriptions des classifications de conversion {#section_4A98DD5F5C314B9DAEE710AEE4EE51D4}

<table id="table_0B72C485467348E2A34BF913441F4AF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nom</span> </td> 
   <td colname="col2"> Nom de la classification. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Date d’activation (Texte uniquement)</span> </td> 
   <td colname="col2"> <p>Indique si la classification de texte est une plage de dates pour les variables Campagne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Options (Texte uniquement)</span> </td> 
   <td colname="col2">Crée une liste de valeurs de classification disponibles pour cette classification. Utilisez <span class="wintitle">Options</span> avec des variables de campagne afin de fournir aux utilisateurs la liste des valeurs prises en charge pour leur classification dans le <span class="wintitle">Gestionnaire de campagnes</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Type de nombre (Numérique uniquement)</span> </td> 
   <td colname="col2">Indique le type de nombre dans la classification numérique. Les options comprennent <span class="wintitle">Numérique</span>, <span class="wintitle">Pourcentage</span> et <span class="wintitle">Devise</span>. </td> 
  </tr> 
 </tbody> 
</table>

## Ajout de classifications de conversion {#task_D535D09E3EAF4CD1A15A6B93C0BB1BB5}

<!-- 

t_classification_conversion.xml

 -->

Description de la procédure d’ajout de classifications de conversion dans Admin.

1. Cliquez sur **[!UICONTROL Admin]** &gt; **[!UICONTROL Suites de rapports]**.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Classifications des conversions]**.
1. Dans la liste déroulante **[!UICONTROL Choisir le type de classification]**, sélectionnez la variable qui doit contenir une classification.

   ![Infos sur l’étape](assets/sub_class_create.png)

1. Placez le pointeur de la souris sur l’icône **[!UICONTROL Modifier la classification]**, puis sélectionnez **[!UICONTROL Ajouter une classification]**.
1. Dans le champ **[!UICONTROL Sélectionner un type]**, choisissez le type de classification à ajouter à la variable.

   Les options comprennent **[!UICONTROL Texte]** et **[!UICONTROL Numérique]**. Pour plus d’informations sur les types de classification, voir [À propos des classifications](/help/components/c-classifications2/c-classifications.md).
1. Dans la boîte de dialogue **[!UICONTROL Classifications de texte]**, configurez la classification selon vos besoins.

   Pour plus d’informations sur ces éléments, voir [Descriptions des classifications de conversion](/help/components/c-classifications2/conversion-classifications.md#section_4A98DD5F5C314B9DAEE710AEE4EE51D4).

1. Dans la boîte de dialogue **[!UICONTROL Liste déroulante]**, ajoutez ou supprimez des options.

   L’ajout d’options crée une liste de valeurs de classification disponibles pour cette classification. Vous pouvez utiliser cette option avec des variables de campagne afin de fournir aux utilisateurs la liste des valeurs prises en charge pour leur classification dans le gestionnaire de campagnes. Utilisez cette option pour les dimensions des classifications pour lesquelles vous avez un faible nombre de valeurs autorisées qui ne changent jamais ou rarement. Par exemple, vous pouvez exécuter différentes campagnes visant différents niveaux de fidélité des clients : Argent, Or et Platine. Vous pouvez alors utiliser la liste déroulante pour garantir que les seules valeurs qui sont acceptées sont celles qui correspondent aux trois niveaux. Si un utilisateur tente d’utiliser une valeur différente, elle est ignorée.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Suppression d’une classification de conversion {#task_566651BC245944618A6A833E58211FDE}

<!-- 

t_classification_delete_conversion.xml

 -->

Vous pouvez supprimer une classification de conversion devenue inutile.

1. Ouvrez le Gestionnaire de suites de rapports en cliquant sur **[!UICONTROL Admin]** &gt; **[!UICONTROL Suites de rapports]** dans l’en-tête de la suite.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Classifications des conversions]**.
1. Dans la liste déroulante **[!UICONTROL Choisir le type de classification]**, sélectionnez la variable dans laquelle vous souhaitez supprimer une classification.
1. Placez le pointeur de la souris sur l’icône **[!UICONTROL Modifier une classification]**, puis sélectionnez **[!UICONTROL Supprimer la classification]**.
1. Dans la boîte de dialogue Supprimer la classification, cliquez sur **[!UICONTROL Supprimer]**.
