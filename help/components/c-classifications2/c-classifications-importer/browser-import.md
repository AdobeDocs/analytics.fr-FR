---
description: Vous pouvez importer (télécharger) des données de classification à l’aide du navigateur. Cette méthode limite le téléchargement des données de classification à une seule suite de rapports.
subtopic: Classifications
title: Importation navigateur
topic: Admin tools
uuid: 56dfbf4c-36e6-49f4-b5cb-8ab714432825
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Importation navigateur

Vous pouvez importer (télécharger) des données de classification à l’aide du navigateur. Cette méthode limite le téléchargement des données de classification à une seule suite de rapports.

## Importation navigateur {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Vous pouvez importer (télécharger) des données de classification à l’aide du navigateur. Cette méthode limite le téléchargement des données de classification à une seule suite de rapports.

**[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**

## Classifications – Importation navigateur – Description des champs {#section_F628C47081DA4026A4D30E3D3454B1DA}

<table id="table_7FC7E510E7E74C2D9E8F316C5C6B66DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Sélectionner une suite de rapports </td> 
   <td colname="col2"> <p>Suite de rapports dans laquelle vous souhaitez importer les données de classification. Le fichier de données d’importation doit correspondre au format de l’ensemble de données de la suite de rapports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Données à classer </td> 
   <td colname="col2"> <p>Jeu de données de réception des classifications. La liste déroulante comprend tous les rapports des suites de rapports qui sont configurés pour les classifications. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sélectionner le fichier à importer </td> 
   <td colname="col2"> <p>Permet de rechercher le fichier de données d’importation à télécharger. </p> <p>Remarque : La taille du fichier de téléchargement est limitée à 1 Mo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Remplacer les données en cas de conflit </td> 
   <td colname="col2"> <p>Remplace automatiquement les données existantes qui entrent en conflit avec les données importées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Télécharger automatiquement le fichier de classification après la fin de l’importation </td> 
   <td colname="col2"> <p>Télécharge automatiquement un fichier délimité par des tabulations qui représente le jeu de données avec les données de classification nouvellement chargées. Adobe génère automatiquement ce fichier si l’importation crée des identifiants uniques ou en cas d’erreurs. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Importer des classifications par le biais du navigateur {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

<!-- 

t_upload_a_saint_data_file_via_web_browser.xml

 -->

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
1. Cliquez sur **[!UICONTROL Importer un fichier]**.
1. Configurez les champs **[!UICONTROL Importation navigateur]**.
1. Cliquez sur **[!UICONTROL Importer un fichier]**.
1. Vérifiez les messages de traitement dans la fenêtre d’état.
1. (Sous condition) Si vous avez sélectionné **[!UICONTROL Télécharger automatiquement le fichier de classification au terme du téléchargement vers le serveur]**, indiquez où stocker le fichier obtenu une fois l’importation terminée.
>Une importation réussie affiche immédiatement les modifications adéquates dans une exportation. Toutefois, les modifications des données dans les rapports peuvent prendre jusqu’à quatre heures pour s’afficher en cas d’importation avec l’option Navigateur (et jusqu’à 24 heures en cas d’importation FTP).

