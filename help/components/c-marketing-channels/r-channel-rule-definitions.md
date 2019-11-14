---
description: Ce tableau de référence définit les champs, options et attributs de visite que vous pouvez sélectionner sur la page Règles de traitement des canaux marketing.
solution: Analytics
subtopic: Marketing channels
title: Règles de traitement des canaux marketing - Définitions
topic: Reports and analytics
uuid: 4e71ff5b-912a-4dc0-9c22-4be74c5e3cc0
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Règles de traitement des canaux marketing - Définitions

Ce tableau de référence définit les champs, options et attributs de visite que vous pouvez sélectionner sur la page Règles de traitement des canaux marketing.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Terme </p> </th> 
   <th colname="col2" class="entry"> <p>Définition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tous </p> </td> 
   <td colname="col2"> <p>N’active ce canal que lorsque toutes les règles de la règles numérotée sont vraies. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quelconque </p> </td> 
   <td colname="col2"> <p>Active ce canal lorsque l’une des règles de l’ensemble de règles est vraie. Cette option n’est disponible que s’il existe plusieurs règles dans la règle numérotée. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID AMO </p> </td> 
   <td colname="col2"> <p>Code de suivi principal utilisé par les intégrations Advertising Cloud et Advertising Analytics. Lorsque l’une de ces intégrations est activée, le préfixe du code de suivi peut être utilisé pour identifier les canaux spécifiques à Advertising Cloud. Utilisez "AMO ID" commence par "AL" pour la recherche, "AC" pour l’affichage ou "AO" pour Social. Lorsque l’ID d’OMA est utilisé dans les canaux marketing, les mesures de clic/coût/impression peuvent être attribuées au canal approprié (lorsqu’elles ne sont pas configurées, elles sont alors définies sur Direct ou Aucun). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID AMO ED </p> </td> 
   <td colname="col2"> <p>Code de suivi secondaire utilisé par Advertising Cloud. Le principal objectif de ce code de suivi est de servir de clé pour renvoyer les données vers Ad Cloud. Il peut toutefois également être utilisé pour identifier les clics publicitaires par rapport aux affichages publicitaires si vous souhaitez les voir comme deux canaux marketing distincts. Pour ce faire, définissez la logique du canal marketing pour "AMO EF ID" se termine par ":d" pour les clics publicitaires ou "AMO EF ID" se termine par ":i" pour les affichages publicitaires. Si vous ne souhaitez pas diviser l’affichage en deux canaux, utilisez plutôt la dimension d’identifiant AMO. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variables de conversion </p> </td> 
   <td colname="col2"> <p>Comprend des variables eVar activées pour cette suite de rapports et ne s’applique que lorsque ces variables sont définies au moyen du code Adobe sur la page. </p> <p>Consultez le <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/oms_sc_implement.pdf"  >Guide d’implémentation </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Existe </p> </td> 
   <td colname="col2"> <p>Plusieurs sélections sont disponibles, notamment : </p> <p> 
     <ul id="ul_FE39B5F36235441FB757CC73CA2C4F51"> 
      <li id="li_6DC09918D69B443091AB94DB773D5189"> <p> <span class="uicontrol">N’existe pas</span> : indique que l’attribut de visite n’existe pas pour la demande. Dans un domaine référent par exemple, si l’utilisateur saisit une URL ou clique sur un signet, l’attribut de domaine référent n’existe pas. </p> </li> 
      <li id="li_3AB958F997974682824E85014CA266D6"> <p> <span class="uicontrol"> Est vide</span> : indique que l’attribut de visite existe, généralement sous la forme d’un paramètre de chaîne de requête ou eVar, mais qu’aucune valeur associée à l’attribut de visite n’est attribuée. </p> </li> 
      <li id="li_25EDA39748D141BA8173CC4C41035ABA"> <p> <span class="uicontrol"> Ne contient pas </span>: Vous permet, par exemple, de spécifier qu’un domaine référent ne contient pas de valeur spécifique (contrairement à l’utilisation de la sélection <span class="term"> Contient </span>. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifier le canal comme </p> </td> 
   <td colname="col2"> <p>Associe la règle à un canal marketing ajouté à la page <span class="wintitle">Gestionnaire de canaux marketing</span>. </p> <p>See <a href="/help/components/c-marketing-channels/c-channels.md"   > Add marketing channels </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fait correspondre les règles de détection des recherches payées </p> </td> 
   <td colname="col2"> <p>Une recherche payante détectée par Adobe. Lors des recherches payantes, les sociétés paient une somme au moteur de recherche pour répertorier leur site. Les recherches payantes figurent habituellement en haut ou à droite des résultats de la recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fait correspondre les règles de détection des recherches naturelles </p> </td> 
   <td colname="col2"> <p>Une recherche non payante détectée par Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le référent correspond aux filtres d’URL internes </p> </td> 
   <td colname="col2"> <p> Une visite dont l’URL de page correspond à un filtre d’URL interne, tel qu’il est défini pour la suite de rapports dans les Outils d’administration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le référent ne correspond pas aux filtres d’URL internes </p> </td> 
   <td colname="col2"> <p>L’URL référente ne correspond pas à un filtre d’URL interne, tel qu’il est défini pour la suite de rapports dans les Outils d’administration. Vous pouvez utiliser ce paramètre avec <span class="term"> Page URL </span> and <span class="term"> Exists </span> to set up a catch-all rule, so that no visits land in the <a href="/help/components/c-marketing-channels/c-faq.md#no-channel-identified" > No Channel Identified </a> section of the report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ignorer les visites correspondant aux filtres URL internes </p> </td> 
   <td colname="col2"> <p>(Pour les référents) Effectue uniquement le suivi des visites provenant de sites externes. En règle générale, ce paramètre doit rester activé, à moins que vous ne souhaitiez inclure le trafic interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Est la première page de la visite </p> </td> 
   <td colname="col2"> <p>La première page d’une visite détectée par Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Activity Map </p> </td> 
   <td colname="col2"> <p>nom de page d’une page Web de votre site qui est balisée à l’aide de la balise Web d’Adobe. This value is equivalent to <span class="varname"> s.pageName </span>. Par exemple, <span class="varname"> Page d’accueil </span> et <span class="varname"> Qui sommes-nous </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine de page </p> </td> 
   <td colname="col2"> <p>Le domaine de la page à laquelle accède le visiteur, tel que <span class="filepath">produits.exemple.co.uk </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine et chemin de page </p> </td> 
   <td colname="col2"> <p>Domaine et chemin d’accès, comme par exemple <span class="filepath">products.example.co.uk/mens/pants/overview.html </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine racine de page (TLD+1) </p> </td> 
   <td colname="col2"> <p>Domaine racine de la page à laquelle accède le visiteur, tel que <span class="filepath">exemple.co.uk </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL de la page </p> </td> 
   <td colname="col2"> <p>L’URL d’une page Web de votre site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine référent </p> </td> 
   <td colname="col2"> <p>Le domaine d’où proviennent les visiteurs avant de visiter votre site ; par exemple, les référents provenant de <span class="filepath">abcsite.com</span> par rapport à <span class="filepath">xyzsite.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paramètre de chaîne de requête </p> </td> 
   <td colname="col2"> <p>If a page URL on your site looks like <span class="filepath"> https://example.com/?page=12345&amp;cat=1 </span>, then page and cat are both query string parameters. (See <span class="filepath"> https://en.wikipedia.org/wiki/Query_string </span>.) </p> <p>Vous ne pouvez spécifier qu’un seul paramètre de chaîne de requête par ensemble de règles. Pour ajouter des paramètres de chaîne de requête supplémentaires, utilisez <span class="uicontrol">ANY</span> comme opérateur, puis ajoutez les nouveaux paramètres de chaîne de requête à la règle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Référent </p> </td> 
   <td colname="col2"> <p>L’emplacement de la page Web (adresse URL complète) sur laquelle vos visiteurs se trouvaient avant de consulter votre site. Il existe un référent en dehors de votre domaine défini. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine et chemin référents </p> </td> 
   <td colname="col2"> <p>Une concaténation de « Domaine référent » et « Chemin d’accès à l’URL ». Par exemple : </p> <p> <span class="filepath"> www.example.com/products/id/12345 </span> </p> <p> <span class="filepath"> ad.example.com/foo </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paramètre de référent </p> </td> 
   <td colname="col2"> <p>Un paramètre de chaîne de requête sur l’URL de renvoi. Par exemple, si vos visiteurs proviennent de <span class="filepath">exemple.com/?page=12345&amp;cat=1</span>, alors « page » et « cat » sont les paramètres référents. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine racine référent </p> </td> 
   <td colname="col2"> <p>Le domaine racine du référent. Il existe un référent en dehors de votre domaine défini. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Moteur de recherche </p> </td> 
   <td colname="col2"> <p>Moteur de recherche, tel que Google ou Yahoo!, qui a dirigé les visiteurs sur votre site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mots-clés de recherche </p> </td> 
   <td colname="col2"> <p>Mot utilisé dans une recherche en utilisant un moteur de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Moteur de recherche - Mots-clés </p> </td> 
   <td colname="col2"> <p>Une concaténation de « Mot-clé de recherche » et de « Moteur de recherche » pour identifier avec exactitude le moteur de recherche. Par exemple, si vous cherchez le mot « ordinateur », le moteur de recherche et le mot-clé sont identifiés comme suit : </p> 
    <code>
      Search&nbsp;Tracking&nbsp;Code&nbsp;= &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"&lt;search_type&gt;:&lt;search&nbsp;engine&gt;:&lt;search&nbsp;keyword&gt;"&nbsp;where &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;search_type&nbsp;=&nbsp;"n"&nbsp;or&nbsp;"p",&nbsp;search_engine&nbsp;=&nbsp;"Google",&nbsp;and&nbsp;search_keyword&nbsp;= &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"computer" 
    </code> <p><b></b> Remarque : n = naturelle; p = payé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Définir la valeur du canal comme </p> </td> 
   <td colname="col2"> <p>Outre le fait de savoir quel canal marketing conduit un visiteur sur votre site, vous pouvez savoir quelle bannière publicitaire, quel mot-clé de recherche ou quelle campagne par courriel du canal reçoit le crédit de l’activité d’un visiteur sur le site. Cet identifiant est une valeur de canal enregistrée avec le canal. Cette valeur correspond le plus souvent à un identifiant de campagne intégré dans la page d’entrée ou dans l’URL de renvoi ; dans d’autres cas, c’est la combinaison du moteur de recherche et du mot-clé de recherche, ou encore l’URL de renvoi, qui identifient avec le plus de précision le visiteur en provenance d’un canal donné. </p> </td> 
  </tr> 
 </tbody> 
</table>
