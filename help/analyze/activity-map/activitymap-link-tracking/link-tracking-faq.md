---
description: Questions fréquentes sur le suivi des liens dans Activity Map.
title: Questions fréquentes sur le suivi des liens
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: Professionnel, Administrateur
translation-type: tm+mt
source-git-commit: f9d9c7dbaf5fde5bd51c929d927d4cd3f61cb63b
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 69%

---


# Questions fréquentes sur le suivi des liens

Questions fréquentes sur le suivi des liens dans Activity Map.

>[!CAUTION]
>
>En activant le suivi Activity Map, **vous pouvez collecter des données d’informations d’identification personnelle (PII).** Ces données peuvent être utilisées seules ou avec d’autres informations pour identifier, contacter ou localiser une seule personne, ou pour identifier une personne dans son contexte.

Vous trouverez ci-dessous certains cas connus de collecte des données relatives aux informations d’identification personnelles à l’aide du suivi Activity Map :

* Liens `Mailto`. Un lien mailto est un type de lien HTML qui active le client de messagerie par défaut sur l’ordinateur afin d’envoyer un message électronique.
* Liens `User ID` qui peuvent s’afficher dans l’en-tête ou le pied de page d’un site web une fois l’utilisateur connecté.
* Dans le cas des établissements financiers, le numéro de compte peut s’afficher sous la forme d’un lien. Le fait de cliquer dessus collecte le texte du lien.
* Les sites web du secteur des soins de santé peuvent également afficher des données relatives aux informations d’identification personnelles sous la forme de liens. Le fait de cliquer sur ces liens collecte le texte du lien, et donc les données relatives aux informations d’identification personnelles.

