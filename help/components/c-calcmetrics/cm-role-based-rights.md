---
description: Les droits des mesures calculées diffèrent entre les utilisateurs administrateur et non administrateur.
title: 'Mesures calculées : droits en fonction du rôle'
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '251'
ht-degree: 100%

---

# Mesures calculées : droits en fonction du rôle

Les droits des mesures calculées diffèrent entre les utilisateurs administrateur et non administrateur.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> Créez </th> 
   <th colname="col2" class="entry"> Partager </th> 
   <th colname="col3" class="entry"> Consulter/Gérer </th> 
   <th colname="col4" class="entry"> Approuver </th> 
   <th colname="col5" class="entry"> Appliquer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Administrateurs</b> </td> 
   <td colname="col02"> Pour limiter les droits de création de mesures calculées des utilisateurs, les administrateurs peuvent créer des mesures calculées ainsi que des profils de produits dans lʼAdmin Console. </td> 
   <td colname="col2"> Peuvent effectuer un partage avec l’ensemble de l’entreprise, avec des groupes d’utilisateurs et avec des utilisateurs individuels. </td> 
   <td colname="col3"> <span class="keyword"> Reports &amp; Analytics</span> : peuvent afficher/modifier/supprimer, etc. leurs propres mesures calculées et celles des autres utilisateurs. <p> <span class="keyword"> Report Builder </span> : peut, entre autres, consulter, modifier ou supprimer ses propres mesures calculées et celles partagées avec lui. </p> </td> 
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
