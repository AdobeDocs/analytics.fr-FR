---
description: Tous les segments créés dans le Créateur de segments ne sont pas compatibles avec Data Warehouse. Ce tableau répertorie les fonctions prises en charge.
title: Compatibilité des segments avec Data Warehouse
feature: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 100%

---

# Compatibilité des segments avec Data Warehouse

Tous les segments créés dans le Créateur de segments ne sont pas compatibles avec l’[!DNL Data Warehouse]. Ce tableau répertorie les fonctions prises en charge.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace, Reports &amp; Analytics </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>Exclure le conteneur</b> </td> 
   <td> Pris en charge à n’importe quel niveau </td> 
   <td> Pris en charge uniquement dans des cas spéciaux au niveau supérieur </td> 
  </tr> 
  <tr> 
   <td> <b>Segments séquentiels</b> </td> 
   <td> Pris en charge </td> 
   <td> Non pris en charge </td> 
  </tr> 
  <tr> 
   <td> <b>AND et OR peuvent être associés sans limites</b> </td> 
   <td> Pris en charge </td> 
   <td> Certaines limites. Voir *note* sous le tableau. </td> 
  </tr> 
  <tr> 
   <td> <b>Conteneurs imbriqués</b> </td> 
   <td> Pris en charge </td> 
   <td> Certaines limites (dont la portée doit diminuer, par exemple les visiteurs peuvent contenir des accès mais non l’inverse) </td> 
  </tr> 
  <tr> 
   <td> <b>Dimensions</b> </td> 
   <td>Faites glisser-déposer une dimension dans le champ <span class="uicontrol">Définitions</span> du Créateur de segments pour découvrir sa compatibilité avec les produits. Par exemple, ces dimensions ne sont prises en charge que dans Analysis Workspace, Reports &amp; Analytics : 
    <ul> 
     <li>Serveur d’accès </li> 
     <li>Catégorie d’accès </li> 
     <li>Date d’accès </li> 
     <li>Classement de toutes les pages de recherche </li> 
    </ul> </td> 
   <td> Faites glisser-déposer une dimension dans le champ <span class="uicontrol">Définitions</span> du Créateur de segments pour découvrir sa compatibilité avec les produits. Par exemple, les dimensions suivantes ne sont prises en charge que dans Data Warehouse : 
    <ul> 
     <li>Adresse IP </li> 
     <li>URL de la page </li> 
     <li>Identifiant visiteur </li> 
     <li>Identifiant visiteur Experience Cloud </li> 
    </ul> <p>Il <b>n’est pas</b> possible d’utiliser les dimensions ci-après dans les segments de Data Warehouse : </p> 
    <ul> 
     <li>Classement de toutes les pages de recherche </li> 
     <li>Matin/après-midi </li> 
     <li>Jour du mois </li> 
     <li>Jour de la semaine </li> 
     <li>Jour de l’année </li> 
     <li>Unité opérationnelle d’entrée </li> 
     <li>Entrée (toutes les dimensions commençant avec l’entrée, à l’exception de la page d’accès) </li> 
     <li>Sortie (toutes les dimensions commençant avec la sortie, à l’exception de Lien de sortie et Page de sortie) </li> 
     <li>Hiérarchie (toutes les dimensions commençant avec la hiérarchie) </li> 
     <li>Profondeur d’accès </li> 
     <li>Type d’accès </li> 
     <li>Heure Jour </li> 
     <li>Mois de l’année </li> 
     <li>Pages introuvables </li> 
     <li>Recherche payante </li> 
     <li>Trimestre de l’année </li> 
     <li>Fréquence des retours </li> 
     <li>Visites sur une seule page </li> 
     <li>Durée avant événement </li> 
     <li>Durée de consultation de la page – Regroupement </li> 
     <li>Durée par visite – Regroupement </li> 
     <li>Suivi du motif d’exclusion </li> 
     <li>États américains </li> 
     <li>Jour ouvrable/week-end </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>Empilement de segments</b> </td> 
   <td> Pris en charge </td> 
   <td> Pris en charge </td> 
  </tr>
  <tr>
    <td><b>Opérateurs « Est égal à n’importe lequel » et « N’est égal à aucun »</b></td>
    <td>Pris en charge</td>
    <td>Non pris en charge</td>
  </tr>
 </tbody> 
</table>

*Remarque : Data Warehouse ne prend pas en charge tous les cas d’utilisation d’un conteneur `exclusion` ou `without` lors de l’utilisation de `AND/OR`. Lors de l’utilisation d’une telle combinaison, seuls les segments qui peuvent être réécrits en tant que `A AND NOT B` (ou **inclure cette caractéristique** et **exclure cette caractéristique**) sont pris en charge dans Data Warehouse.*
