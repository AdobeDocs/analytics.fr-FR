---
description: Créez, gérez et consultez l’utilisation des sources de données dans une suite de rapports.
subtopic: Data sources
title: Gestionnaire des sources de données
topic: Developer and implementation
uuid: ccfa4a1c-7c56-421b-8ee6-a42b334659b1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Gestionnaire des sources de données

Créez, gérez et consultez l’utilisation des sources de données dans une suite de rapports.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; Sources **[!UICONTROL de]** données.

## Onglet Créer {#section_74603FDA3D8842E49F1A51624A06DE20}

Cet onglet permet de configurer une nouvelle source de données pour la suite de rapports actuellement sélectionnée. Lorsque vous activez une source de données, l’[!UICONTROL Assistant Sources de données] vous guide tout au long du processus de création d’un modèle de source de données, puis crée un emplacement FTP pour le transfert des données.

La sélection que vous effectuez sur l’onglet Créer détermine les champs initiaux dans le modèle créé. Reportez-vous à la section [Génération d’un modèle de fichier d’importation](/help/import/c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md).

## Onglet Gérer {#section_DD559A6701CA45F1A85E56F840F48DBE}

<table id="table_F74696EC855441328CFE0BF49C20D9B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nouveau traitement </p> </td> 
   <td colname="col2"> <p>Relance le traitement des sources de données précédemment interrompu en raison d’erreurs ou d’avertissements. Le traitement se poursuit jusqu’à la prochaine erreur. La fonctionnalité Sources de données interrompt le traitement d’un fichier de source de données uniquement lorsque vous sélectionnez <span class="uicontrol">Arrêter le traitement en cas d’erreur</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Terminer le traitement </p> </td> 
   <td colname="col2"> <p>Indique à la fonctionnalité Sources de données de clôturer les visites ouvertes dans le fichier et de terminer le traitement du fichier comme s’il était complet. Ceci est utile lorsque des visites s’étendent sur plusieurs fichiers de source de données. Ceci s’applique également au <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Traitement complet</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Désactiver </p> </td> 
   <td colname="col2"> <p> La désactivation d’une source de données supprime cette dernière. Si le traitement de certains fichiers sur le serveur est commencé, il se poursuit jusqu’à ce qu’il soit terminé. Les fichiers dont le traitement n’a pas encore commencé ne seront pas traités. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Arrêter le traitement en cas d’erreur/d’avertissement </p> </td> 
   <td colname="col2"> <p> Indique au moteur de traitement des sources de données d’interrompre le traitement en cas d’erreur. Le traitement ne reprend que lorsque vous sélectionnez Nouveau traitement. L’option Arrêter le traitement en cas d’avertissement s’applique uniquement au <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Traitement complet</a>. </p> <p>Si la fonctionnalité Sources de données détecte une erreur de fichier, elle vous en informe. Le système déplace le fichier Sources de données comportant l’erreur dans un dossier intitulé <span class="filepath">files_with_errors</span> sur le serveur FTP. Une fois le problème résolu, renvoyez le fichier pour qu’il soit traité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurer </p> </td> 
   <td colname="col2"> <p>Vous permet de modifier le modèle de source de données ou tout autre paramètre spécifique à cette source de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Infos FTP </p> </td> 
   <td colname="col2"> <p>Affiche les informations du site FTP pour cette source de données. Utilisez ces informations pour accéder au modèle de source de données et envoyer les données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom de fichier </p> </td> 
   <td colname="col2"> <p>Nom du fichier transféré. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>État </p> </td> 
   <td colname="col2"> <p> État actuel du fichier. Les valeurs d’état possibles sont les suivantes : </p> 
    <ul id="ul_56A0BF8C1BE249F6BB39B0D11DA3997F"> 
     <li id="li_BAB359E08EDE4E0298C0362258789603">En file d’attente (étape 1 sur 3) : le fichier existe, mais son traitement n’a pas commencé. If the file doesn't appear within 30 minutes, check that the associated <span class="filepath"> .fin</span> file is present </li> 
     <li id="li_A09A14F42CB74F01B694799740B3DA17">En préparation (étape 2 sur 3) : le fichier est analysé afin de vérifier s’il contient des erreurs ou des avertissements. </li> 
     <li id="li_793FDCDB64CF434D82CAF5B6E9BDE557">En traitement (étape 3 sur 3) : le fichier est en cours de traitement. </li> 
     <li id="li_1D8C4B241FF0453EAF7DDFD8354C5573">Échec : le fichier n’a pas été traité en raison d’erreurs. </li> 
     <li id="li_A52507602FB4492B83A70AF6449A539A">Succès : le fichier a été complètement traité. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Onglet Journal des fichiers {#section_B7AC7EE8CAD740A59DD53CF1919373F0}

Le journal des fichiers est doté d’une fonction de recherche grâce à laquelle vous pouvez rechercher des informations par nom ou type de source de données, nom de fichier, date de réception ou état.
