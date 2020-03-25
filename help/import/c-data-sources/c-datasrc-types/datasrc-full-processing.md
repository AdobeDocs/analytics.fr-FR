---
description: Les variables suivantes sont prises en charge lors du traitement des données sous forme d’un appel de serveur standard (Générique > Traitement complet).
subtopic: Data sources
title: Traitement complet
topic: Developer and implementation
uuid: 590ae89c-6e17-453b-b701-ce1adbea6fa4
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Traitement complet

Les variables suivantes sont prises en charge lors du traitement des données sous forme d’un appel de serveur standard (Générique > Traitement complet).

Les sources de données à traitement complet sont traitées comme si elles étaient reçues par les serveurs Adobe au moment spécifié (chaque correspondance comprend un horodatage).

* [Profil du visiteur](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_6065627D0C144506965F562C80AE67F8)
* [Référence de colonne](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_92BAE76639E3404E97276B1BE0581078)

## Profil du visiteur {#section_6065627D0C144506965F562C80AE67F8}

Les sources de données à traitement complet sont traitées en utilisant les profils du visiteur distincts, de sorte que même si l’identifiant visiteur dans les données transférées correspond aux données collectées à l’aide d’une bibliothèque JavaScript ou AppMeasurement, les profils du visiteur ne sont pas connectés du point de vue de l’attribution des eVars.

Par exemple, un utilisateur avec un identifiant visiteur `"user@example.com"` se rend sur votre site à partir d’une campagne marketing nommée « Soldes de printemps », qui est stockée dans la variable de campagne. Si vous transférez par la suite une transaction à l’aide du même identifiant visiteur, la campagne « Soldes de printemps » n’est pas créditée pour les recettes ou les événements de succès transférés à l’aide de sources de données à traitement complet.

## Référence de colonne {#section_92BAE76639E3404E97276B1BE0581078}

