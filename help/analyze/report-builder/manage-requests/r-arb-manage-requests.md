---
description: Description des champs de gestion des requêtes dans le Créateur de rapports.
seo-description: Description des champs de gestion des requêtes dans le Créateur de rapports.
seo-title: Gérer les requêtes - définitions
solution: Analytics
title: Gérer les requêtes - définitions
topic: Créateur de rapports
uuid: 01 b 21 d 0 e-c 870-4 df 8-95 b 9-f 4 aef 1 f 4 d 16 b
translation-type: tm+mt
source-git-commit: 6a70b32b576cc7b5b6a6f0037d98e35b3f8c1426

---


# Gérer les requêtes - définitions

Description des champs de gestion des requêtes dans le Créateur de rapports.

## Aperçu {#section_75C288C945FA4781A4EDF806711A5660}

Le [!UICONTROL Gestionnaire de requêtes] présente une vue détaillée de l’état de toutes les requêtes générées pour toutes les feuilles ou pour une seule feuille du classeur actif. Il permet également d’ajouter, de modifier, d’actualiser et de supprimer une requête (fonctions généralement associées à l’[!UICONTROL Assistant Requête] et au [!UICONTROL Gestionnaire de requêtes]) en cliquant avec le bouton droit sur l’une des cellules disponibles de la feuille de calcul Excel qui contient les requêtes précédentes.

The [!UICONTROL Request Manager] displays when you click **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) in the Report Builder toolbar.

>[!NOTE]
>
>Le créateur de rapports Adobe applique uniquement les dépendances de requêtes dans la même feuille de calcul, et non dans les feuilles de calcul. Ceci garantit la rapidité de l’exécution.

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
   <td colname="col1"> <p>Report Suite </p> </td> 
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
   <td colname="col2"> <p>Affiche la boîte de dialogue Assistant Requête. Reportez-vous à la section <a href="../../../analyze/report-builder/data-requests/t-create-a-data-request.md#task_65B453C8F015429A8EA73A1B64025B6C" type="task" format="dita" scope="local"> Créer une requête de données</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifier </p> </td> 
   <td colname="col2"> <p> (ou Modifier plusieurs) Modifie une requête sélectionnée. Le système affiche la boîte de dialogue <span class="wintitle">Assistant Requête</span>. See <a href="../../../analyze/report-builder/manage-requests/t-edit-multiple-requests.md#task_70A13DBE43CD4BBEBE1B62459ADB3AD1" type="task" format="dita" scope="local"> Edit Multiple Requests</a>. </p> </td> 
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
   <td colname="col2"> <p>Actualise une ou plusieurs requêtes sélectionnées. (Reportez-vous à la section <a href="../../../analyze/report-builder/manage-requests/t-refresh-a-request.md#task_96556DB051A2479A955999D3837EE609" type="task" format="dita" scope="local"> Actualisation d’une requête</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Réactualiser la liste </p> </td> 
   <td colname="col2"> <p>Actualise toutes les requêtes affichées. Lorsque vous actualisez toutes les requêtes, la durée requise pour la mise à jour des informations du serveur dans votre rapport est directement proportionnelle à la complexité des requêtes du rapport. L’actualisation de toutes les requêtes peut prendre plusieurs minutes pour les rapports volumineux. C’est pourquoi il peut s’avérer judicieux d’actualiser les requêtes les plus urgentes individuellement, puis de sélectionner l’option <span class="wintitle">Actualiser tout</span> ultérieurement, à un moment moins crucial. </p> <p> <p>Remarque : si vous actualisez une feuille de calcul contenant de nombreuses requêtes, il est conseillé de vérifier régulièrement les résultats dans le <span class="wintitle">Gestionnaire de requêtes</span>. En cas d’échec d’une requête, vous pouvez remonter à la source de l’erreur à l’aide du message d’erreur qui s’affiche dans la colonne de diagnostic. Gardez à l’esprit, toutefois, que si un message d’erreur s’affiche généralement en cas d’échec d’une requête, il arrive aussi qu’aucun message d’erreur ne soit généré. Vous remarquerez peut-être qu’une actualisation ne met pas à jour les données d’une cellule contenant une référence ou qu’une mise à jour supprime les données de la cellule. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

