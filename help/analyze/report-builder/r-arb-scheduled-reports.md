---
description: Description des champs du Gestionnaire des tâches planifiées.
title: Gestionnaires des tâches planifiées
topic: Report builder
uuid: dec259f0-2a04-4c94-abbc-5008cf2f1cb8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Gestionnaires des tâches planifiées

Description des champs du Gestionnaire des tâches planifiées.

Le Gestionnaire des tâches planifiées vous permet d’afficher une liste des rapports planifiés existants, ainsi que leurs destinataires, les détails de la planification et les formats de fichier. Il vous permet également de réactiver les classeurs planifiés dont l’exécution a échoué.

<table id="table_21B07A0B5F1D4435A4E882E45A7A6B6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Onglet <b>Rapports planifiés</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom de rapport </p> </td> 
   <td colname="col2"> <p>Indique le nom de la tâche planifiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Courriel/FTP </p> </td> 
   <td colname="col2"> <p>Adresse électronique ou FTP du destinataire. </p> <p>Remarque : si vous avez sélectionné Courriel, les rapports de plus de 1 Mo sont automatiquement joints sous forme de fichier .zip. Cette fonction évite que les pièces jointes ne soient trop volumineuses ; elle ne peut pas être désactivée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Options de publication </p> </td> 
   <td colname="col2"> <p>Cette colonne contient Power BI si l’une des <a href="/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md"  > options de publication Power BI</a> est sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Planifier </p> </td> 
   <td colname="col2"> <p>Type de la remise planifiée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Format du fichier </p> </td> 
   <td colname="col2"> <p> Format de remise du rapport, tel que Excel, PDF, HTML, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Réactiver </p> </td> 
   <td colname="col2"> <p>Si l’exécution d’un classeur planifié échoue, le Créateur de rapports effectue deux tentatives d’exécution supplémentaires espacées de 15 minutes. Après trois tentatives infructueuses, le Créateur de rapports désactive le planning et affiche le bouton <span class="wintitle">Réactiver</span>. Lorsque vous réactivez un classeur, la remise planifiée redémarre au niveau du point de désactivation. </p> <p>Par exemple, si vous avez réactivé aujourd’hui un classeur planifié qui a été désactivé il y a 14 jours, il est exécuté et distribué 14 fois, soit 1 fois par jour de désactivation. Si vous ne souhaitez pas que la remise soit effectuée pour les jours manquants, vous pouvez supprimer le classeur planifié, puis en créer un nouveau en utilisant les mêmes paramètres de planification. </p> <p> <p>Remarque : il est déconseillé de réactiver un classeur, sauf si vous connaissez le motif de sa désactivation. Une méthode de dépannage consiste à télécharger un classeur désactivé, puis à l’actualiser sur le client. Si aucune erreur n’est détectée, vous devriez être en mesure de le réactiver. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dernier envoi </p> </td> 
   <td colname="col2"> <p>Date et heure auxquelles le rapport a été envoyé en dernier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Onglet <b>Destinataire</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Courriel du destinataire </p> </td> 
   <td colname="col2"> Adresse électronique du destinataire du rapport. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rapports </p> </td> 
   <td colname="col2"> Le ou les rapports qui ont été envoyés à chaque destinataire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Onglet <b>Historique des rapports</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom de fichier </p> </td> 
   <td colname="col2"> Indique le nom de la tâche planifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date </p> </td> 
   <td colname="col2"> Date et heure auxquelles le rapport a été envoyé en dernier. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>État </p> </td> 
   <td colname="col2"> L’état indique si le rapport a été Envoyé ou Pas envoyé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Courriel/FTP </p> </td> 
   <td colname="col2"> Adresse électronique ou FTP du destinataire du rapport. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Format du fichier </p> </td> 
   <td colname="col2"> Format de remise du rapport, tel que Excel, PDF, HTML, etc. </td> 
  </tr> 
 </tbody> 
</table>
