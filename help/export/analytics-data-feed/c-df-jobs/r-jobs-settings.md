---
description: Lorsque vous configurez un flux, certains paramètres déterminent la fréquence de traitement des tâches.
keywords: Flux de données ; tâche ; paramètres ; quotidien ; horaire ; Renvois de données pour les flux de données horaires ; renvoi
seo-description: Lorsque vous configurez un flux, certains paramètres déterminent la fréquence de traitement des tâches.
seo-title: Paramètres de tâches
solution: Analytics
title: Paramètres de tâches
uuid: e 124 b 4 f 1-0168-4 eaa -8657-19207 b 2 f 263 f
translation-type: tm+mt
source-git-commit: b6169d2febded32d772f82d5917b1132695ab442

---


# Paramètres de tâches

Lorsque vous configurez un flux, certains paramètres déterminent la fréquence de traitement des tâches.

Utilisez les paramètres suivants pour configurer les horaires de traitement des tâches. Ces paramètres sont définis au niveau du flux et non pas au niveau des tâches.

<table id="table_2070F73212F245E98DADC6B5DFDB1C72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Quotidien </td> 
   <td colname="col2"> <p>Chaque jour, les données sont envoyées dans un fichier compressé unique. Ce fichier ne peut pas excéder 2 Go. Si le fichier dépasse 2 Go de données non compressées, des fichiers supplémentaires sont créés. Vous recevez tous les fichiers en un seul envoi chaque jour. </p> <p>Chaque fichier est nommé selon le format suivant : </p> <p> <span class="filepath"><span class="varname"> reportsuite</span>-<span class="varname"> date</span>.tar</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Horaire (par défaut) </td> 
   <td colname="col2"> <p>Les données correspondant à chaque heure sont remises dans un seul fichier compressé contenant l’ensemble des données reçues au cours de cette période d’une heure. Vous recevez 24 remises distinctes pour chaque jour, chaque fichier étant livré après le traitement des données relatives à cette période d’une heure. </p> <p>Le terme « horaire » décrit la période des données envoyées avec chaque exportation et non la période au cours de laquelle la remise est effectuée. Les flux de données horaires sont traités et distribués selon la méthode d’acheminement au mieux (best-effort delivery). </p> <p>S’agissant des flux de données horaires, on s’attend à ce que, dans 95 % des cas, le flux soit diffusé dans les 12 heures suivant la collecte de l’équivalent des données de cette période horaire. Les flux de données des suites de rapports avec de forts volumes de trafic peuvent nécessiter davantage de temps de traitement et de diffusion. </p> <p>Il ne faut pas confondre la réception d’un flux de données horaire et la réception d’un flux quotidien avec remise de plusieurs fichiers. Lors de la réception de flux de données horaires, les données correspondant à chaque jour sont divisées en 24 fichiers sur la base des données collectées pour cette période d’une heure, et chaque fichier est distribué dès qu’il est disponible. Un flux quotidien qui est livré sous la forme de plusieurs fichiers est distribué une fois par jour après le traitement des données du jour précédent et divisé en incréments de 2 Go sur la base de la quantité de données collectées. </p> <p>Chaque fichier est nommé selon le format suivant : </p> <p> <span class="filepath"><span class="varname"> reportsuite</span>-<span class="varname"> date</span>-<span class="varname"> heure</span>.tar</span> </p> <p>Voir <a href="../../../export/analytics-data-feed/c-df-contents/jobs-faq.md#concept_7C67A012CCF64B0C8DA33E5A6CF7FD9E" format="dita" scope="local">FAQ sur les tâches</a> pour en savoir plus sur les facteurs qui peuvent impacter les flux horaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Renvois de données pour les flux de données horaires </td> 
   <td colname="col2"> <p>Si vous demandez des données pour des dates antérieures lors de la configuration d’un nouveau flux de données horaire, les données pour les dates renvoyant à plus de 60 jours dans le passé peuvent être distribuées sous un format quotidien plutôt qu’horaire. </p> <p>Dans ce cas, vous ne recevrez pas 24 livraisons distinctes pour les jours concernés, mais vous recevrez une seule livraison avec un horodatage à minuit, contenant toutes les données pour la journée. Si vous demandez ce type de renvoi, veillez à ce que votre ETL soit configuré pour gérer les livraisons quotidiennes. </p> </td> 
  </tr> 
 </tbody> 
</table>

