---
description: Questions fréquentes sur le suivi des liens dans Activity Map.
seo-description: Questions fréquentes sur le suivi des liens dans Activity Map.
seo-title: FAQ sur le suivi des liens
solution: Analytics
title: FAQ sur le suivi des liens
topic: Activity Map
uuid: 10172073-b 98 b -4950-8397-67 a 18 b 37 b 3 b 4
translation-type: tm+mt
source-git-commit: d877f86dd5a05d0aa452ecebce47468ebf94cbb2

---


# FAQ sur le suivi des liens

Questions fréquentes sur le suivi des liens dans Activity Map.

>[!CAUTION]
>
>By turning on Activity Map tracking, **you may be** **collecting personally identifiable information (PII) data.** This data can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context.

Vous trouverez ci-dessous certains cas connus de collecte des données relatives aux informations d’identification personnelles à l’aide du suivi Activity Map :

* `Mailto` liens. Un lien mailto est un type de lien HTML qui active le client de messagerie par défaut sur l’ordinateur afin d’envoyer un message électronique.
* `User ID` liens pouvant figurer dans l'en-tête/pied de page d'un site Web une fois que l'utilisateur a ouvert une session.
* Dans le cas des établissements financiers, le numéro de compte peut s’afficher sous la forme d’un lien. Le fait de cliquer dessus collecte le texte du lien.
* Les sites web du secteur des soins de santé peuvent également afficher des données relatives aux informations d’identification personnelles sous la forme de liens. Le fait de cliquer sur ces liens collecte le texte du lien, et donc les données relatives aux informations d’identification personnelles.

<table id="table_0951EAC617344156BAE43000CCD838AF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Q : Quand le suivi des liens se produit-il ?</b> <p> </p> </td> 
   <td colname="col2"> R : L’identification des liens et des régions d’Activity Map se produit lorsque les utilisateurs cliquent sur une page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q : Quels éléments sont suivis par défaut ?</b> <p> </p> </td> 
   <td colname="col2"> R : Si un événement de clic se produit sur un élément, certaines vérifications doivent être effectuées afin de déterminer si AppMeasurement le considérera comme un lien. Ces vérifications sont les suivantes : 
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0"> 
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">S’agit-il d’une balise &lt;A&gt; ou &lt;AREA&gt; avec une propriété HREF ? </li> 
     <li id="li_77828D24D54343E5B9A1FF7345221781">Un attribut « onclick » définit-il une variable s_objectID ? </li> 
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">S’agit-il d’une balise INPUT ou d’un bouton SUBMIT avec une valeur ou du texte enfant ? </li> 
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">S’agit-il d’une balise INPUT de type IMAGE avec une propriété src ? </li> 
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">S’agit-il d’un &lt;Bouton&gt; ? </li> 
    </ul> <p>Si la réponse à l’une des questions ci-dessus est <b>Oui</b>, l’élément est considéré comme un lien et sera suivi. </p> <p>Important : Les balises de bouton avec l’attribut type="button" ne sont pas considérées comme des liens par AppMeasurement. Envisagez de supprimer "type='button'" sur les balises de bouton et d’ajouter à la place role="button" ou submit="button". </p> <p>Important : Une balise d'ancrage avec une href commençant par « # » est considérée comme un emplacement cible interne par appmeasurement, et non comme un lien (puisque vous ne quittez pas la page). Par défaut, Carte d'activités ne suit pas ces emplacements cibles internes. Il suit uniquement les liens qui parcourent l'utilisateur vers une nouvelle page.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q : Comment Activity Map suit-elle d’autres éléments HTML visuels ?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5"> 
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>Par le biais de la fonction <code>s.tl()</code></b> <p>Si le clic s’est produit par le biais d’un appel s.tl, Activity Map recevra également cet événement de clic et déterminera si une variable de chaîne linkName a été trouvée. Lors de l’exécution de s.tl, ce linkName sera défini comme l’ID de lien d’Activity Map. L’élément sur lequel l’utilisateur a cliqué et qui est à l’origine de l’appel s.tl() sera utilisé pour déterminer la région. Exemple : </p> <p> 
       <code>&lt; img &amp; amp ; nbsp ; onclick = "s. tl (true,'o ','abc ')" &amp; amp ; nbsp ; src = "someimageurl. png"/&gt; </code>
  </p> </li> 
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>Par le biais de la variable <code>s_objectID</code></b> <p>Exemple : </p> <p> 
       <code>&lt; img onclick = « s_ objectid ='abc '; " src = "someimageurl. png"/&gt; &lt; a href = « some-url.html » onclick = « s_ objectid ='abc ';  » &gt; Text Text Here &lt;/a &gt; </code>
  </p> <p>Important : Notez qu’un point-virgule (;) de fin est requis lorsque la variable s_objectID est utilisée dans Activity Map. </p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q : Pouvez-vous me donner des exemples de liens qui seront suivis ?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA"> 
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0"> 
      <code>&lt; a &amp; amp ; nbsp ; href = "/home" &gt; Home &lt;/a &gt; </code>
  </li> 
     <li id="li_76F3DB36ED734132A2386871E6EB4929"> 
      <code>&lt; input &amp; amp ; nbsp ; type = "submit" &amp; amp ; nbsp ; value = "Submit"/&gt; </code>
  </li> 
     <li id="li_10CF9EDA224645169E7CDF74956DB98B"> 
      <code>&lt; input &amp; amp ; nbsp ; type = "image" &amp; amp ; nbsp ; src = "submit-button. png"/&gt; </code>
  </li> 
     <li id="li_9FA171D7F49547E798DE21869F73A402"> 
      <code>&lt; p onclick = "var s_ objectid ='id de lien personnalisé '; " &gt; &lt; span class = "title" &gt; Current Market Rate &lt;/span &gt; &lt; span class = "subtitle" &gt; 1.45 USD &lt;/span &gt; &lt;/p &gt; </code>
  </li> 
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF"> 
      <code>&lt; div onclick = "s. tl (true,'o ','custom link id ')" &gt; &lt; span class = "title" &gt; Current Market Rate &lt;/span &gt; &lt; span class = "subtitle" &gt; 1.45 USD &lt;/span &gt; &lt;/div &gt; </code>
  </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q : Pouvez-vous me donner des exemples de liens qui ne seront PAS suivis ?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547"> 
     <li id="li_99372060646B43EF94C13A9C682CE693">Raison : la balise d’ancrage ne possède pas de href valide 
      <code>&lt; a &amp; amp ; nbsp ; name = "inneranchor" &gt; Section &amp; amp ; nbsp ; header &lt;/a &gt; </code>
  </li> 
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;p onclick="showPanel('market rates')"&gt;     &lt;span class="title"&gt;Current Market Rates&lt;/span&gt;&lt;span  class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;input type="radio" onclick="changeState(this)" name="group1" value="A"/&gt; &lt;input type="radio" onclick="changeState(this)" name="group1" value="B"/&gt; &lt;input type="radio" onclick="changeState(this)" name="group1" value="C"/&gt;
      </code> </li> 
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Reason: src property is missing a form input element 
      <code>
        &lt;input&amp;nbsp;type="image"/&gt; 
      </code> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