<table id="table_0951EAC617344156BAE43000CCD838AF">
 <tbody>
  <tr>
   <td colname="col1"> <b>Q : Quand le suivi des liens se produit-il ?</b> </td>
   <td colname="col2"> R : L’identification des liens et des régions d’Activity Map se produit lorsque les utilisateurs cliquent sur une page. </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Q : Quels éléments sont suivis par défaut ?</b> </td>
   <td colname="col2"> R : Si un événement de clic se produit sur un élément, certaines vérifications doivent être effectuées afin de déterminer si AppMeasurement le considérera comme un lien. Ces vérifications sont les suivantes :
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0">
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">S’agit-il d’une balise <code>&lt;A&gt;</code> ou <code>&lt;AREA&gt;</code> avec une propriété <code>"href"</code> ? </li>
     <li id="li_77828D24D54343E5B9A1FF7345221781">Existe-t-il un attribut <code>"onclick"</code> qui définit une variable <code>s_objectID</code> ? </li>
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">S’agit-il d’une balise <code>&lt;INPUT&gt;</code> ou d’un bouton <code>&lt;SUBMIT&gt;</code> avec une valeur ou un texte enfant ? </li>
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">S’agit-il d’une balise <code>&lt;INPUT&gt;</code> de type <code>&lt;IMAGE&gt;</code> et d’une propriété <code>"src"</code> ? </li>
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">Est-ce un <code>&lt;BUTTON&gt;</code> ? </li>
    </ul>
    Si la réponse à l’une des questions ci-dessus est <b>Oui</b>, l’élément est considéré comme un lien et sera suivi. <br/>
     <br/>
    Important : Les balises de bouton avec l’attribut ne  <code>type="button"</code> sont pas considérées comme des liens par AppMeasurement. Envisagez de supprimer <code>type="button"</code> sur les balises de bouton et d’ajouter <code>role="button"</code> ou <code>submit="button"</code> à la place. <br/>
     <br/>
    Important : Une balise d’ancrage avec un début  <code>"href"</code> qui  <code>"#"</code> est considéré comme un emplacement de cible interne par AppMeasurement, et non comme un lien (puisque vous ne quittez pas la page). Par défaut, Activity Map ne suit pas ces emplacements cibles internes. Il effectue uniquement le suivi des liens qui permettent à l’utilisateur d’accéder à une nouvelle page. </td> 
  </tr>
  <tr>
   <td colname="col1"> <b>Q : Comment Activity Map suit-elle d’autres éléments HTML visuels ?</b> </td>
   <td colname="col2">
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5">
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>Par le biais de la<code>s.tl()</code> fonction</b> <br/>
       <br/>
      Si le clic s’est produit par le biais d’un appel , Activity Map recevra également cet événement de clic et déterminera si une variable de chaîne a été trouvée. <code>s.tl()</code><code>linkName</code> Au cours de l'exécution de <code>s.tl()</code>, <code>linkName</code> sera défini comme identifiant de lien Activity Map. L'élément sur lequel l'utilisateur a cliqué à l'origine de l'appel <code>s.tl()</code> sera utilisé pour déterminer la région. <br/>
       <br/>
      Exemple :  <br/>
       <br/>
      <code>&lt;img&nbsp;onclick="s.tl(true,'o','abc')"&nbsp;src="someimageurl.png"/&gt;</code><br/>
       
     </li>
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>Par le biais de  <code>s_objectID</code> </b> <br/>
       <br/>
      variableExample :  <br/>
       <br/>
      <code>&lt;img&nbsp;onclick="s_objectID='abc';"&nbsp;src="someimageurl.png"/&gt;</code><br/>
      <code>&lt;a&nbsp;href="some-url.html"&nbsp;onclick="s_objectID='abc';"&nbsp;&gt;</code><br/>
      <code>&nbsp;&nbsp;Link&nbsp;Text&nbsp;Here</code><br/>
      <code>&lt;/a&gt;</code> <br/>
       <br/>
      Important : Notez qu’un point-virgule de fin (<code>;</code>) est requis lors de l’utilisation  <code>s_objectID</code> dans le Activity Map.
     </li>
    </ol>
   </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Q : Pouvez-vous me donner des exemples de liens qui seront suivis ?</b> </td>
   <td colname="col2">
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA">
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0">
      <code>&lt;a&nbsp;href="/home"&gt;Home&lt;/a&gt;</code>
     </li>
     <li id="li_76F3DB36ED734132A2386871E6EB4929">
      <code>&lt;input&nbsp;type="submit"&nbsp;value="Submit"/&gt;</code>
     </li>
     <li id="li_10CF9EDA224645169E7CDF74956DB98B">
      <code>&lt;input&nbsp;type="image"&nbsp;src="submit-button.png"/&gt;</code>
     </li>
     <li id="li_9FA171D7F49547E798DE21869F73A402">
      <code>&lt;p&nbsp;onclick="var&nbsp;s_objectID='custom&nbsp;link&nbsp;id';"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/p&gt;</code>
     </li>
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF">
      <code>&lt;div&nbsp;onclick="s.tl(true,'o','custom&nbsp;link&nbsp;id')"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/div&gt;</code>
     </li>
    </ol>
   </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Q : Pouvez-vous me donner des exemples de liens qui ne seront PAS suivis ?</b> </td>
   <td colname="col2">
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547">
     <li id="li_99372060646B43EF94C13A9C682CE693">Raison : la balise d’ancrage ne possède pas de valide <code>"href"</code> <br/>
       <br/>
      <code>&lt;a&nbsp;name="innerAnchor"&gt;Section&nbsp;header&lt;/a&gt;</code><br/>
       
     </li>
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Raison : Ni <code>s_ObjectID</code> ni <code>s.tl()</code> ne présente <br/>
       <br/>
      <code>&lt;p&nbsp;onclick="showPanel('market&nbsp;rates')"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/p&gt;</code><br/>
       
     </li>
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Raison : Ni <code>s_ObjectID</code> ni <code>s.tl()</code> ne présente <br/>
       <br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="A"/&gt;</code><br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="B"/&gt;</code><br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="C"/&gt;</code><br/>
       
     </li>
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Raison : La propriété <code>"src"</code> ne comporte pas d'élément de formulaire <code>input</code> <br/>
       <br/>
      <code>&lt;input&nbsp;type="image"/&gt;</code><br/>
       
     </li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>