<table id="table_AAC04491D643467B9C80FDEF88130B13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable JavaScript </th> 
   <th colname="col2" class="entry"> Variable de colonne Traitement complet </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>campaign </p> </td> 
   <td colname="col2"> <p>campaign </p> </td> 
   <td colname="col3"> <p>Code de suivi de campagne de conversion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>marketing </p> </td> 
   <td colname="col2"> <p>marketing </p> </td> 
   <td colname="col3"> <p>Chaîne de canal (par exemple, section Sports). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>currencyCode </p> <p>Remarque : cette variable est également prise en charge par les sources de données standard sous forme de <code> currency code </code>. </p> </td> 
   <td colname="col3"> <p>Code de devise du revenu (par exemple, USD). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timestamp </p> </td> 
   <td colname="col2"> <p>date </p> </td> 
   <td colname="col3"> <p>Utilisez le format de date ISO 8601 <code> YYYY-MM-DDThh:mm:ss±UTC_offset </code> (par exemple, <code> 2013-09-01T12:00:00-07:00 </code>) ou le format d’heure Unix (nombre de secondes écoulées depuis le 1er janvier 1970). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar<i>N</i> </p> </td> 
   <td colname="col2"> <p>eVar<i>N</i>, c.-à-d. &lt;eVar2&gt;…&lt;/eVar2&gt; </p> </td> 
   <td colname="col3"> <p>Nom de la variable eVar de conversion. Vous pouvez avoir jusqu’à 75 eVars ( <span class="varname"> eVar1 </span> - <span class="varname"> eVar75 </span>). </p> <p>Vous pouvez définir le nom de l’eVar (eVar12) ou un nom convivial (Campagne publicitaire 3). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>events </p> </td> 
   <td colname="col2"> <p>events </p> </td> 
   <td colname="col3"> <p>Chaîne d’événements, formatée selon la même syntaxe que la variable <a href="https://docs.adobe.com/content/help/fr-FR/analytics/implementation/vars/page-vars/events/event-serialization.html"  >s.events</a>. </p> <p>Par exemple : </p> 
    <code>
      scAdd,event1,event7 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hier<i>N</i> </p> </td> 
   <td colname="col2"> <p>hier<i>N</i>, c.-à-d. &lt;hier2&gt;…&lt;/hier2&gt; </p> </td> 
   <td colname="col3"> <p>Nom de la hiérarchie. Vous pouvez avoir jusqu’à 5 hiérarchies ( <span class="varname"> hier1</span> - <span class="varname">hier5 </span>). </p> <p>Vous pouvez définir le nom de hiérarchie par défaut (<span class="varname">hier2</span>) ou un nom convivial (<span class="term">Yankees </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkName </p> </td> 
   <td colname="col2"> <p>linkName </p> </td> 
   <td colname="col3"> <p>Nom du lien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkType </p> </td> 
   <td colname="col2"> <p>linkType </p> </td> 
   <td colname="col3"> <p>Type de lien. Les valeurs acceptables sont : </p> 
    <ul id="ul_E441013055A9447AB6C3FB05B6099F7D"> 
     <li id="li_A33F66F30B60479284F72AE3AD4BF499"> <b>d</b> : lien de téléchargement </li> 
     <li id="li_182F695AA2D044DAB036BAFE38BC3915"> <b>e</b> : lien de sortie </li> 
     <li id="li_4FD4D542D1774607860BEF41C1B090D1"> <b>o</b> : lien personnalisé </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkURL </p> </td> 
   <td colname="col2"> <p>linkURL </p> </td> 
   <td colname="col3"> <p>HREF du lien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageName </p> </td> 
   <td colname="col2"> <p>pageName </p> </td> 
   <td colname="col3"> <p>Nom de page </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageType </p> </td> 
   <td colname="col2"> <p>pageType </p> </td> 
   <td colname="col3"> <p>Type de page (« Page d’erreur »). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageURL </p> </td> 
   <td colname="col2"> <p>pageURL </p> </td> 
   <td colname="col3"> <p>URL de la page (par exemple, <code>https://www.mysite.com/index.html)</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>products </p> </td> 
   <td colname="col2"> <p>products </p> </td> 
   <td colname="col3"> <p>Liste de produits (par exemple, <code> "Sports;Ball;1;5.95") </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prop1 - prop75 </p> </td> 
   <td colname="col2"> <p>prop<i>N</i>, c.-à-d. &lt;prop2&gt;…&lt;/prop2&gt; </p> </td> 
   <td colname="col3"> <p>Chaîne du numéro de propriété (par exemple, <span class="term"> section Sports </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchaseID </p> </td> 
   <td colname="col2"> <p>purchaseID </p> </td> 
   <td colname="col3"> <p>ID d’achat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>s_account </p> </td> 
   <td colname="col2"> <p>reportSuiteID </p> </td> 
   <td colname="col3"> <p>ID de la suite de rapports auquel attribuer la correspondance. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server </p> </td> 
   <td colname="col2"> <p>server </p> </td> 
   <td colname="col3"> <p>Chaîne du serveur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>state </p> </td> 
   <td colname="col2"> <p>state </p> </td> 
   <td colname="col3"> <p>Chaîne d’état de conversion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zip </p> </td> 
   <td colname="col2"> <p>zip </p> </td> 
   <td colname="col3"> <p>Code postal de conversion. </p> </td> 
  </tr> 
 </tbody> 
</table>

Le tableau suivant contient des variables de trafic renseignées automatiquement lors de l’utilisation de bibliothèques JavaScript. Ces propriétés n’ont pas de variables associées mais peuvent être importées à l’aide de sources de données.

<table id="table_FDBC5BD225644AA09078C0570BE709FE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Variable de colonne Traitement complet </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>browserHeight </p> </td> 
   <td colname="col2"> <p>Hauteur du navigateur en pixels (par exemple, 768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>browserWidth </p> </td> 
   <td colname="col2"> <p>Largeur du navigateur en pixels (par exemple, 1 024). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>charSet </p> </td> 
   <td colname="col2"> <p>Jeu de caractères pris en charge pour votre site Web. Par exemple, UTF-8, ISO-8859-1, etc. </p> <p>Voir le livre blanc « <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/multibyte/index.html"  >Jeux de caractères à plusieurs octets (internationalisation)</a> » pour obtenir une liste complète. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickAction </p> </td> 
   <td colname="col2"> <p>Identificateur d’objet pour la carte des clics des visiteurs (oid). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickActionType </p> </td> 
   <td colname="col2"> <p>Type d’identificateur d’objet pour la carte des clics des visiteurs (oidt). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContext </p> </td> 
   <td colname="col2"> <p>Identificateur de page pour la carte des clics des visiteurs (pid). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContextType </p> </td> 
   <td colname="col2"> <p>Type d’identificateur de page pour la carte des clics des visiteurs (pidt). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickSourceID </p> </td> 
   <td colname="col2"> <p>Index source pour la carte des clics des visiteurs (oi). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickTag </p> </td> 
   <td colname="col2"> <p>Nom de balise d’objet pour la carte des clics des visiteurs (ot). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>colorDepth </p> </td> 
   <td colname="col2"> <p>Intensité de couleur du moniteur en bits (par exemple, 24). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>connectionType </p> </td> 
   <td colname="col2"> <p>Type de connexion du visiteur ( <span class="term"> lan </span> ou <span class="term"> modem </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cookiesEnabled </p> </td> 
   <td colname="col2"> <p>Y ou N selon que le visiteur prend en charge les cookies de session propriétaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>Code de devise par défaut utilisé sur votre site Web. </p> <p>Par exemple, USD = dollars américains, EUR = euros, JPY = yen japonais, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>homePage </p> </td> 
   <td colname="col2"> <p>Y ou N – Page active de la page d’accueil du visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaEnabled </p> </td> 
   <td colname="col2"> <p>Y ou N – selon que Java est activé sur l’ordinateur du visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaScriptVersion </p> </td> 
   <td colname="col2"> <p>Version JavaScript (par exemple, 1.3). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>plugins </p> </td> 
   <td colname="col2"> <p>Liste de noms des modules complémentaires de navigateur séparés par des points-virgules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>propN </p> </td> 
   <td colname="col2"> <p>Valeurs de vos propriétés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>referrer </p> </td> 
   <td colname="col2"> <p>URL du référent de la page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>resolution </p> </td> 
   <td colname="col2"> <p>Résolution de l’écran (par exemple, 1 024 x 768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>scXmlVer </p> </td> 
   <td colname="col2"> <p>Numéro de version de requête XML des rapports marketing (par exemple, 1.0). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timezone </p> </td> 
   <td colname="col2"> <p>Décalage du fuseau horaire du visiteur par rapport à GMT, en heures (ex. : -8). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorID </p> </td> 
   <td colname="col2"> <p>ID du visiteur. </p> </td> 
  </tr> 
 </tbody> 
</table>

