---
description: Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. Vous appliquez une variable au jeu de règles. Si vous souhaitez créer plusieurs jeux de règles pour une variable, vous devez appliquer chaque jeu de règles à plusieurs suites de rapports.
subtopic: Classifications
title: Jeux de règles de classification
topic: Admin tools
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 0e97e28ffb2bf94acfb382c3f97ff30b31321467

---


# Jeux de règles de classification

Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. Vous appliquez une variable au jeu de règles. Si vous souhaitez créer plusieurs jeux de règles pour une variable, vous devez appliquer chaque jeu de règles à plusieurs suites de rapports.

## Jeux de règles de classification

Un jeu de règles est un groupe de règles de classification relatives à une variable spécifique. Vous appliquez une variable au jeu de règles. Si vous souhaitez créer plusieurs jeux de règles pour une variable, vous devez appliquer chaque jeu de règles à plusieurs suites de rapports.

## Page du créateur de règles de classification  {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Les champs et options suivants sont disponibles sur le [!UICONTROL Classifications Rule Builder].

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/components/c-classifications2/crb/classification-rule-set.md"  > Ajouter un jeu de règles</a> </p> </td> 
   <td colname="col2"> <p>Crée un jeu de règles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Règles </p> </td> 
   <td colname="col2"> Affiche le nombre de règles contenues dans le jeu. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>État </p> </td> 
   <td colname="col2"> Affiche l’état   du jeu de règles, tel que Brouillon ou Actif. Les règles actives sont traitées quotidiennement, en examinant les données de classification qui remontent généralement à un mois. Les règles recherchent automatiquement les nouvelles valeurs et téléchargent les classifications. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dernière modification </p> </td> 
   <td colname="col2"> Indique le moment où le jeu de règles a été modifié. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dupliquer </p> </td> 
   <td colname="col2"> Duplique (copie) un jeu de règles, de telle sorte que vous puissiez l’appliquer à une autre variable ou à la même variable dans une autre suite de rapports. </td> 
  </tr> 
 </tbody> 
</table>

## Créer un jeu de règles de classification {#create-classification-rule-set}

Nommez le jeu de règles de classification, appliquez la variable et spécifiez les paramètres de remplacement.

1. (Prerequisite) Define the classification structure in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

   (Voir [Classifications](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) dans l’aide des outils d’administration sur l’ajout de classifications.)

   Variables will display in the [!UICONTROL New Rule Set] panel only after they have at least one classification defined for that variable.

   Vous pouvez créer des classifications sur une variable dans **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Traffic]** > **[!UICONTROL Traffic Classifications]** (ou **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**). Then select the variable, then click **[!UICONTROL Add Classification]**.

1. Pour créer le jeu de règles, cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]** > **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. Nommez le jeu de règles, puis cliquez sur **[!UICONTROL Create Rule Set]**.
1. Sélectionnez le jeu de règles pour modification.

   ![](assets/classification_rules_page.png)

1. Cliquez sur **[!UICONTROL Select Report Suites and Variables]**.

   La suite de rapports et le  de variables sont renseignés avec toutes les variables classées disponibles dans toutes les suites de rapports de votre de connexion. Une variable unique d’une suite de rapports ne peut appartenir qu’à un seul jeu de règles.

   See *`Variable`* in the definitions for the [Classification Rule Builder](/help/components/c-classifications2/crb/classification-rule-definitions.md) page for more information.
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. Poursuivez en [ajoutant des règles de classification](/help/components/c-classifications2/crb/classification-rule-set.md) au jeu de règles.
