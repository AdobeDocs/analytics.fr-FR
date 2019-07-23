---
description: Pour commencer à utiliser Analytics, des données doivent être envoyées à une suite de rapports afin de les afficher dans des rapports.
keywords: Implémentation d'Analytics ; javascript ; implémentation javascript ; appmeasurement ; télécharger appmeasurement ; Service d'identité ; visitorapi. js ; mise en cache ; compression appmeasurement
seo-description: Pour commencer à utiliser Analytics, des données doivent être envoyées à une suite de rapports afin de les afficher dans des rapports.
seo-title: Présentation de la mise en œuvre JavaScript
solution: Analytics
title: Présentation de la mise en œuvre JavaScript
topic: Développeur et mise en œuvre
uuid: bb 661 d 8 c-faf 9-4454-ac 3 c -0 c 1 a 4 c 0 a 9336
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Présentation de la mise en œuvre JavaScript

Pour commencer à utiliser Analytics, des données doivent être envoyées à une suite de rapports afin de les afficher dans des rapports.

The easiest and recommended way to send data to [!DNL Analytics] is by using [Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md). Toutefois, dans certains cas, il est possible que vous vouliez mettre en œuvre Analytics à l’aide de l’ancienne méthode JavaScript.

>[!NOTE]
>
>Cette section décrit la méthode héritée d'implémentation d'Analytics. Tous les clients Analytics ont accès à [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) qui est la méthode standard pour déployer des balises Experience Cloud.

## Procédure de mise en œuvre {#section_73961BAD5BB4430A95E073DE5C026277}

Pour implémenter une page avec du code pour collecter des données, vous devez avoir accès aux serveurs d’hébergement afin de télécharger du nouveau contenu sur votre site Web. Disposer d’un site Web sur lequel implémenter du code s’avère également utile.

