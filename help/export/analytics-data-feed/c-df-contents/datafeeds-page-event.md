---
description: Table de recherche permettant de déterminer le type d’un accès d’après la valeur page_event.
keywords: Data Feed;page;event;page_event;post_page_event
solution: Analytics
title: Recherche d’événement de page
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Recherche d’événement de page

Table de recherche permettant de déterminer le type d’un accès d’après la valeur page_event.

<table id="table_33AF375E0B41474696D7A4A92C652A5F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’accès </th> 
   <th colname="col02" class="entry"> Valeur page_event </th> 
   <th colname="col2" class="entry"> Valeur post_page_event </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Pages vues </td> 
   <td colname="col02"> Identique à la publication </td> 
   <td colname="col2"> <p>0 for all page views ( <code> s.t() </code> calls) </p> <p>0 pour les appels <code> trackState </code> en provenance de kits SDK mobiles </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suivi des liens  </td> 
   <td colname="col02"> <p>10 pour « autre lien » </p> <p>10 pour les appels <code> trackAction </code> et de cycle de vie en provenance de kits SDK mobiles </p> <p>11 pour « lien de téléchargement » </p> <p>12 pour « lien de sortie ou externe » </p> </td> 
   <td colname="col2"> <p>100 pour « autre lien » </p> <p>100 pour les appels <code> trackAction </code> et de cycle de vie en provenance de kits SDK mobiles </p> <p>101 pour « lien de téléchargement » </p> <p>102 pour « lien de sortie ou externe » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vidéo – Jalon </td> 
   <td colname="col02"> 
    <!--<p>30 - Legacy full media tracking event at the end of the video playback (no longer supported)</p>--> <p>31 – Événement de début du média </p> <p>32 – Événement de mise à jour du média uniquement (pas de traitement d’eVar ou d’une quelconque autre variable) </p> <p>33 – Événement de mise à jour de média + autre variable (y compris le traitement d’eVar et d’une autre variable) </p> </td> 
   <td colname="col2"> 
    <!--<p> 75 - Legacy full media tracking event at theend of the video playback (no longer supported)</p>--> <p> 76 – Événement de début du média </p> <p>77 – Événement de mise à jour du média uniquement (pas de traitement d’eVar ou d’une quelconque autre variable) </p> <p>78 – Événement de mise à jour de média + autre variable (y compris le traitement d’eVar et d’une autre variable) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vidéo – Pulsation </p> </td> 
   <td colname="col02"> Identique à la publication </td> 
   <td colname="col2"> <p> 50 = (non Primetime) Début du flux média </p> <p> 51 = (non Primetime) Fermeture du flux média (Complet/Terminer) </p> <p> 52 = (non Primetime) Défilement du flux média </p> <p> 53 = (non Primetime) Connexion persistante du flux de média </p> <p> 54 = (non Primetime) Début de publicité du flux média </p> <p> 55 = (non Primetime) Fermeture de publicité du flux média (Complet/Terminer) </p> <p> 56 = (non Primetime) Recherche de publicité dans le flux média </p> <p> 60 = (Primetime) Début du flux média </p> <p> 61 = (Primetime) Fermeture du flux média (Complet/Terminer) </p> <p> 62 = (Primetime) Défilement du flux média </p> <p> 63 = (Primetime) Connexion persistante du flux de média </p> <p> 64 = (Primetime) Début de publicité du flux média </p> <p> 65 = (Primetime) Fermeture de publicité du flux média (Complet/Terminer) </p> <p> 66 = (Primetime) Recherche de publicité dans le flux média </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sondage </td> 
   <td colname="col02"> 40 </td> 
   <td colname="col2"> 80 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Analytics pour Target </td> 
   <td colname="col02"> 70 - Indique un accès qui inclut des données sur l’activité Target, associé ou non à un appel Analytics. </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

