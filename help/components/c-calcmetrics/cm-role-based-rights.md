---
description: Les droits des mesures calculées diffèrent entre les utilisateurs administrateur et non administrateur.
seo-description: Les droits des mesures calculées diffèrent entre les utilisateurs administrateur et non administrateur.
seo-title: Droits basés sur les rôles calculés
title: Droits basés sur les rôles calculés
uuid: 7 c 14 d 32 d -370 c -4 afa -8 f 80-5 bbd 8 fc 12 ec 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Mesures calculées : droits basés sur un rôle

Les droits des mesures calculées diffèrent entre les utilisateurs administrateur et non administrateur.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> Créez     </th> 
   <th colname="col2" class="entry"> Partager </th> 
   <th colname="col3" class="entry"> Afficher/Gérer </th> 
   <th colname="col4" class="entry"> Approuver </th> 
   <th colname="col5" class="entry"> Appliquer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Administrateurs</b> </td> 
   <td colname="col02"> Les administrateurs peuvent créer des mesures calculées ainsi que des <a href="https://marketing.adobe.com/resources/help/en_US/reference/groups.html" format="https" scope="external">groupes</a> pour limiter les droits de création de mesures calculées des utilisateurs. </td> 
   <td colname="col2"> Peuvent effectuer un partage avec l’ensemble de l’entreprise, avec des groupes d’utilisateurs et avec des utilisateurs individuels. </td> 
   <td colname="col3"> <span class="keyword"> [! UICONTROL Reports &amp; Analytics] </span>: Peut afficher/modifier/supprimer etc. leurs propres mesures calculées et celles des autres utilisateurs. <p> <span class="keyword"> Ad Hoc Analysis</span> et <span class="keyword">Report Builder</span> : peuvent afficher/modifier/supprimer, etc. leurs propres mesures calculées et celles partagées avec eux. </p> </td> 
   <td colname="col4"> Peuvent approuver les mesures calculées comme étant canoniques. </td> 
   <td colname="col5"> Peuvent appliquer toute mesure calculée à l’échelle de l’entreprise. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Utilisateurs non administrateur</b> </td> 
   <td colname="col02"> Par défaut, les utilisateurs peuvent créer des mesures calculées. Ces droits peuvent être toutefois limités par les administrateurs. </td> 
   <td colname="col2"> Peuvent effectuer un partage avec des utilisateurs individuels uniquement. </td> 
   <td colname="col3"> Peuvent afficher/modifier/supprimer, etc. uniquement leurs propres mesures calculées. <p>Les utilisateurs non administrateurs doivent avoir accès à tous les événements de composant pour pouvoir visualiser des mesures partagées (les autorisations de la Admin Console sont toujours appliquées). </p> <p>Si un tableau de bord ou un rapport planifié est partagé avec un utilisateur non administrateur et que la mesure n’est pas partagée avec les utilisateurs non administrateurs, le rapport s’exécute avec la mesure appliquée (en présumant qu’ils disposent des autorisations de consultation des événements). Néanmoins, les utilisateurs non administrateurs ne pourront pas consulter la définition ou modifier la mesure. </p> </td> 
   <td colname="col4"> Ne peuvent utiliser que les mesures calculées approuvées ; ne peuvent pas les marquer comme approuvées. </td> 
   <td colname="col5"> Peuvent appliquer leurs propres mesures calculées et les segments qui ont été partagés avec eux. </td> 
  </tr> 
 </tbody> 
</table>

