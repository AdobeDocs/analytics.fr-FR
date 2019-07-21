---
description: Les classifications permettent de catégoriser des valeurs dans des groupes et de générer des rapports au niveau d’un groupe. Vous pouvez, par exemple, classifier toutes les campagnes de recherche payante dans une catégorie comme termes de pop music et générer des rapports sur le succès de la catégorie par rapport à des mesures de type Instances (ou clics publicitaires), ainsi que la conversion en événements de succès.
seo-description: Les classifications permettent de catégoriser des valeurs dans des groupes et de générer des rapports au niveau d’un groupe. Vous pouvez, par exemple, classifier toutes les campagnes de recherche payante dans une catégorie comme termes de pop music et générer des rapports sur le succès de la catégorie par rapport à des mesures de type Instances (ou clics publicitaires), ainsi que la conversion en événements de succès.
seo-title: Classifications des conversions
solution: Analytics
subtopic: Gestionnaire
title: Classifications des conversions
topic: Outils d’administration
uuid: 4 c 8726 c 9-f 527-44 e 1-be 01-8 c 7 b 3 b 5 c 20 f 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Classifications des conversions

Les classifications permettent de catégoriser des valeurs dans des groupes et de générer des rapports au niveau d’un groupe. Vous pouvez, par exemple, classifier toutes les campagnes de recherche payante dans une catégorie comme termes de pop music et générer des rapports sur le succès de la catégorie par rapport à des mesures de type Instances (ou clics publicitaires), ainsi que la conversion en événements de succès.

## Conversion classifications {#concept_B4B1478A8CB540599AC9D4A58CA4B6FE}

Les classifications permettent de catégoriser des valeurs dans des groupes et de générer des rapports au niveau d’un groupe. Vous pouvez, par exemple, classifier toutes les campagnes de recherche payante dans une catégorie comme *termes de pop music* et générer des rapports sur le succès de la catégorie par rapport à des mesures de type Instances (ou clics publicitaires), ainsi que la conversion en événements de succès.

Les classifications de conversion vous permettent de classer des variables de conversion. Une fois classé, tout rapport pouvant être généré en utilisant les données clés peut également l’être à l’aide des propriétés de données associées.

Après avoir activé les classifications, utilisez [l’importateur de classifications](../../components/c-classifications2/c-classifications-importer/c-working-with-saint.md#concept_08ED8C7A86C64E7DA5DE3044BB94B2EA) pour affecter des valeurs spécifiques à la classification appropriée.

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

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Sélectionnez une suite de rapports.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**.
1.   Dans la liste déroulante **Choisir le type de classification**, sélectionnez la variable qui doit contenir une classification. 

   ![Informations sur les étapes](assets/sub_class_create.png)

1. Mouse over the **[!UICONTROL Edit Classification]** icon, then select **[!UICONTROL Add Classification]**.
1.   Dans le champ **Sélectionner un type**, choisissez le type de classification à ajouter à la variable. 

   Options include **[!UICONTROL Text]** and **[!UICONTROL Numeric]**. For more information on classification types, see [About Classifications](../../components/c-classifications2/c-classifications.md#concept_4CEC7FF1A9E24204A7DA6B9AC70709DE).
1. In the **[!UICONTROL Text Classifications]** dialog box, configure the classification as desired.

   Pour plus d’informations sur ces éléments, voir [Descriptions des classifications de conversion](../../components/c-classifications2/conversion-classifications.md#section_4A98DD5F5C314B9DAEE710AEE4EE51D4).

1. In the **[!UICONTROL Dropdown List]** dialog box, add or remove options.

   L’ajout d’options crée une liste de valeurs de classification disponibles pour cette classification. Vous pouvez utiliser cette option avec des variables de campagne afin de fournir aux utilisateurs la liste des valeurs prises en charge pour leur classification dans le gestionnaire de campagnes. Utilisez cette option pour les dimensions des classifications pour lesquelles vous avez un faible nombre de valeurs autorisées qui ne changent jamais ou rarement. Par exemple, vous pouvez exécuter différentes campagnes visant différents niveaux de fidélité des clients : Argent, Or et Platine. Vous pouvez alors utiliser la liste déroulante pour garantir que les seules valeurs qui sont acceptées sont celles qui correspondent aux trois niveaux. Si un utilisateur tente d’utiliser une valeur différente, elle est ignorée.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Suppression d’une classification de conversion {#task_566651BC245944618A6A833E58211FDE}

<!-- 

t_classification_delete_conversion.xml

 -->

Vous pouvez supprimer une classification de conversion devenue inutile.

1. Open the Report Suite Manager by clicking **[!UICONTROL Admin]**&gt; **[!UICONTROL Report Suites]** in the Suite header.
1. Sélectionnez une suite de rapports.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**.
1.   Dans la liste déroulante **Choisir le type de classification**, sélectionnez la variable dans laquelle vous souhaitez supprimer une classification. 
1. Mouse over the **[!UICONTROL Edit Classification]** icon, then select **[!UICONTROL Delete Classification]**.
1. Dans la boîte de dialogue Supprimer la classification, cliquez sur **[!UICONTROL Supprimer]**.
