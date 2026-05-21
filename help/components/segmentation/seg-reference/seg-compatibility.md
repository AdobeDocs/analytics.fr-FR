---
description: Comprenez pourquoi tous les segments créés dans le créateur de segments ne sont pas compatibles avec Data Warehouse. Découvrez les fonctions prises en charge.
title: Compatibilité des segments avec Data Warehouse
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 80%

---

# Compatibilité des segments avec l’entrepôt de données

Tous les segments créés dans le créateur de segments ne sont pas compatibles avec [!DNL Data Warehouse]. Ce tableau répertorie les fonctions prises en charge.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace, Reports &amp; Analytics </th> 
   <th> Entrepôt de données </th> 
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
   <td>Faites glisser et déposez une dimension dans le champ Définitions de <span class="uicontrol"> du créateur de segments </span> pour en savoir plus sur la compatibilité de ses produits. Par exemple, ces dimensions ne sont prises en charge que dans Analysis Workspace, Reports &amp; Analytics : 
    <ul> 
     <li>Serveur d’accès </li> 
     <li>Catégorie d’accès </li> 
     <li>Date d’accès </li> 
     <li>Classement de toutes les pages de recherche </li> 
    </ul> </td> 
   <td> Faites glisser et déposez une dimension dans le champ Définitions de <span class="uicontrol"> du créateur de segments </span> pour en savoir plus sur la compatibilité de ses produits. Par exemple, les dimensions suivantes ne sont prises en charge que dans Data Warehouse : 
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
     <li>Jour de l'heure </li> 
     <li>Mois de l’année </li> 
     <li>Pages introuvables </li> 
     <li>Référencement payant </li> 
     <li>Trimestre de l’année </li> 
     <li>Fréquence des retours </li> 
     <li>Visites de page unique </li> 
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
