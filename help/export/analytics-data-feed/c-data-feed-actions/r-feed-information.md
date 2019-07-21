---
description: Utilisez la section Informations sur les flux pour nommer le flux, définir la suite de rapports sur laquelle l’exécuter, déterminer sa fréquence ainsi que sa date et son heure de début et de fin.
keywords: Flux de données ; informations ; name ; suite de rapports ; email une fois terminé ; email ; intervalle ; flux ; le traitement du délai ; delay ; start ; end ; date ; flux continu
seo-description: Utilisez la section Informations sur les flux pour nommer le flux, définir la suite de rapports sur laquelle l’exécuter, déterminer sa fréquence ainsi que sa date et son heure de début et de fin.
seo-title: Informations sur les flux
solution: Analytics
title: Informations sur les flux
uuid: adf 92 f 42-a 957-4 de 0-a 5 a 1-683 f 2933 af 04
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Informations sur les flux

Utilisez la section Informations sur les flux pour nommer le flux, définir la suite de rapports sur laquelle l’exécuter, déterminer sa fréquence ainsi que sa date et son heure de début et de fin.

![](assets/feed-info.jpg)

<table id="table_C98C7C3CE4194BEF819E792793EBC517">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Champ </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nom (obligatoire) </p> </td>
   <td colname="col2"> <p>Saisissez le nom du flux. </p> <p>Le nom doit être unique au sein de la suite de rapports sélectionnée et peut comporter jusqu’à 255 caractères. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Suite de rapports (obligatoire) </p> </td>
   <td colname="col2"> <p>Indiquez les suites de rapports pour la demande de flux. </p> <p>Vous devez sélectionner au moins une suite de rapports. Vous ne pouvez pas répertorier deux fois la même suite de rapports. </p> <p>Toutes les suites de rapports non virtuelles disponibles pour l'utilisateur connecté sont disponibles. </p></td>
  </tr>
  <tr>
   <td colname="col1"> <p>Envoyer par courrier électronique une fois terminé (obligatoire) </p> </td>
   <td colname="col2"> <p>Indiquez l’adresse électronique du destinataire des mises à jour de diffusion du flux. </p> <p>Ce champ ne peut pas être vide. Il doit contenir une adresse électronique correcte. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Intervalle du flux (obligatoire) </p> </td>
   <td colname="col2"> <p>Indiquez la fréquence prévue. </p> <p>Remarque : En raison de la taille potentielle des fichiers compressés du flux de données, veillez à ce que le processus ETL utilise un utilitaire de compression de 64 bits. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Traitement du délai (facultatif) </p> </td>
   <td colname="col2"> <p>Indiquez quel délai appliquer entre chaque instance planifiée. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Date de début et de fin (obligatoire) </p> <p>Flux continu (facultatif) </p> </td>
   <td colname="col2"> <p>Définissez à quelles dates le flux commencera et s’arrêtera. </p> <p>
     <ul id="ul_509977336CD34032924B48E043E8CBC7">
      <li id="li_BFB5B6ADCB184D839C9BA42DB3DCAF32">Date de début : par défaut, la date d’aujourd’hui. </li>
      <li id="li_34F8DB45D9B54076840D1A0B782812D3">Date de fin : par défaut, la date de demain. </li>
     </ul>
     </p> </td>
  </tr>
 </tbody>
</table>