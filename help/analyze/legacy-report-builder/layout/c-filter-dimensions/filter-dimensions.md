---
description: Vous pouvez filtrer les dimensions que vous ajoutez à la grille Libellés de lignes. Les filtres permettent de limiter les données renvoyées par les requêtes. Ils peuvent être appliqués à partir des dispositions croisées dynamiques ou personnalisées. Lorsque vous configurez le filtrage des dimensions à partir de la Disposition croisée dynamique, vous pouvez, en outre, préciser le nombre d’entrées de la cellule.
title: Dimensions du filtre - Aperçu
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: User, Admin
exl-id: eded07d5-3c06-419b-92fd-1a48856ac293
source-git-commit: e09234ca27fbf923e026aa1f2ed0ebfed636bf7c
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 73%

---

# Dimensions du filtre - Aperçu

{{legacy-arb}}

Vous pouvez filtrer les dimensions que vous ajoutez à la grille Libellés de lignes. Les filtres permettent de limiter les données renvoyées par les requêtes. Ils peuvent être appliqués à partir des dispositions croisées dynamiques ou personnalisées. Lorsque vous configurez le filtrage des dimensions à partir de la Disposition croisée dynamique, vous pouvez, en outre, préciser le nombre d’entrées de la cellule.

Le formulaire de filtrage sélectionné est renseigné en fonction de l’élément et de la mesure sélectionnés dans la requête Report Builder.

## Définition d’un filtre - Valeurs et caractères spéciaux {#section_15840216A4044C40974945FAA435AD93}

Des informations sur les filtres dont accessibles dans le panneau **[!UICONTROL Filtre le plus populaire]** > **[!UICONTROL Définir un filtre]**.

![Capture d’écran montrant la boîte de dialogue Définir un filtre avec des options pour filtrer par application, utilisateur et projet.](/help/admin/tools/assets/filter.png)

Les tableaux suivants contiennent des exemples et des informations sur les filtres :

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filtre </th> 
   <th colname="col02" class="entry"> Description </th> 
   <th colname="col2" class="entry"> Exemple de filtre </th> 
   <th colname="col3" class="entry"> Résultats de la correspondance </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Contient tous les termes </p> </td> 
   <td colname="col02"> <p>Contient tous les valeurs délimitées par des espaces dans n’importe quel ordre. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Correspond <span class="term"> a b c</span>et <span class="term"> b a c</span>, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contient n’importe quel terme </p> </td> 
   <td colname="col02"> <p>Contient au moins l’un des filtres (délimités par des espaces). </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>Correspond <span class="term"> A1</span>, <span class="term"> B2</span>, <span class="term"> C3</span>, mais pas <span class="term"> D4</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contient l’expression </p> </td> 
   <td colname="col02"> <p>Contient le filtre de recherche et éventuellement d’autres termes. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Correspond <span class="term"> abc</span> et <span class="term"> abc def</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ne contient aucun terme </p> </td> 
   <td colname="col02"> <p>Renvoie n’importe quel résultat, à moins que vous ne saisissiez une valeur. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Correspond à <span class="term"> d e f</span> mais pas <span class="term"> c d e f</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ne contient pas l’expression </p> </td> 
   <td colname="col02"> <p>Renvoie toutes les valeurs qui ne contiennent pas votre expression. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Exclut <span class="term"> abc</span>, <span class="term"> abc def</span> et correspond <span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Est égal à </p> </td> 
   <td colname="col02"> <p>Renvoie une correspondance exacte. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> est renvoyé, et rien d’autre. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>N’est pas égal à </p> </td> 
   <td colname="col02"> <p>Renvoie n’importe quel résultat qui ne correspond pas exactement à votre saisie. </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>Ne correspond pas <span class="term"> a</span>. </p> <p>Correspond à <span class="term"> a b c</span>. </p> <p>Correspond à <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Commence par </p> </td> 
   <td colname="col02"> <p>Renvoie des résultats qui commencent par une valeur spécifique. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Correspond <span class="term"> abcd</span> mais pas <span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se termine par </p> </td> 
   <td colname="col02"> <p>Renvoie des résultats qui se terminent par une valeur spécifique. </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>Correspond à <span class="term">wxyz</span>, mais pas à <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avancé (caractères spéciaux) </p> </td> 
   <td colname="col02"> <p>Vous permet d’utiliser les caractères suivants : </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Page*Accueil$" | sports </p> </td> 
   <td colname="col3"> <p> Cet exemple définit un filtre qui commence par <span class="term"> Accueil</span> puis recherche zéro ou plusieurs caractères et se termine par <span class="term"> Page</span>. </p> <p>Aussi, n’importe quelle page contenant <span class="term"> sport</span>. </p> <p>Quelques exemples de correspondance : </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">PageAccueil </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Page et (autres caractères) Accueil </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Page sports </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">sports Accueil </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">sports </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz sports abc </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_8BBB06C8860745DEA41B39673699DC0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caractères spéciaux </th> 
   <th colname="col2" class="entry"> Rôle </th> 
   <th colname="col3" class="entry"> Remarques </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> « » </td> 
   <td colname="col2"> Est égal à </td> 
   <td colname="col3"> <p>N’est pas ignoré sauf s’il n’est pas accompagné d’un autre guillemet double. Par exemple, <span class="term">’affichage de 17 pouces</span> n’est pas une expression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> Caractère générique </td> 
   <td colname="col3"> <p>Identique à l’astérisque utilisé dans les expressions régulières. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ^ </td> 
   <td colname="col2"> Commence par </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> $ </td> 
   <td colname="col2"> Se termine par </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> Pas </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> OU </td> 
   <td colname="col3"> <p>Pris en charge uniquement dans le filtre <span class="term"> avancé (caractères spéciaux)</span> </p> </td> 
  </tr> 
 </tbody> 
</table>
