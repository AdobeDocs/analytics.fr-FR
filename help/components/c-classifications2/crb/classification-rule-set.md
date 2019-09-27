---
description: Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. Vous appliquez une variable au jeu de règles. Si vous souhaitez créer plusieurs jeux de règles pour une seule variable, vous devez appliquer chacun d’eux à plusieurs suites de rapports.
seo-description: Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. Vous appliquez une variable au jeu de règles. Si vous souhaitez créer plusieurs jeux de règles pour une seule variable, vous devez appliquer chacun d’eux à plusieurs suites de rapports.
seo-title: Jeux de règles de classification
solution: Analytics
subtopic: Classifications
title: Jeux de règles de classification
topic: Outils d’administration
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Jeux de règles de classification

Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. Vous appliquez une variable au jeu de règles. Si vous souhaitez créer plusieurs jeux de règles pour une seule variable, vous devez appliquer chacun d’eux à plusieurs suites de rapports.

## Jeux de règles de classification {#concept_CD3D510F5070486584F3BB535AE41524}

Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. Vous appliquez une variable au jeu de règles. Si vous souhaitez créer plusieurs jeux de règles pour une seule variable, vous devez appliquer chacun d’eux à plusieurs suites de rapports.

## Page du créateur de règles de classification {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]**

Les champs et options ci-dessous sont disponibles sur la page [!UICONTROL Créateur de règles de classifications].

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B" format="dita" scope="local"> Ajouter un jeu de règles</a> </p> </td> 
   <td colname="col2"> <p>Crée un jeu de règles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Règles </p> </td> 
   <td colname="col2"> Affiche le nombre de règles du jeu. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>État </p> </td> 
   <td colname="col2"> Affiche l’état d’activité du jeu de règles ; Version préliminaire ou Actif, par exemple. Les règles actives sont traitées tous les jours ; elles examinent les données de classification remontant généralement à un mois. Les règles recherchent automatiquement les nouvelles valeurs et téléchargent les classifications. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dernière modification </p> </td> 
   <td colname="col2"> Indique la date de la dernière modification du jeu de règles. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dupliquer </p> </td> 
   <td colname="col2"> Duplique (copie) un jeu de règles, de telle sorte que vous puissiez l’appliquer à une autre variable ou à la même variable dans une autre suite de rapports. </td> 
  </tr> 
 </tbody> 
</table>

## Create a Classification Rule Set {#task_86F216DFD2534FA181E64ABDF306782B}

<!-- 

t_classification_rule_set.xml

 -->

Nommez le jeu de règles de classification, appliquez la variable et spécifiez les paramètres de remplacement.

1. (Prerequisite) Define the classification structure in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.

   (Voir [Classifications](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) dans l’aide des outils d’administration à propos de l’ajout de classifications.)

   Les variables s’affichent dans le panneau [!UICONTROL Nouveau jeu de règles] uniquement une fois qu’au moins une classification est définie pour la variable.

   You can create classifications on a variable in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Traffic]** &gt; **[!UICONTROL Traffic Classifications]** (or **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**). Sélectionnez ensuite la variable et cliquez sur **[!UICONTROL Ajouter une classification]**.

1. To create the rule set, click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]** &gt; **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. Name the rule set, then click **[!UICONTROL Create Rule Set]**.
1. Sélectionnez le jeu de règles pour modification.

   ![](assets/classification_rules_page.png)

1. Click **[!UICONTROL Select Report Suites and Variables]**.

   La liste des suites de rapports et des variables contient toutes les variables classées disponibles dans l’ensemble des suites de rapports de la société qui a établi la connexion. Une variable unique d’une suite de rapports ne peut appartenir qu’à un seul jeu de règles.

   Voir *`Variable`* dans les définitions de la page [Créateur de règles de classifications](../../../components/c-classifications2/crb/classification-rule-definitions.md#section_4D1A70A607C9419EB2116A5174EACB72) pour plus d’informations.
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. Continue by [adding classification rules](../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B) to the rule set.
