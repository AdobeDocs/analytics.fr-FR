---
description: Description des champs de gestion des requêtes dans le Créateur de rapports.
title: Gestion des requêtes - Définitions
topic: Report builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Gestion des requêtes - Définitions

Description des champs de gestion des requêtes dans le Créateur de rapports.

## Aperçu {#section_75C288C945FA4781A4EDF806711A5660}

Le [!UICONTROL Gestionnaire de requêtes] présente une vue détaillée de l’état de toutes les requêtes générées pour toutes les feuilles ou pour une seule feuille du classeur actif. Il permet également d’ajouter, de modifier, d’actualiser et de supprimer une requête (fonctions généralement associées à l’[!UICONTROL Assistant Requête] et au [!UICONTROL Gestionnaire de requêtes]) en cliquant avec le bouton droit sur l’une des cellules disponibles de la feuille de calcul Excel qui contient les requêtes précédentes.

Le Gestionnaire de [!UICONTROL requêtes] s’affiche lorsque vous cliquez sur **[!UICONTROL Gérer]** ( ![](assets/edit_request.gif) dans la barre d’outils du créateur de rapports).

> [!NOTE] Le créateur de rapports d’Adobe applique les dépendances des requêtes uniquement dans la même feuille de calcul, et non dans les feuilles de calcul. Ceci garantit la rapidité de l’exécution.

## Définitions {#section_FD29D8614DE74F32A0027FA130F40304}

<table id="table_0880204181074BDBBA37E3DF2972A672"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Toutes les feuilles </p> </td> 
   <td colname="col2"> <p>Affiche les requêtes de toutes les feuilles du classeur actif. Désactivez cette option pour afficher les requêtes de feuilles spécifiques. Vous devez, dans ce cas, cliquer sur un onglet Feuille au bas du rapport Excel afin d’afficher les requêtes associées à cette feuille dans le <span class="wintitle">Gestionnaire de requêtes</span>. Le libellé en regard de la case à cocher indique la feuille du classeur qui est actuellement sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feuille </p> </td> 
   <td colname="col2"> <p>Affiche le nom des feuilles du classeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Suite de rapports </p> </td> 
   <td colname="col2"> <p>Affiche le nom du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Période </p> </td> 
   <td colname="col2"> <p>Affiche la plage de dates spécifique au rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Granularité </p> </td> 
   <td colname="col2"> <p>Précise la granularité de la requête. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dernière exécution </p> </td> 
   <td colname="col2"> <p>Précise la date de la dernière exécution de la requête par le Créateur de rapports. Un message de diagnostic s’affiche également dans ce tableau dans la colonne <span class="wintitle">Dernière exécution</span>, le cas échéant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ajouter </p> </td> 
   <td colname="col2"> <p>Affiche la boîte de dialogue Assistant Requête. Reportez-vous à la section <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   > Créer une requête de données</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifier </p> </td> 
   <td colname="col2"> <p> (ou Modifier plusieurs) Modifie une requête sélectionnée. Le système affiche la boîte de dialogue <span class="wintitle">Assistant Requête</span>. See <a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   > Edit Multiple Requests</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Supprimer </p> </td> 
   <td colname="col2"> <p>Supprime des requêtes. Vous pouvez supprimer plusieurs requêtes sélectionnées. Vous pouvez également supprimer une requête de la liste en la sélectionnant, puis en appuyant sur la touche Suppr du clavier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Sélectionner tout </p> </td> 
   <td colname="col2"> <p>Sélectionne toutes les requêtes. Le <span class="wintitle">Gestionnaire de requêtes</span> affiche le nombre de requêtes sélectionnées au bas de la liste de requêtes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>À partir de la cellule </p> </td> 
   <td colname="col2"> <p>Récupère les données d’une requête de la feuille de calcul. Si une requête est associée à la cellule actuellement sélectionnée dans la feuille de calcul active, la requête associée dans la liste est sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Actualiser </p> </td> 
   <td colname="col2"> <p>Actualise une ou plusieurs requêtes sélectionnées. (Reportez-vous à la section <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Actualisation d’une requête</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Réactualiser la liste </p> </td> 
   <td colname="col2"> <p>Actualise toutes les requêtes affichées. Lorsque vous actualisez toutes les requêtes, la durée requise pour la mise à jour des informations du serveur dans votre rapport est directement proportionnelle à la complexité des requêtes du rapport. L’actualisation de toutes les requêtes peut prendre plusieurs minutes pour les rapports volumineux. C’est pourquoi il peut s’avérer judicieux d’actualiser les requêtes les plus urgentes individuellement, puis de sélectionner l’option <span class="wintitle">Actualiser tout</span> ultérieurement, à un moment moins crucial. </p> <p> <p>Remarque : si vous actualisez une feuille de calcul contenant de nombreuses requêtes, il est conseillé de vérifier régulièrement les résultats dans le <span class="wintitle">Gestionnaire de requêtes</span>. En cas d’échec d’une requête, vous pouvez remonter à la source de l’erreur à l’aide du message d’erreur qui s’affiche dans la colonne de diagnostic. Gardez à l’esprit, toutefois, que si un message d’erreur s’affiche généralement en cas d’échec d’une requête, il arrive aussi qu’aucun message d’erreur ne soit généré. Vous remarquerez peut-être qu’une actualisation ne met pas à jour les données d’une cellule contenant une référence ou qu’une mise à jour supprime les données de la cellule. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

