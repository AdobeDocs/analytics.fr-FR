---
description: Le tableau ci-après montre les rapports associés aux variables utilisées pour les renseigner dans Analytics.
keywords: Analytics Implementation
title: Mappage des rapports vers la variable
topic: Developer and implementation
uuid: fd81f97d-dd1a-47d5-9157-b7932fe13490
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mappage des rapports vers la variable

Le tableau ci-après montre les rapports associés aux variables utilisées pour les renseigner dans Analytics.

Chaque variables est répertoriée avec les rapports qui l’utilise.

<table id="table_16443E46AC0E46509F8533D26EDE1BCC"> 
 <thead> 
  <tr> 
   <th class="entry"> Variable </th> 
   <th class="entry"> Rapports renseignés </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> s.pageName </td> 
   <td> <p>Rapports de conversion &gt; Rapports Chemin &gt; Valeur de la page </p> <p>Rapports de conversion &gt; Rapports Chemin &gt; Page d’entrée </p> <p>Rapports de conversion &gt; Rapports Chemin &gt; Pages d’entrée originales </p> <p>Rapports sur le trafic &gt; Trafic du site &gt; Pages vues </p> <p>Rapports sur le trafic &gt; Trafic du site &gt; Visiteurs uniques par heure </p> <p>Rapports sur le trafic &gt; Trafic du site &gt; Visiteurs uniques par jour </p> <p>Rapports sur le trafic &gt; Trafic du site &gt; Visiteurs uniques par mois </p> <p>Rapports sur le trafic &gt; Trafic du site &gt; Visiteurs uniques par an </p> <p>Rapports sur le trafic &gt; Profil du visiteur &gt; Pages vues par visiteurs clés </p> <p>Rapports sur le trafic &gt; Segmentation &gt; Pages les plus populaires </p> <p>Rapports Chemin &gt; Pages &gt; Résumé pour la page </p> <p>Rapports Chemin &gt; Pages &gt; Valeur de la page </p> <p>Rapports Chemin &gt; Pages &gt; Pages les plus populaires </p> <p>Rapports Chemin &gt; Pages &gt; Actualisations </p> <p>Rapports Chemin &gt; Pages &gt; Clics jusqu’à la page </p> <p>Rapports Chemin &gt; Pages &gt; Durée de consultation de la page </p> <p>Rapports Chemin &gt; Entrées et sorties &gt; Pages d’entrée </p> <p>Rapports Chemin &gt; Entrées et sorties &gt; Pages de sortie </p> <p>Rapports Chemin &gt; Entrées et sorties &gt; Liens de sortie </p> <p>Rapports Chemin &gt; Chemins complets &gt; Chemins complets </p> <p>Rapports Chemin &gt; Chemins complets &gt; Chemins les plus longs </p> <p>Rapports Chemin &gt; Chemins complets &gt; Longueur de chemin </p> <p>Rapports Chemin &gt; Chemins complets &gt; Durée de la visite </p> <p>Rapports Chemin &gt; Chemins complets &gt; Visites mono-page </p> <p>Rapports Chemin &gt; Analyse avancée &gt; Page précédente </p> <p>Rapports Chemin &gt; Analyse avancée &gt; Page suivante </p> <p>Rapports Chemin &gt; Analyse avancée &gt; Flux de page précédente </p> <p>Rapports Chemin &gt; Analyse avancée &gt; Flux de page suivante </p> <p>Rapports Chemin &gt; Analyse avancée &gt; PathFinder </p> <p>Rapports Chemin &gt; Analyse avancée &gt; Abandons </p> <p> <b>Remarque :</b> Dans tous les rapports sur le <span class="wintitle">trafic</span> répertoriés ci-dessus (à l’exception du rapport <span class="wintitle">Pages les plus populaires</span>), lorsque la variable <span class="wintitle">s.pageName</span> n’est pas définie, l’URL est utilisée. </p> </td> 
  </tr> 
  <tr> 
   <td> s.server </td> 
   <td> Rapports sur le trafic &gt; Segmentation &gt; Serveurs les plus populaires </td> 
  </tr> 
  <tr> 
   <td> s.pageType </td> 
   <td> Rapports Chemin &gt; Pages &gt; Pages introuvables </td> 
  </tr> 
  <tr> 
   <td> s.channel </td> 
   <td> <p>Rapports de conversion &gt; Chemin du site &gt; Section du site </p> <p>Rapports sur le trafic &gt; Segmentation &gt; Sections du site les plus populaires </p> </td> 
  </tr> 
  <tr> 
   <td> s.prop1 - s.prop20 </td> 
   <td> Rapports sur le trafic &gt; Aperçu personnalisé &gt; Aperçu personnalisé 1 à 20 </td> 
  </tr> 
  <tr> 
   <td> s.campaign </td> 
   <td> <p>Rapports de conversion &gt; Campagnes &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Campagnes &gt; Code de suivi </p> </td> 
  </tr> 
  <tr> 
   <td> s.state </td> 
   <td> Rapports de conversion &gt; Profil du visiteur &gt; Etats </td> 
  </tr> 
  <tr> 
   <td> s.zip </td> 
   <td> Rapports de conversion &gt; Profil du visiteur &gt; Codes postaux </td> 
  </tr> 
  <tr> 
   <td> s.events </td> 
   <td> <p>Rapports de conversion &gt; Achats &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Achats &gt; Recettes </p> <p>Rapports de conversion &gt; Achats &gt; Commandes </p> <p>Rapports de conversion &gt; Achats &gt; Unités </p> <p>Rapports de conversion &gt; Panier &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Panier &gt; Paniers </p> <p>Rapports de conversion &gt; Panier &gt; Consultations du panier </p> <p>Rapports de conversion &gt; Panier &gt; Ajouts au panier </p> <p>Rapports de conversion &gt; Panier &gt; Retraits du panier </p> <p>Rapports de conversion &gt; Panier &gt; Passage en caisse </p> <p>Conversion Reports &gt; Evénements personnalisés &gt; Evénement personnalisé 1 à 20 </p> <p>Rapports de conversion &gt; Produits &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Produits &gt; Vente croisée </p> <p>Rapports de conversion &gt; Produits &gt; Catégories </p> <p>Rapports de conversion &gt; Campagnes &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Fidélité de la clientèle &gt; Fidélité de la clientèle </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Jours avant le premier achat </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Jours depuis le dernier achat </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Nombre de visites </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Clients quotidiens uniques </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Clients mensuels uniques </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Clients annuels uniques </p> <p>Rapports de conversion &gt; Chemin du site &gt; Valeur de la page </p> </td> 
  </tr> 
  <tr> 
   <td> s.products </td> 
   <td> <p>Rapports de conversion &gt; Achats &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Achats &gt; Recettes </p> <p>Rapports de conversion &gt; Achats &gt; Commandes </p> <p>Rapports de conversion &gt; Achats &gt; Unités </p> <p>Rapports de conversion &gt; Panier &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Produits &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Produits &gt; Vente croisée </p> <p>Rapports de conversion &gt; Produits &gt; Catégories </p> <p>Rapports de conversion &gt; Campagnes &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Fidélité de la clientèle &gt; Fidélité de la clientèle </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Jours avant le premier achat </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Jours depuis le dernier achat </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Nombre de visites </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Clients quotidiens uniques </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Clients mensuels uniques </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Clients annuels uniques </p> <p>Rapports de conversion &gt; Chemin du site &gt; Valeur de la page </p> </td> 
  </tr> 
  <tr> 
   <td> s.purchaseID </td> 
   <td> <p>Rapports de conversion &gt; Achats &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Achats &gt; Recettes </p> <p>Rapports de conversion &gt; Achats &gt; Commandes </p> <p>Rapports de conversion &gt; Achats &gt; Unités </p> <p>Rapports de conversion &gt; Panier &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Produits &gt; Conversion et moyennes </p> <p>Rapports de conversion &gt; Produits &gt; Vente croisée </p> <p>Rapports de conversion &gt; Fidélité de la clientèle &gt; Fidélité de la clientèle </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Jours avant le premier achat </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Jours depuis le dernier achat </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Nombre de visites </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Clients quotidiens uniques </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Clients mensuels uniques </p> <p>Rapports de conversion &gt; Cycle de ventes &gt; Clients annuels uniques </p> <p>Rapports de conversion &gt; Chemin du site &gt; Valeur de la page </p> </td> 
  </tr> 
  <tr> 
   <td> s.eVar1-s.eVar20 </td> 
   <td> Rapports de conversion &gt; Variables personnalisées &gt; eVar personnalisée 1 à 20 </td> 
  </tr> 
  <tr> 
   <td> s.linkName </td> 
   <td> Rapports sur le trafic &gt; Aperçu personnalisé &gt; Liens personnalisés </td> 
  </tr> 
  <tr> 
   <td> s.hier1 - s.hier5 </td> 
   <td> Rapports sur le trafic &gt; Hiérarchies &gt; Hiérarchie 1 à 5 </td> 
  </tr> 
 </tbody> 
</table>

