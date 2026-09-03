---
description: Découvrez la description des champs de la section Gestion des requêtes dans Report Builder.
title: Gestion des requêtes dans Report Builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
feature: Report Builder
role: User, Admin
exl-id: fd8c0145-4c7e-4f07-aa63-656a8a20724c
TQID: https://experienceleague.adobe.com/ZAVAW4NN9WCHCdj-ZPXDOflV4oC0-WPbClzkdlrf3JM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 563
ht-degree: 27%

---

# Gestion des requêtes - Définitions

{{legacy-arb}}

Affichez les détails du statut d’une demande et utilisez la description des champs pour gérer les demandes dans Report Builder.

## Vue d’ensemble {#section_75C288C945FA4781A4EDF806711A5660}

Le [!UICONTROL Gestionnaire de requêtes] fournit une vue détaillée du statut de toutes les requêtes que vous avez créées pour toutes les feuilles ou pour une seule feuille du classeur actif. Vous pouvez également ajouter, modifier, actualiser et supprimer une requête. Ces fonctions sont généralement associées à l’[!UICONTROL Assistant Requête] et au [!UICONTROL Gestionnaire de requêtes] lorsque vous cliquez avec le bouton droit sur une cellule disponible dans la feuille de calcul Excel qui contient les requêtes précédentes.

Le [!UICONTROL Gestionnaire de requêtes] s’affiche lorsque vous cliquez sur le ![](assets/edit_request.gif) **[!UICONTROL Gérer]** de la barre d’outils de Report Builder.

>[!NOTE]
>
>Adobe Report Builder applique les dépendances de requête uniquement dans la même feuille de calcul, et non entre les feuilles de calcul. Le fait de se limiter aux dépendances dans une seule feuille de calcul garantit la rapidité d’exécution.

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
   <td colname="col2"> <p>Affiche les demandes de toutes les feuilles du classeur actif. Pour afficher les demandes provenant de feuilles spécifiques, désactivez cette option. Vous devez, dans ce cas, cliquer sur un onglet Feuille au bas du rapport Excel afin d’afficher les requêtes associées à cette feuille dans le <span class="wintitle">Gestionnaire de requêtes</span>. Le libellé en regard de la case à cocher indique quelle feuille du classeur est actuellement sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feuille </p> </td> 
   <td colname="col2"> <p>Affiche le nom des feuilles du classeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Suite de rapports </p> </td> 
   <td colname="col2"> <p>Affiche le nom de la suite de rapports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Période </p> </td> 
   <td colname="col2"> <p>Affiche la période spécifiée du rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Granularité </p> </td> 
   <td colname="col2"> <p>Indique la granularité de la requête. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dernière exécution </p> </td> 
   <td colname="col2"> <p>Précise la date de la dernière exécution de la requête par le Report Builder. Un message de diagnostic s’affiche également dans ce tableau dans la colonne <span class="wintitle">Dernière exécution</span>, le cas échéant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ajouter </p> </td> 
   <td colname="col2"> <p>Affiche la boîte de dialogue Assistant Requête. Voir <a href="/help/analyze/legacy-report-builder/data-requests/t-create-a-data-request.md"   > Créer une demande de données</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifier </p> </td> 
   <td colname="col2"> <p> (Ou Modifier plusieurs) Modifie une requête sélectionnée. Le système affiche la boîte de dialogue <span class="wintitle">Assistant Requête</span>. Consultez la section <a href="/help/analyze/legacy-report-builder/manage-requests/t-edit-multiple-requests.md"   >Modification de plusieurs requêtes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Supprimer </p> </td> 
   <td colname="col2"> <p>Supprime les requêtes. Vous pouvez supprimer plusieurs requêtes sélectionnées. Vous pouvez également supprimer une requête dans la liste en la sélectionnant et en appuyant sur Supprimer sur votre clavier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Sélectionner tout </p> </td> 
   <td colname="col2"> <p>Sélectionnez toutes les requêtes. Le <span class="wintitle">Gestionnaire de requêtes</span> affiche le nombre de requêtes sélectionnées au bas de la liste de requêtes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Depuis la cellule </p> </td> 
   <td colname="col2"> <p>Obtient les données d'une requête à partir de la feuille de calcul. Si une demande est associée à la cellule actuellement sélectionnée dans la feuille de calcul active, la demande associée dans la liste est sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Actualiser </p> </td> 
   <td colname="col2"> <p>Actualise une seule demande ou une sélection de demandes. (Voir <a href="/help/analyze/legacy-report-builder/manage-requests/t-refresh-a-request.md"   > une demande</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualiser la liste </p> </td> 
   <td colname="col2"> <p>Actualise toutes les requêtes affichées. Lorsque vous actualisez toutes les requêtes, le temps nécessaire pour mettre à jour les informations du serveur dans votre rapport est directement proportionnel à la complexité des requêtes dans le rapport. Pour les rapports très volumineux, l’actualisation de toutes les requêtes peut prendre plusieurs minutes. C’est pourquoi il peut s’avérer judicieux de mettre à jour les demandes les plus urgentes individuellement, puis de sélectionner l’option <span class="wintitle">Actualiser tout</span> ultérieurement, à un moment moins crucial. </p> <p> <p>Remarque : si vous actualisez une feuille de calcul contenant de nombreuses requêtes, il est conseillé de vérifier régulièrement les résultats dans le <span class="wintitle">Gestionnaire de requêtes</span>. En cas d’échec de la requête, le message d’erreur de la colonne de diagnostic vous aide à identifier la source de l’erreur. Bien que dans la plupart des cas un message d’erreur s’affiche lorsqu’une requête échoue, notez qu’aucun message d’erreur n’est parfois généré. Vous remarquerez peut-être qu'une actualisation ne met pas à jour les données d'une cellule contenant une référence, ou qu'une mise à jour supprime les données de la cellule. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
