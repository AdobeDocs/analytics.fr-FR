---
description: valeur nulle
title: Feuille de route de mise en œuvre
uuid: 988bcca5-67ae-4e3f-97e6-6a42030b1962
translation-type: tm+mt
source-git-commit: 9d0b8e1e9bc2d92fb949ceed7bcfaa31818d02b8

---


# Feuille de route de mise en œuvre

## Nouveaux utilisateurs {#section_77433E4FC5ED4C6BAFC1E72EB61C4503}

Si vous êtes un nouvel utilisateur d’Adobe Analytics, vous pouvez créer rapidement votre première suite de rapports Analytics (référentiel de données) en utilisant le guide [Prise en main d’Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/). Vous pouvez ensuite déployer le code Analytics à l’aide d’[Experience Platform Launch](https://docs.adobelaunch.com/).

## Feuille de route de mise en œuvre {#section_E3DD8D199B744FFB9E9B386A44220206}

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Étape </th> 
   <th colname="col1" class="entry"> Tâche </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> Choix d’une méthode de mise en œuvre. </td> 
   <td colname="col2"> <p>Les méthodes de mise en œuvre d’Analytics les plus utilisées incluent : </p> <p> 
     <ul id="ul_A7475867861540EFBD77AEE8C6DAD418"> 
      <li id="li_035E2619670F4D04A7F708625A9C01EF"> <a href="https://docs.adobelaunch.com/"> Experience Platform Launch</a> (Recommandé) <p>Ce guide vous explique tout ce que vous devez savoir concernant l’utilisation des fonctionnalités de gestion de SDK mobile et des balises de site web d’Adobe, et leur mise en œuvre. </p> </li> 
      <li id="li_996FA2F5B0E149399CED391AB5235D8A"> <a href="/help/implement/c-implement-with-dtm/dtm-implementation-overview.md">Dynamic Tag Management </a> <p>Ce guide contient des informations spécifiques à Analytics afin de vous guider dans la mise en œuvre de Dynamic Tag Management. </p> </li> 
      <li id="li_18E6AD6D864246D0BA26DAA1D91DD811"> <a href="/help/implement/js-implementation/javascript-implementation-overview.md"> JavaScript </a> <p>Ce guide contient une description des variables de collecte de données et des informations détaillées sur la mise en œuvre du code de collecte de données dans JavaScript, y compris <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js.html">video </a>. </p> </li> 
      <li id="li_85EC7A0AC5E04EE6981ED72A88C5D1FD"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html"> SDK d’Analytics </a> <p>Utilisez les SDK d’Analytics pour gérer : </p> <p> 
        <ul id="ul_F67F2E1964724800A84445A36DFB8E86"> 
         <li id="li_9C43F051EB5B4EA7A4C14EC1513DB824"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/analytics_main.html"> Applications mobiles sur iOS </a> </li> 
         <li id="li_4354E44EB8B3494A88578C1621EF5BAC"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/analytics_main.html"> Applications mobiles sur Android </a> </li> 
        </ul> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> Configurez le service d’identité. </td> 
   <td colname="col2"> <p>(Anciennement <span class="term"> Service d’identification des visiteurs </span>.) Voir <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html"> Configuration du service d’identité pour Analytics </a>. </p> 
    <draft-comment> 
     <p>Ajoutez le code d’initialisation d’identifiant visiteur suivant au début du fichier <code> VisitorAPI.js </code> : </p> 
     <code class="syntax javascript">
       var&nbsp;visitor&nbsp;=&nbsp;Visitor.getInstance("INSERT-MCORG-ID-HERE"); 
      visitor.trackingServer&nbsp;=&nbsp;"INSERT-TRACKING-SERVER-HERE";&nbsp;//&nbsp;same&nbsp;as&nbsp;s.trackingServer 
      visitor.trackingServerSecure&nbsp;=&nbsp;"INSERT-SECURE-TRACKING-SERVER-HERE";&nbsp;//same&nbsp;as&nbsp;s.trackingServerSecure 
      /* 
      &nbsp;==============&nbsp;DO&nbsp;NOT&nbsp;ALTER&nbsp;ANYTHING&nbsp;BELOW&nbsp;THIS&nbsp;LINE&nbsp;!&nbsp;============
     </code> 
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> "INSERT-MCORG-ID-HERE" </code> - (Obligatoire) Cet ID d’organisation Adobe Experience Cloud est envoyé à votre administrateur lorsque votre société est configurée pour Adobe Experience Cloud. </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code> "INSERT-TRACKING-SERVER-HERE" </code> - (Obligatoire) Votre serveur de suivi Analytics. </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code> "INSERT-SECURE-TRACKING-SERVER-HERE" </code> - (Obligatoire si ssl est activé) Votre serveur de suivi Analytics sécurisé. </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> Utilisez la méthode de mise en œuvre sélectionnée pour mettre à jour le code de page et le déployer. </td> 
   <td colname="col2"> <p>Place the page code just after the opening <code> &lt;body&gt; </code> tag on each page you want to track. Vous devez, au minimum, mettre à jour les variables suivantes : </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // for example, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Utilisez le débogueur Adobe Experience Cloud pour vérifier que l’envoi des données est en cours. </td> 
   <td colname="col2"> <p>Installez le <a href="/help/implement/impl-testing/debugger.md">débogueur Experience Cloud </a>. Une fois cet outil installé, chargez une page dans laquelle vous avez déployé le code de page, puis ouvrez le débogueur. Le débogueur affiche des informations détaillées sur les données de collecte qui ont été envoyées : </p> </td> 
  </tr> 
 </tbody> 
</table>

## Plus d’informations {#section_64B6A948DF4A4B5E9E1D22549F8C508B}

Pour plus d’informations sur les différences entre les méthodes [!UICONTROL Experience Platform Launch], [!UICONTROL Dynamic Tag Management] et JavaScript, voir [Choix d’une méthode de mise en œuvre](/help/implement/c-implementation-methods/choose-implementation-method.md).

Pour obtenir un aperçu rapide du processus de prise en main et configurer rapidement votre première suite de rapports Analytics, voir [Prise en main de la mise en œuvre d’Analytics](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) dans le guide Prise en main d’Analytics.
