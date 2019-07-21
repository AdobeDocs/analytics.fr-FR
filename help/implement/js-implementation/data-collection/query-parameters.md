---
description: Vous trouverez, dans le tableau ci-dessous, les paramètres de requête contenant la valeur de chaque variable d’analyse envoyée à la collecte de données.
keywords: Mise en œuvre d’Analytics
seo-description: Vous trouverez, dans le tableau ci-dessous, les paramètres de requête contenant la valeur de chaque variable d’analyse envoyée à la collecte de données.
seo-title: Paramètres de requête de collecte de données
solution: Analytics
title: Paramètres de requête de collecte de données
topic: Développeur et mise en œuvre
uuid: 4 d 5 af 486-df 27-42 fe-bb 9 c -28938 dddf 2 b 2
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Paramètres de requête de collecte de données

Vous trouverez, dans le tableau ci-dessous, les paramètres de requête contenant la valeur de chaque variable d’analyse envoyée à la collecte de données.

Ces informations peuvent être utilisées lors d’opérations de débogage réalisées à l’aide de [Moniteurs de paquets](../../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258), lors de la création manuelle de demandes d'image ou lors de l'utilisation [de variables dynamiques](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262).

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> Paramètre </th> 
   <th class="entry"> Variable Analytics </th> 
   <th class="entry"> Rapport rempli </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> Aucune </td> 
   <td colname="col3"> Aucune </td> 
   <td colname="col4"> Conseil relatif à l’emplacement d’Audience Manager (utilisé dans l’intégration du profil partagé d’Experience Cloud) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> Aucune </td> 
   <td colname="col3"> Aucune </td> 
   <td colname="col4"> Audience Manager Blob (utilisé dans l’intégration du profil partagé d’Experience Cloud) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> Aucune </td> 
   <td colname="col3"> Aucun </td> 
   <td colname="col4"> Identifiant visiteur Analytics </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> Aucune </td> 
   <td> Aucun </td> 
   <td> Indique le début d’une demande d’image. </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> Aucune </td> 
   <td> Aucun </td> 
   <td> Indique la fin d’une demande d’image, ce qui signifie que la demande n’a pas été tronquée. </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> Aucune </td> 
   <td> Profil du visiteur | Technologie | Hauteur du navigateur </td> 
   <td> Hauteur de la fenêtre du navigateur (en pixels) </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> Aucune </td> 
   <td> Profil du visiteur | Technologie | Largeur du navigateur </td> 
   <td> Largeur de la fenêtre du navigateur (en pixels) </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> Aucune </td> 
   <td> Profil du visiteur | Technologie | Profondeurs de couleur du moniteur </td> 
   <td> Qualité des couleurs (en bits) </td> 
  </tr> 
  <tr> 
   <td> <code> c. <span class="varname"> [key] </code></span> </td> 
   <td> <p>s.contextData </p> </td> 
   <td> <p>Aucun </p> </td> 
   <td> <p>Les paires clé-valeur sont indiquées dans l’un des formats suivants : </p> <p> <code> &lt;my.a&gt;red&lt;/my.a&gt; </code> </p> <p>ou : </p> <p> <code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code> </p> <p>Chacun de ces exemples génère une valeur de données contextuelles <code>my.a = red </code>. Plusieurs paires clé-valeur peuvent être spécifiées. </p> <p>In the query string, this context data variable would appear as <code> c.&amp;my.a=red </code> </p> </td> 
  </tr> 
  <tr> 
   <td> c1 - c75 </td> 
   <td> s.prop1 - s.prop75 </td> 
   <td> Tous les rapports de trafic personnalisés </td> 
   <td> Variables de trafic utilisées pour générer des rapports de trafic personnalisé </td> 
  </tr> 
  <tr> 
   <td> cc </td> 
   <td> s.currencyCode </td> 
   <td> Aucun </td> 
   <td> Type de devise utilisée sur le site </td> 
  </tr> 
  <tr> 
   <td> cdp </td> 
   <td> s.cookieDomainPeriods </td> 
   <td> Aucun </td> 
   <td> Indique le nombre de périodes dans un domaine pour le suivi des cookies. Paramètre défini manuellement. </td> 
  </tr> 
  <tr> 
   <td> ce </td> 
   <td> s.charSet </td> 
   <td> Aucun </td> 
   <td> Codage de caractères de la demande d’image </td> 
  </tr> 
  <tr> 
   <td> cl </td> 
   <td> s.cookieLifetime (durée de vie, en secondes, du cookie s_vi) </td> 
   <td> Aucun </td> 
   <td> Durée de vie du cookie visiteur. </td> 
  </tr> 
  <tr> 
   <td> ch </td> 
   <td> s.channel </td> 
   <td> Contenu du site | Sections du site </td> 
   <td> Variable Sections du site utilisées pour générer des rapports sur le trafic </td> 
  </tr> 
  <tr> 
   <td> cp </td> 
   <td> Type d’accès </td> 
   <td> Type d’accès </td> 
   <td> Indique si le comportement est le résultat du premier plan d’interaction directe ou d’informations que l’appareil envoie sans arrière-plan d’interaction directe. </td> 
  </tr> 
  <tr> 
   <td> ct </td> 
   <td> Aucune </td> 
   <td> Profil du visiteur | Technologie | Types de connexion </td> 
   <td> Type de connexion (modem, LAN, etc. ; ne peut être rempli que dans les navigateurs IE) </td> 
  </tr> 
  <tr> 
   <td> <code> D </code> </td> 
   <td> dynamicVariablePrefix </td> 
   <td> Aucun </td> 
   <td> <p>Voir <a href="../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262" format="dita" scope="local"> Variables dynamiques </a>. </p> </td> 
  </tr> 
  <tr> 
   <td> events ou ev </td> 
   <td> s.events </td> 
   <td> Trafic du site | Achats, panier, événements personnalisés </td> 
   <td> Événements commerciaux et personnalisés, qui se sont produits dans la page. Paramètre utilisé dans les rapports de conversion. </td> 
  </tr> 
  <tr> 
   <td> g </td> 
   <td> Aucune </td> 
   <td> Aucun </td> 
   <td> URL de la page active jusqu’à 255 octets </td> 
  </tr> 
  <tr> 
   <td> -g </td> 
   <td> Aucune </td> 
   <td> Aucun </td> 
   <td> Les URL de plus de 255 octets sont fractionnées, les 255 premiers octets apparaissant dans le paramètre g=, les autres apparaissant plus tard dans la chaîne de requête, dans le paramètre de requête -g=.  </td> 
  </tr> 
  <tr> 
   <td> h1 - h5 </td> 
   <td> s.hier1 - s.hier5 </td> 
   <td> Contenu du site | Rapports hiérarchiques </td> 
   <td> Variables de hiérarchie, utilisées pour la génération de rapports de trafic </td> 
  </tr> 
  <tr> 
   <td> hp </td> 
   <td> Aucune </td> 
   <td> Profil du visiteur | Page d’accueil des visiteurs </td> 
   <td> Indique si la page active est la page d’accueil du navigateur (Y ou N ; ce paramètre n’est renseigné que dans les navigateurs IE). </td> 
  </tr> 
  <tr> 
   <td> j </td> 
   <td> Aucune </td> 
   <td> Profil du visiteur | Technologie | Version Javascript </td> 
   <td> Affiche la version Javascript actuelle installée (en général, 1.x). </td> 
  </tr> 
  <tr> 
   <td> k </td> 
   <td> Aucune </td> 
   <td> Profil du visiteur | Technologie | Cookies </td> 
   <td> Prise en charge des cookies dans le navigateur (O, N ou I) </td> 
  </tr> 
  <tr> 
   <td> l1-l3 </td> 
   <td> s.list1-s.list3 </td> 
   <td> Conversion personnalisée </td> 
   <td> Liste délimitée de valeurs transmises à une variable, puis signalées comme lignes individuelles pour la création de rapports. </td> 
  </tr> 
  <tr> 
   <td> mid </td> 
   <td> Aucune </td> 
   <td> Aucune </td> 
   <td> Identifiant visiteur Experience Cloud </td> 
  </tr> 
  <tr> 
   <td> ndh </td> 
   <td> Aucune </td> 
   <td> Aucun </td> 
   <td> Indique si la demande d’image provient d’un fichier JS (1 ou 0). </td> 
  </tr> 
  <tr> 
   <td> ns </td> 
   <td> s.visitorNameSpace </td> 
   <td> Aucun </td> 
   <td> Spécifie le domaine dans lequel les cookies sont définis. </td> 
  </tr> 
  <tr> 
   <td> oid </td> 
   <td> s.objectID </td> 
   <td> Contenu du site | Liens | ClickMap </td> 
   <td> Identificateur d’objet de la dernière page, utilisé dans ClickMap </td> 
  </tr> 
  <tr> 
   <td> ot </td> 
   <td> Aucune </td> 
   <td> Contenu du site | Liens | ClickMap </td> 
   <td> Nom de la balise d’objet de la dernière page, utilisé dans ClickMap </td> 
  </tr> 
  <tr> 
   <td> p </td> 
   <td> Aucune </td> 
   <td> Profil du visiteur | Technologie | Modules externes Netscape </td> 
   <td> Noms de module externe du navigateur séparés par des points virgules </td> 
  </tr> 
  <tr> 
   <td> pageName (ou gn) </td> 
   <td> s.pageName </td> 
   <td> Contenu du site | Pages </td> 
   <td> Nom désigné de la page lors pour la génération de rapports </td> 
  </tr> 
  <tr> 
   <td> pageType (ou gt) </td> 
   <td> s.pageType </td> 
   <td> Contenu du site | Pages introuvables </td> 
   <td> Indique s’il s’agit d’une page 404 ou non (page d’erreur ou page vide). </td> 
  </tr> 
  <tr> 
   <td> pccr </td> 
   <td> Aucune </td> 
   <td> Aucun </td> 
   <td> Ne se produit que pour les nouveaux visiteurs. Empêche les redirections infinies (toujours true). </td> 
  </tr> 
  <tr> 
   <td> pe </td> 
   <td> s.linkType </td> 
   <td> Contenu du site | Liens | Liens de sortie, téléchargement de fichiers, liens personnalisés </td> 
   <td> Détermine le type de correspondance de lien personnalisé déclenché. </td> 
  </tr> 
  <tr> 
   <td> pev1 </td> 
   <td> Aucune </td> 
   <td> Contenu du site | Liens | Liens de sortie, téléchargement de fichiers, liens personnalisés </td> 
   <td> URL affichée lorsque vous avez cliqué sur le lien personnalisé </td> 
  </tr> 
  <tr> 
   <td> pev2 </td> 
   <td> Aucune </td> 
   <td> Contenu du site | Liens | Liens de sortie, téléchargement de fichiers, liens personnalisés </td> 
   <td> Nom convivial du lien personnalisé </td> 
  </tr> 
  <tr> 
   <td> pev3 </td> 
   <td> Aucune </td> 
   <td> Tous les rapports vidéo </td> 
   <td> Permet de suivre les jalons pour la génération de rapports de vidéo propriétaire. Ce paramètre a été abandonné avec la version 15. </td> 
  </tr> 
  <tr> 
   <td> pf </td> 
   <td> Aucun </td> 
   <td> Aucune </td> 
   <td> Concerne uniquement Adobe. Ne pas modifier. </td> 
  </tr> 
  <tr> 
   <td> pid </td> 
   <td> Aucune </td> 
   <td> Contenu du site | Liens | ClickMap </td> 
   <td> Identificateur de page de la dernière page, utilisé dans ClickMap </td> 
  </tr> 
  <tr> 
   <td> pidt </td> 
   <td> Aucune </td> 
   <td> Contenu du site | Liens | ClickMap </td> 
   <td> Type d’identificateur de page de la dernière page, utilisé dans ClickMap </td> 
  </tr> 
  <tr> 
   <td> products (ou pl) </td> 
   <td> s.products. </td> 
   <td> Produits | Produits </td> 
   <td> Variable de produits utilisée pour la variable Produits, utilisée pour la génération de rapports de conversion </td> 
  </tr> 
  <tr> 
   <td> purchaseID (ou pi) </td> 
   <td> s.purchaseID </td> 
   <td> Aucun </td> 
   <td> Permet de supprimer les achats en double, pour empêcher l’inflation des recettes. </td> 
  </tr> 
  <tr> 
   <td> r </td> 
   <td> s.referrer </td> 
   <td> Tous les rapports de source de trafic </td> 
   <td> URL de référence </td> 
  </tr> 
  <tr> 
   <td> s </td> 
   <td> Aucune </td> 
   <td> Profil du visiteur | Technologie | Résolutions du moniteur </td> 
   <td> Résolution d’écran (largeur x hauteur) </td> 
  </tr> 
  <tr> 
   <td> server (ou sv) </td> 
   <td> s.server </td> 
   <td> Contenu du site | Serveurs </td> 
   <td> Serveur de la page, utilisé pour la génération de rapports de trafic </td> 
  </tr> 
  <tr> 
   <td> state </td> 
   <td> s.state </td> 
   <td> Profil du visiteur | État du visiteur </td> 
   <td> Spécifie l’état tel que défini par la variable. </td> 
  </tr> 
  <tr> 
   <td> t </td> 
   <td> (automatique, envoyé avec chaque accès ne comportant pas d’horodatage personnalisé) </td> 
   <td> Aucun </td> 
   <td> <p>Le paramètre <code>t</code> est au format suivant : </p> 
    <code>dd/mm/aaaa &amp; amp ; nbsp ; hh : mm : ss &amp; amp ; nbsp ; D &amp; amp ; nbsp ; OFFSET </code>
  <p>Où D est un chiffre compris entre <code>0 et 6</code> qui indique le jour de la semaine et où <code>OFFSET</code> représente : </p> 
    <code>offset &amp; amp ; nbsp ; from &amp; amp ; nbsp ; GMT &amp; amp ; nbsp ; in &amp; amp ; nbsp ; heures et amp ; nbsp ; * &amp; amp ; nbsp ; 60 &amp; amp ; nbsp ; * &amp; amp ; nbsp ; -&amp; amp ; nbsp ; 1 </code>
  <p> Par exemple : </p> 
    <code>23/09/2016 &amp; amp ; nbsp ; 14:00:00 &amp; amp ; nbsp ; 1 &amp; amp ; nbsp ; 420 </code>
  </td> 
  </tr> 
  <tr> 
   <td> <code> ts </code> </td> 
   <td> <p>timestamp </p> </td> 
   <td> Aucun </td> 
   <td> <p>L’horodatage personnalisé calculé et envoyé avec l’accès. Généralement utilisé pour le suivi hors ligne. </p> </td> 
  </tr> 
  <tr> 
   <td> v </td> 
   <td> Aucune </td> 
   <td> Profil du visiteur | Technologie | Java </td> 
   <td> Java activé (« Y » pour oui, « N » pour non) </td> 
  </tr> 
  <tr> 
   <td> v0 </td> 
   <td> s.campaign </td> 
   <td> Campagne | Codes de suivi </td> 
   <td> Variable de campagne, utilisée pour la génération de rapports de conversion </td> 
  </tr> 
  <tr> 
   <td> v1 - v75 </td> 
   <td> s.eVar1-s.eVar75 </td> 
   <td> Tous les rapports de conversion personnalisés </td> 
   <td> Variables de conversion, utilisées pour la génération de rapports de conversion personnalisés </td> 
  </tr> 
  <tr> 
   <td> vid </td> 
   <td> <p>s.visitorID </p> </td> 
   <td> Aucun </td> 
   <td> ID unique du visiteur   tel que défini dans la variable Identifiant visiteur. </td> 
  </tr> 
  <tr> 
   <td> vmk </td> 
   <td> s.vmk </td> 
   <td> Aucun </td> 
   <td> Clé de migration des visiteurs, utilisée pour la migration de cookies tiers vers des cookies de premier niveau. Déconseillé. </td> 
  </tr> 
  <tr> 
   <td> vvp </td> 
   <td> s.variableProvider </td> 
   <td> Aucun </td> 
   <td> Utilisé pour l’intégration à Genesis </td> 
  </tr> 
  <tr> 
   <td> xact </td> 
   <td> s.transactionID </td> 
   <td> Aucun </td> 
   <td> ID transaction utilisé pour lier des données en ligne à des données hors ligne </td> 
  </tr> 
  <tr> 
   <td> zip </td> 
   <td> s.zip </td> 
   <td> Profil du visiteur | Code postal du visiteur </td> 
   <td> Détermine le code postal défini par la variable. </td> 
  </tr> 
  <tr> 
   <td> /5/ (pour le protocole mobile) ou /1/ (pour un autre protocole) dans l’URL de demande d’image. </td> 
   <td> Aucune </td> 
   <td> Aucun </td> 
   <td> <p> Contrôle l’ordre dans lequel les cookies et d’autres méthodes sont utilisés pour identifier les visiteurs. </p> </td> 
  </tr> 
 </tbody> 
</table>

