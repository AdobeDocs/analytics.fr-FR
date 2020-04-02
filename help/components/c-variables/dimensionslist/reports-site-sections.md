---
description: Indique les zones de votre site qui sont les plus consultées par les utilisateurs. Les sections du site peuvent inclure des groupes de produits, similaires aux catégories que vous définissez. Vous pouvez, par exemple, définir un groupe de pages Caméras, un groupe Ordinateurs, etc. Les données relatives au rapport Sections du site de conversion sont importées du rapport Section du site dans le groupe Trafic, lequel reçoit ses informations de la variable de canal dans le code de suivi. Utilisez ce rapport pour identifier le plus grand impact sur les statistiques du site des éléments de différentes sections.
title: Sections du site
topic: Reports
uuid: 6839c566-f88f-4979-9cf5-52a77c0b0416
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sections du site

Indique les zones de votre site qui sont les plus consultées par les utilisateurs. Les sections du site peuvent inclure des groupes de produits, similaires aux catégories que vous définissez. Vous pouvez, par exemple, définir un groupe de pages Caméras, un groupe Ordinateurs, etc. Les données relatives au rapport Sections du site de conversion sont importées du rapport Section du site dans le groupe Trafic, lequel reçoit ses informations de la variable de canal dans le code de suivi. Utilisez ce rapport pour identifier le plus grand impact sur les statistiques du site des éléments de différentes sections.

* Ce rapport fait directement référence à des données de la variable [s.channel](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_channel.html) implémentée sur votre site web.
* Ce rapport peut être visualisé sous la forme d’un rapport de tendance ou avec classement.
* Ce rapport peut utiliser un filtre de recherche afin de localiser des éléments spécifiques.
* Vous pouvez utiliser des classifications dans ce rapport afin de renommer et de consolider des éléments.
* Vous pouvez créer des corrélations avec n’importe quelle autre variable de trafic au moyen des outils d’administration.
* Ce rapport peut utiliser les mesures suivantes :

   * **Pages vues** : nombre de fois où la variable [pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_pagename.html) ou l’URL a été définie (configurée comme mesure par défaut).

   * **Toutes les mesures de cheminement** : Visites, Profondeur moyenne de page, Durée de consultation moyenne de la page, Entrées, Sorties, Actualisations et Accès unique.
   * En fonction des paramètres de votre suite de rapports et de votre entreprise : les mesures Visiteurs uniques par jour, par semaine, par mois et par trimestre peuvent être activées sur ce rapport.
   * **Toutes les variables de commerce électronique standard** : Recettes, Commandes, Unités, Paniers, Consultations du panier, Passages en caisse, Ajouts au panier, Retraits du panier.
   * **Tous les événements personnalisés** : Événements 1-80, et Événements 81-100 si le code est H22 ou supérieur.

Tous les événements de conversion du [!UICONTROL rapport Sections du site] utilisent la dernière affectation. La conversion est divisée entre les pages de votre implémentation qui ne contiennent pas d’événements de succès. Il s’agit d’une différence comparé au  [rapport Pages](/help/components/c-variables/dimensionslist/reports-pages.md) qui utilise l’allocation linéaire.

**Informations propres au produit**

<table id="table_525FDF95C8ED4BF2A1E25BE2DA971EFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Interface </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reports &amp; Analytics </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Contenu du site</span> &gt; <span class="uicontrol">Sections du site</span> </p> <p>Outre les corrélations, ce rapport peut utiliser les ventilations suivantes : </p> 
    <ul id="ul_9CD009D89B134C53807332E3C88D3C44"> 
     <li id="li_566417EB074D425C9A1F4FB28AA7FAB4"> 
      <ul id="ul_3795C7AAE6DA4B7E96FCDC7F3211DFBB"> 
       <li id="li_50B295E961724CFB83D222DE9B4C7FF2">Tout rapport classifié sur la base de ce rapport </li> 
       <li id="li_697682892D8841BC8120BEC0E1AE9753"> <span class="wintitle"> Rapport Codes de suivi</span> </li> 
       <li id="li_F6D893FCBA7A4B3EB04715833CA41022"> Rapports <span class="wintitle">Produits</span> et <span class="wintitle">Catégories</span> </li> 
       <li id="li_9F379E61DB4F4753AE1FFFC8F9C17347"> <span class="wintitle"> Rapport de fidélité de la clientèle</span> </li> 
       <li id="li_64A6A06F9265410ABB425DA4AF50C440">Toute variable de conversion complètement sous-liée </li> 
       <li id="li_907DDFCC35AB48EEA5B169B4A2598FB1"> <span class="wintitle"> Canaux marketing Première touche et Dernière touche</span> </li> 
       <li id="li_B08A0DCB40154152AF1033B7629A5B5A"> Rapport <span class="uicontrol">Target</span> &gt; <span class="uicontrol">Campagnes</span> (s’il est activé) </li> 
       <li id="li_6D4E65DD6E2B49C9A8C12181D23F185A">Durée de la visite </li> 
       <li id="li_C6D3AD5A534243A8A6E17C663FEBA6BA">Sections du site </li> 
       <li id="li_E1F46EED5CE2425D83200A2FCB686EE5">Pages d’entrée </li> 
       <li id="li_1201EE0EBF13476C9A9525E0700F30F3">La plupart des rapports de source de trafic </li> 
       <li id="li_563E07858FB1473BB22C2B191E8BE620">Nombre de visites </li> 
       <li id="li_1CAD77ABA6A2454282A4DA7E88C047E8">De nombreux rapports de profil du visiteur </li> 
       <li id="li_D3A04E4CD8EC4646AAB90BF19F0AFA8A">Toutes les variables de conversion et variables de liste </li> 
       <li id="li_01C194CE0F3E4C0694A34B4C6697F385">Visites, Visiteurs uniques par jour, Visiteurs uniques par semaine, Visiteurs uniques par mois, Visiteurs uniques par trimestre et Visiteurs paramétrés uniques sont disponibles. </li> 
      </ul> </li> 
    </ul> <p>Ce rapport peut utiliser des segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Hoc Analysis </td> 
   <td colname="col2"> 
    <ul id="ul_DFF9BFC01FC1424B8905C2D2C0EFD156"> 
     <li id="li_65FDF1C165C84F729E0EE84FF671B5E4">Les Ad Hoc Analysis permettent de ventiler le rapport Sections du site selon pratiquement tous les autres rapports de l’interface du rapport marketing. </li> 
     <li id="li_2159DE10C52D40AA89E4C934FC184641">Outre tous les événements susmentionnés, elle peut utiliser l’ensemble des mesures de conversion et de trafic, ainsi qu’une affectation différente pour toutes les mesures de conversion. </li> 
     <li id="li_3A23C6286D314B5D814612469F4F77C5">Ce rapport peut utiliser plusieurs segments très avancés. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

