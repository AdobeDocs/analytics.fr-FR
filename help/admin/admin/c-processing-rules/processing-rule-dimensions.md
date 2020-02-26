---
description: Dimensions que vous pouvez lire et écrire (sauf indication contraire) à l’aide de règles de traitement.
subtopic: Processing rules
title: Dimensions disponibles pour les règles de traitement
topic: Admin tools
uuid: ba73ab59-a8cf-491c-8757-5fb03d6b0745
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Dimensions disponibles pour les règles de traitement

Dimensions que vous pouvez lire et écrire (sauf indication contraire) à l’aide de règles de traitement.

## Valeurs personnalisées et données contextuelles {#section_7A5E1810CAC34B0BBC69F8F5F7C75AA5}

<table id="table_5011C501D5DC489E87A42FFC51DEB40D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valeur </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Valeur personnalisée </p> </td> 
   <td colname="col2"> <p>Valeurs ou texte personnalisés saisis directement dans l’action d’une règle de traitement. Ces valeurs sont disponibles dans les conditions et règles suivantes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valeur concaténée </p> </td> 
   <td colname="col2"> <p>Valeurs créées par la combinaison de deux autres valeurs. La catégorie et le nom de page, par exemple, peuvent être combinés afin de créer une sous-catégorie. Ces valeurs sont disponibles dans les conditions et règles suivantes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valeurs modifiées </p> </td> 
   <td colname="col2"> <p>Si une valeur de variable est modifiée à l’aide de règles de traitement, elle est utilisée dans les conditions et règles suivantes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variables de données contextuelles </p> </td> 
   <td colname="col2"> <p>Variables nommées envoyées avec un accès. </p> <p>Remarque : pour figurer dans un rapport, une donnée contenue dans une variable de données contextuelles doit être copiée dans une variable de création de rapports. Les variables de données contextuelles ne sont visibles dans aucune interface de création de rapports, y compris Flux de données de parcours de navigation. </p> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Copier une variable de données contextuelles dans une eVar </a> </p> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> Définir un événement à l’aide d’une variable de données contextuelles </a> </p> <p> <a href="https://marketing.adobe.com/resources/help/fr_FR/sc/implement/context_data_variables.html"> Variables de données contextuelles</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables de trafic {#section_225156106F8B41F8BC1E68D58DDC2652}

<table id="table_575F618C59DC4933BC77F935518EAE39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>prop 1-75 </p> </td> 
   <td colname="col2"> <p> <code> prop1 - prop75</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hiérarchie 1-5 </p> </td> 
   <td colname="col2"> <p> <code> hier1 - hier5</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Section du site </p> </td> 
   <td colname="col2"> <p> <code> s.channel </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveur </p> </td> 
   <td colname="col2"> <p> <code> s.server </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Attributs d’accès {#section_07E69A86A47741A083FD84F112EB80D0}

<table id="table_9011B1FA462B4DBBAA58FC2D6D638DA1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribut </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identifiant de Report Suite (lecture seule) </p> </td> 
   <td colname="col2"> <p>Suite de rapports sur laquelle est exécutée la règle de traitement, qui doit être différente de la suite d’origine spécifiée dans AppMeasurement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom de page </p> </td> 
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>Remarque : une page vue est comptabilisée sur tous les accès pour lesquels le nom de page n’est pas vide. Lorsqu’un lien est suivi, le serveur de collecte des données supprime le nom de page de l’accès afin que les pages vues ne soient pas comptabilisées. Si vous réinsérez un nom de page dans ces appels à l’aide des règles de traitement, une page vue est comptabilisée. Nous vous recommandons de vérifier que le nom de page est déjà défini avant de le modifier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL de la page </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> ou URL de la page en cours si <code> s.pageURL</code> n’est pas spécifié. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paramètre de chaîne de requête </p> </td> 
   <td colname="col2"> <p>Valeur d’un paramètre de chaîne de requête spécifié dans l’URL en cours ou null s’il n’existe aucun paramètre. Dans le cas de l’URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, la valeur du paramètre de chaîne de requête <span class="syntax codeph"> cid</span> est <b>ad1</b> et le <span class="syntax codeph"> nœud</span> du paramètre de chaîne de requête est <b>4</b>. </p> <p>Si vous exécutez JavaScript AppMeasurement H.25.2 ou version antérieure, il se peut que l’URL de la page soit tronquée après 255 caractères. JavaScript AppMeasurement H.25.3 (publié en janvier 2013) et versions ultérieures fournissent une URL complète aux règles de traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chemin de la page </p> </td> 
   <td colname="col2"> <p>Chemin d’accès de l’URL de la page. Le chemin de l’URL <b>https://www.example.com/news/a.html?cid=ad1</b> est <span class="syntax codeph">news/a.html</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine de page </p> </td> 
   <td colname="col2"> <p>Nom d’hôte complet, indiqué dans l’URL. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine racine de page </p> </td> 
   <td colname="col2"> <p>Les deux dernières sections du nom d’hôte de la page. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chaîne de requête de page </p> </td> 
   <td colname="col2"> <p>Chaîne de requête complète de l’URL. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Référent* (lecture seule) </p> </td> 
   <td colname="col2"> <p>Référent HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paramètre de chaîne de requête de référent (lecture seule) </p> </td> 
   <td colname="col2"> <p>Valeur d’un paramètre de chaîne de requête spécifié dans l’URL de référence ou null s’il n’existe aucun paramètre. Dans le cas de l’URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, la valeur du paramètre de chaîne de requête <span class="syntax codeph"> cid</span> est <b>ad1</b> et le <span class="syntax codeph"> nœud</span> du paramètre de chaîne de requête est <b>4</b>. </p> <p>Si vous exécutez JavaScript AppMeasurement H.25.2 ou version antérieure, il se peut que l’URL de la page soit tronquée après 255 caractères. JavaScript AppMeasurement H.25.3 (publié en janvier 2013) et versions ultérieures fournissent une URL complète aux règles de traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine référent (lecture seule) </p> </td> 
   <td colname="col2"> <p>Nom d’hôte complet du référent. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domaine racine référent (lecture seule) </p> </td> 
   <td colname="col2"> <p>Les deux dernières sections du nom d’hôte du référent. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chaîne de requête de référent (lecture seule) </p> </td> 
   <td colname="col2"> <p>Paramètres de chaîne de requête contenus dans l’URL de référence. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse IP (lecture seule) </p> </td> 
   <td colname="col2"> <p>Adresse IP telle qu’elle est rapportée par le navigateur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agent utilisateur (lecture seule) </p> </td> 
   <td colname="col2"> <p>Agent utilisateur tel qu’il est rapporté par le navigateur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version du code AppMeasurement (lecture seule) </p> </td> 
   <td colname="col2"> <p>Version de la bibliothèque appMeasurement utilisée pour effectuer la demande. Lors de l’utilisation de balises d’image, vous pouvez compléter cet attribut avec une valeur personnalisée lue à l’aide de règles de traitement. Cette valeur apparaît à l’emplacement suivant dans l’URL : </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/... </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables de conversion {#section_311856B21B3B49DBAA0539CFA06C409F}

<table id="table_E28729026EDA485989178A3B887B5983"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>eVar 1-N </p> </td> 
   <td colname="col2"> <p> <code> evar1</code> - <code> evarN</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code de suivi de campagne </p> </td> 
   <td colname="col2"> <p> <code> s.campaign</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code de devise </p> </td> 
   <td colname="col2"> <p> <code> s.currencyCode</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variables de liste 1 à 3 </p> </td> 
   <td colname="col2"> <p> <code> s.list1</code> - <code> s.list3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifiant d’achat </p> </td> 
   <td colname="col2"> <p> <code> s.purchaseID</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de transaction </p> </td> 
   <td colname="col2"> <p> <code> s.transactionID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>État du visiteur </p> </td> 
   <td colname="col2"> <p> <code> s.state</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code postal du visiteur </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Événements de succès {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

Les règles de traitement peuvent définir des événements, mais elles ne peuvent pas les lire en tant que conditions.

<table id="table_926ED12B58CA4FB685D799DC6EE567C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Événement </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Événement 1-1 000 </p> <p>(Pour les utilisateurs de SiteCatalyst 15, événement 1 à 100.) </p> </td> 
   <td colname="col2"> <p> <code> event1</code> - <code> event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchase, scView, scAdd et autres événements de panier </p> </td> 
   <td colname="col2"> <p>Événements prédéfinis. </p> </td> 
  </tr> 
 </tbody> 
</table>