Les étapes suivantes vous invitent à parcourir une mise en œuvre de base d’Adobe Analytics.

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Etape </th> 
   <th colname="col1" class="entry"> Tâche </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> Télécharger AppMeasurement pour JavaScript et le service d’identification des visiteurs. </td> 
   <td colname="col2"> <p>Pour ce faire, reportez-vous à la section <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=code_manager_admin" format="http" scope="external">Gestionnaire de code </a>. </p> <p>Le fichier ZIP à télécharger contient plusieurs fichiers. <code> AppMeasurement.js</code> et <code>VisitorAPI.js</code> sont les fichiers requis lors de la mise en œuvre d’Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> Configuration du service d'identité. </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p>Ajoutez le code d’initialisation d’identifiant visiteur suivant au début du fichier <code>VisitorAPI.js</code> : </p> 
     <code class="syntax javascript">var visitor = Visitor. getinstance (« INSERT-MCORG-ID-HERE ») ; visitor. trackingserver = « INSERT-TRACKING-SERVER-HERE » ; // identique à s. trackingserver visitor. trackingserversecure = « INSERT-SECURE-TRACKING-SERVER-HERE » ; //same as s. trackingserversecure/* = = DO NOT ALTER ANYTHING BELOW THIS LINE = = 
     </code>  
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> « INSERT-MCORG-ID-HERE » </code> - (Obligatoire) Cet ID d'organisation Adobe Experience Cloud est envoyé à votre administrateur lorsque votre société est configurée pour Adobe Experience Cloud. </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code> "INSERT-TRACKING-SERVER-HERE"</code> – (requis) Votre serveur de suivi Analytics. </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code> "INSERT-SECURE-TRACKING-SERVER-HERE"</code> – (Obligatoire si ssl est activé) Votre serveur de suivi Analytics sécurisé. </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> Mettre à jour <code>AppMeasurement.js </code>. </td> 
   <td colname="col2"> <p>Copiez l’<a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_4351543F2D6049218E18B48769D471E2" format="dita" scope="local">Exemple de code AppMeasurement.js</a> et collez-le au début de votre fichier <code>AppMeasurement.js</code>. Vous devez, au minimum, mettre à jour les variables suivantes : </p> 
    <ul id="ul_62FA640BD2604E589650A92158272615"> 
     <li id="li_54E56B483B3A416EA27D7B540D60E39F"> <code> s.account="INSERT-RSID-HERE" </code> </li> 
     <li id="li_00A958289BB045379B436F13287E03D5"> <code> s.trackingServer="INSERT-TRACKING-SERVER-HERE" </code> </li> 
     <li id="li_C0779ADF780440ED876236AEB1FB5DCC"> <code> s.visitorNamespace = "INSERT-NAMESPACE-HERE" </code> </li> 
     <li id="li_93072B656C134D8C89195B7F2D7D8F05"> <code> s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE") </code> </li> 
    </ul> <p> See <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"> Correctly populate the trackingServer and trackingServerSecure variable </a> or contact Client Care if you are unsure about any of these values. Si les variables ne sont pas correctement définies, les données ne seront pas collectées par votre mise en œuvre. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> Héberger <code>AppMeasurement.js</code> et <code>VisitorAPI.js </code>. </td> 
   <td colname="col2"> <p>Ces fichiers JavaScript principaux doivent être hébergés sur un serveur Web accessible par toutes les pages de votre site : Vous aurez besoin du chemin d’accès à ces fichiers à l’étape suivante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Référencer <code>AppMeasurement.js</code> et <code>VisitorAPI.js</code> sur toutes les pages du site. </td> 
   <td colname="col2"> <p> Insérez le service d’identifiant visiteur en ajoutant la ligne de code suivante dans la balise <code>&lt;head&gt;</code> ou &lt;body&gt; de chaque page. Le fichier <code>VisitorAPI.js</code> doit être inclus avant <code>AppMeasurement.js</code> : </p> 
    <code class="syntax html">&lt; script language = « JavaScript » type = « text/javascript » src = "https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js" &gt; &lt;/script &gt; </code>
  <p> Insérez AppMeasurement pour JavaScript en ajoutant la ligne de code suivante dans la balise <code>&lt;head&gt;</code> ou <code>&lt;body&gt;</code> de chaque page : </p> 
    <code class="syntax html">&lt; script language = « JavaScript » type = « text/javascript » src = "https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js" &gt; &lt;/script &gt; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step6_icon.png" id="image_1C4293CA98F04EE2ADA69EAB95BDE8B1" /> </td> 
   <td colname="col1"> Mettre à jour et déployer le code de page. </td> 
   <td colname="col2"> <p>Copier l’<a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_042412C29CC249E298F19B2BC2F43CE7" format="dita" scope="local">Exemple de code de page</a> et collez-le juste après la balise <code>&lt;body&gt;</code> d’ouverture sur chaque page dont vous souhaitez effectuer le suivi. Vous devez, au minimum, mettre à jour les variables suivantes : </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // par exemple, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step7_icon.png" id="image_A423CBF386AF4E5986E8CBB6E31CD3E5" /> </td> 
   <td colname="col1"> Utiliser le DigitalPulse Debugger pour vérifier que l’envoi des données est en cours. </td> 
   <td colname="col2"> <p>Installez le signet d’applet   <a href="../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2" format="dita" scope="local"> Signet d’applet d’Adobe Debugger</a>. Une fois cet outil installé, chargez une page dans laquelle vous avez déployé le code de page, puis ouvrez le débogueur. Le débogueur affiche des informations détaillées sur les données de collecte qui ont été envoyées : </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mise en cache {#section_4E2D1D962DF046418134C43CFC49AD4A}

Le fichier JavaScript est mis en cache dans le navigateur du visiteur après son chargement initial. En règle générale, il n’est pas téléchargé plus d’une fois par session. Il n’est pas téléchargé sur chaque page, même s’il est utilisé par toutes les pages du site. Sur la plupart des sites Web, les utilisateurs visualisent, en moyenne, plus de quelques pages par session. Dès lors, le transfert de code JavaScript utilisé plusieurs fois dans ce fichier peut générer un nombre moins important de données téléchargées globales.

## Compression JavaScript pour AppMeasurement {#section_C10BBC84C81C414088F97363D29E021B}

Si le poids (taille) des pages du code H (AppMeasurement pour JavaScript 1.0 est précompressé) vous préoccupe, Adobe vous conseille d’envisager la compression du fichier à l’aide de GZIP. GZIP est pris en charge par les principaux navigateurs du marché ; il offre de meilleures performances que la compression JavaScript pour compresser et décompresser le fichier JavaScript principal [!DNL s_code.js].

Les liens ci-dessous vous aident à comprendre l’utilisation de la fonctionnalité GZIP sur votre site en vue de gérer la compression du code JavaScript du fichier [!DNL s_code.js] :

[Module Apache mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html) (en anglais)

[Activation de la compression Gzip avec Tomcat et Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/) (en anglais)
