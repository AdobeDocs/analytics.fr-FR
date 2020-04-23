---
description: Le rapport Liens présente les liens trouvés sur la page active. Il ne rend pas compte de tous les liens collectés pour cette page.
title: Rapport sur les liens
topic: Activity map
uuid: 1e7ca5d8-d144-4a21-a2f9-e05bd3232c59
translation-type: tm+mt
source-git-commit: 6b27755178d156b1eaf159640d466bd84659983d

---


# Rapport sur les liens

Le rapport Liens présente les liens trouvés sur la page active. Il ne rend pas compte de tous les liens collectés pour cette page.

Le rapport Liens de la page   un tabulaire des liens. Il peut arriver que vous souhaitiez voir les clics sur les liens (ou d’autres mesures) classés dans un seul  de. Cela vous permet de mieux comparer un lien à un autre. Créez le rapport Liens de la page, y compris un classé de tous les liens de la page (par ID de lien), des informations sur les clics (# et %) et de la région de la page. Cliquez sur le bouton de rapport Liens de la page dans la barre d’outils de  de carte du .

The **[!UICONTROL Links On Page]** report opens below the browser frame in the Activity Map dashboard.

## Mode standard {#section_C8D2A1C07A2A4E3A8F84AC9240603FA7}

![](assets/links_in_page.png)

En mode standard, le rapport &quot;Liens de la page&quot; affiche des données de lien allant d’un seul jour à plusieurs jours, regroupées sur toute la période. Les informations suivantes s’affichent pour chaque lien :

<table id="table_3DE41B2CFA644B70AF802A3123CE51D9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Colonne </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Classement </td> 
   <td colname="col2"> Classement dans la page. En mode standard, la valeur de classement reste la même, quelle que soit la colonne sur laquelle vous cliquez. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de lien </td> 
   <td colname="col2">The link's primary ID (for more information on how primary ID is defined by the <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md">New Link Tracking Methodology</a>) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clics </td> 
   <td colname="col2"> Nombre de clics bruts pour un lien spécifié et pourcentage du nombre total de clics sur la page. Si l’utilisateur choisit une mesure différente dans la barre d’outils, le rapport Lien crée un rapport sur cette mesure à la place. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Région </td> 
   <td colname="col2"> Représente la région de la page où se trouve le lien. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilité </td> 
   <td colname="col2">Se rapporte à l’état de visibilité du lien. Deux valeurs sont possibles : 
    <ul id="ul_BABCC0F64145407C9D439150A6898E6D">
     <li id="li_9AF0479BDCEB4A44A37292FAABFA83A5"><b>Masqué</b>: le lien se trouve actuellement dans la page mais n'est pas visible pour l'utilisateur final (comme un sous-menu dans un menu de navigation qui devient visible uniquement si l'utilisateur passe sa souris sur le menu parent). </li>
     <li id="li_C6FA4EC27EDD4341AB9821E2B4BC9E60"><b>Affiché</b>: le lien est actuellement affiché sur la page. Il peut toutefois être affiché sous le pli : l’utilisateur doit faire défiler la page pour la voir. </li>
    </ul><p>Remarque : Si un lien est défini sur « Masqué », aucune superposition ne s’affichera pour celui-ci. </p></td> 
  </tr> 
 </tbody> 
</table>

**Filtrage des données**

When you want to zero in on a specific link, you can search for a related term in the **[!UICONTROL Filter Data]** field. Seuls les liens qui correspondent à la recherche auront des superpositions. Sans filtre, les recouvrements spécifiés dans les paramètres [de  de](/help/analyze/activity-map/activitymap-overlay-settings.md) s’affichent.

## Mode réel {#section_AC1967217B5A4532ACB01D33636F6770}

En mode réel, le rapport Liens sur la page affiche les données de tendance sur plusieurs minutes.

![](assets/links_on_page.png)

<table id="table_61D1FB0F02894055A1AB394DE4FE4742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Colonne </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Classement </td> 
   <td colname="col2"> Classement dans la page. Dans le cas d’une superposition en dégradé ou en bulle, la valeur de classement reste la même, quelle que soit la colonne sur laquelle vous cliquez. Dans le cas d’une superposition gagnants/perdants, cette valeur de classement change en fonction des liens qui ont le plus gagné/perdu. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de lien </td> 
   <td colname="col2">ID principal du lien. For more information on how the primary ID is defined by the New <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md"> Link Tracking Methodology</a>. </td>
  </tr> 
  <tr> 
   <td colname="col1"> Clics sur des liens </td> 
   <td colname="col2"> Nombre total de clics pour la période sélectionnée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % Modifier </td> 
   <td colname="col2"> % de changement entre les mesures de lien de la période actuelle et les mesures de lien de la période précédente. Les % de changement négatifs sont affichés en rouge, les % positifs en vert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tendance </td> 
   <td colname="col2"> Graphique linéaire pour toutes les périodes collectées. La période sélectionnée est indiquée par un marqueur vert. La période actuellement survolée est indiquée par un marqueur rouge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Région </td> 
   <td colname="col2"> Représente la région de la page où se trouve le lien. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilité </td> 
   <td colname="col2">Se rapporte à l’état de visibilité du lien. Deux valeurs sont possibles : 
    <ul id="ul_B10C55ED4D3C4CF99506DC467E2E7CFB">
     <li id="li_EA646722A51041CC9E62C56DEF92C81F">Masqué : est actuellement dans la page mais ne vous est pas visible (par exemple, tout lien qui s’affiche après le chargement de la page). </li>
     <li id="li_F9543614C2894003AC9984A7404E2785">Affiché : est actuellement affiché sur la page. Il peut toutefois être affiché sous le pli : vous devrez faire défiler la page pour la voir. </li>
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Tri et filtrage {#section_4B8E8233C21247CAA70DAEC2156548AD}

Il arrive que vous deviez analyser uniquement les résultats d’une zone de page spécifique (panneau de gauche, par exemple) pour décider de l’organisation du contenu de cette zone spécifique de la page Web.

À cette fin, nous avons créé une fonctionnalité de tri et de filtrage pour les liens dans le rapport Liens de la page. Le filtrage est disponible par le biais du champ de filtre et le terme de recherche sera appliqué à la colonne ID de lien et à la colonne Région du lien. Le tri est disponible en cliquant sur les appels (Classement, ID de lien, Clics, Changement au fil du temps, Région, Visibilité) et il peut être croissant et décroissant. Les superpositions disparaissent du site Web lorsque les liens sont filtrés à partir du rapport Liens de la page.
