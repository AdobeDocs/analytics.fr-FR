---
description: Notes de mise à jour cumulées pour iOS.
seo-description: Notes de mise à jour cumulées pour iOS.
seo-title: iOS
solution: Analytics,Experience Cloud
subtopic: Notes de mise à jour
title: iOS
topic: Développeur et mise en œuvre
uuid: cc98f8f2-f619-4b31-abf9-e43f4deac64f
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# iOS{#ios}

Notes de mise à jour cumulées pour iOS.

>[!NOTE]
>
>Pour trouver la version actuelle de la bibliothèque, activez la journalisation du débogage.

Les téléchargements de bibliothèque mobile sont disponibles sur [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) et sur [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-ios).

[Documentation 4.x](https://marketing.adobe.com/resources/help/en_US/mobile/ios/)

[Documentation 3.x](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/ios/)

## Version 4.13.4 {#section_BF05D33CEF6E42358C8089441449449B}

The [!DNL iOS] SDK version 4.13.4 (Feb 16, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_657D643E874D47C099F2F43519C9C1C7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Messagerie in-app </p> </td> 
   <td colname="2"> <p> Correction d’un problème qui empêchait d’utiliser la version correcte de l’application lors de la détermination d’une audience. Ce problème survenait lorsqu’un utilisateur mettait à niveau une application sans relancer la fonctionnalité Cycle de vie. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Acquisition </p> </td> 
   <td colname="2"> <p> Ajout d’un délai de trois secondes avant l’émission d’appels d’API pour récupérer les données Apple Search Ad à l’installation d’une application (conformément aux recommandations de la documentation). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.3 {#section_39618D2B29F942FCBF37E4F5507AA131}

The [!DNL iOS] SDK version 4.13.3 (Jan 19, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_341D35BF18714139A95CA5491899185D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Messagerie in-app </p> </td> 
   <td colname="2"> <p> Vous pouvez désormais désactiver les messages plein écran lorsque VoiceOver est en cours d’exécution. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> Gestion améliorée de l’accès aux bases de données en lecture seule. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Général </p> </td> 
   <td colname="2"> <p> Résolution d’un problème susceptible d’entraîner un blocage lors de l’appel d’une méthode de suivi en arrière-plan tout en utilisant des groupes d’applications. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.2 {#section_CB0DFFDB38FE4D14A84423DF40BF8FD3}

The [!DNL iOS] SDK version 4.13.2 (Nov 10, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AA26B14D271948FFBA44D4D06E3B71AA"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Service d’identification des visiteurs </p> </td> 
   <td colname="2"> <p> Added timestamp and Experience Cloud Organization ID to <code> adobe_mc</code> parameter. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Configuration </p> </td> 
   <td colname="2"> <p> Les identifiants IDFA (00000000-0000-0000-0000-000000000000) non valides transmis au SDK via <code>setAdvertisingIdentifier:</code> seront ignorés. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Lien profond </p> </td> 
   <td colname="2"> <p>Lors de l’appel de <code>trackAdobeDeepLink</code>, les variables dotées du préfixe "<code>adb</code>" ou "<code>ctx</code>" sont désormais correctement gérées. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Acquisition </p> </td> 
   <td colname="2"> <p>Les données d’Apple Search Ads sont désormais envoyées avec vos données d’acquisition. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.1 {#section_18C8A7166EFD4E67AC0F7C06DFBBFE6A}

The [!DNL iOS] SDK version 4.13.1 (Oct 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_5B67A6B8B79D4783BA8DCDA7C2ACA765"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Acquisition </p> </td> 
   <td colname="2"> <p> Le kit SDK prend désormais en charge les données d’acquisition personnalisées qui doivent être renvoyées de manière appropriée par les appels de <code>AdobeDataCallback</code>. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> <p> Les paramètres du <span class="keyword">service d’identification des visiteurs</span> sont désormais transmis dans les requêtes <span class="keyword">Target</span> requests via <code>mboxParams</code>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Corrections de bogues**

* Correction d’un problème qui entraînait un blocage lors de la synchronisation du service VisitorID et de l’envoi simultané des accès de suivi à [!DNL Adobe Analytics].
* Fixed an issue that was causing build warnings when targeting [!DNL iOS] versions older than 8.

## Version 4.13.0 {#section_F72A3357994E4887A9F3967F0FBFFCDD}

The [!DNL iOS] SDK version 4.13.0 (Sep 15, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_FD6156E58FF54BA2BEED7398BC780C46"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Messagerie in-app </p> </td> 
   <td colname="2"> <p>Nouvelle fonctionnalité : ajout d’un nouveau type de message permettant d’ouvrir un URI de lien profond. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.12.0 {#section_2AD26AABBB434833AE961C8D71C9AFE8}

The [!DNL iOS] SDK version 4.12.0 (Aug 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_CC3CD01203ED4BDA9BC26427E925C70D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Service d’identification des visiteurs </p> </td> 
   <td colname="2"> <p> Ajout d’une nouvelle méthode permettant d’annexer l’identité du visiteur à une URL donnée afin de transférer l’identité à une mise en œuvre web. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Messagerie in-app </p> </td> 
   <td colname="2"> <p>Correction d’un problème susceptible de provoquer un blocage lors de la spécification de l’attribut « target » sur « _blank » dans une balise HTML dans un message plein écran personnalisé. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.11.0 {#section_3ABABE0F0B964EB48BD482CCE260A13D}

The [!DNL iOS] SDK version 4.11.0 (June 22, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_14B23402BA3B41238F419CA57341B8F5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Méthodes Target </p> </td> 
   <td colname="2"> <p>Vous pouvez maintenant utiliser la nouvelle méthode <span class="keyword">Target</span> suivante : </p> <p> 
     <ul id="ul_93CDE46E39C9431DA9104664F175708B"> 
      <li id="li_903FAC68526B4B7CB6555DC577CE493A"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:requestLocationParameters:callback:</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.10.0 {#section_F0D6D7FD89DE4DF5A121B05FA093CC5B}

The [!DNL iOS] SDK version 4.10.0 (May 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AC447B6E4D55489F803923BF5D1D6653"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Méthodes Target </p> </td> 
   <td colname="2"> <p>Vous pouvez désormais utiliser les nouvelles méthodes <span class="keyword">Target</span> suivantes : </p> <p> 
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:callback:</code> </li> 
      <li id="li_C0FADBB3CEE141AE951CBD49F3A52642"><code> targetThirdPartyID</code> </li> 
      <li id="li_3E1B3725D9EE4ECE9DB0EB1A9E7682A4"><code> targetSetThirdPartyID:</code> </li> 
      <li id="li_659E295610F541819DD7486FC5177012"><code> targetPcID</code> </li> 
      <li id="li_B00ADCF98B6D4694BB7664DB42CDFF99"><code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Méthodes TVJS </p> </td> 
   <td colname="2"> <p>Vous pouvez désormais utiliser les nouvelles méthodes TVJS <span class="keyword">Target</span> suivantes : </p> <p> 
     <ul id="ul_AED76A2B99534CF3A472AC0381B2618C"> 
      <li id="li_AA731652996C4A19A8E02D5D6B8BDC93"><code> targetThirdPartyID</code> </li> 
      <li id="li_744A63A62A8045E49C75F9D7AED5D75E"><code> targetSetThirdPartyID</code> </li> 
      <li id="li_72BC8D96FE0549A695D90B924FA80A02"> <code> targetPcID</code> </li> 
      <li id="li_FB7A9435B9994DB89FA80C2B2218C047"> <code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Adobe Target pour TVML/TVJS </p> </td> 
   <td colname="2"> <p>Vous pouvez désormais utiliser les noms de propriété suivants lors de la configuration de l’élément <code>ADBTarget</code> : </p> <p> 
     <ul id="ul_A0CEE891AE644B47ABD6F7425ACD464D"> 
      <li id="li_2EB0C3CA52014F45BA1EC07703E821B8"><code> id</code> </li> 
      <li id="li_069D996CED534EE88A1EC82684E470D5"><code> total</code> </li> 
      <li id="li_97F290C03FFD46B8A1E78B7BF2021F55"> <code>purchasedProductIds</code> </li> 
      <li id="li_FAAC4BB12DF9491DA21F161711A7707D"> <code> mboxParameters</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.9.0 {#section_DA97D7294B214067A4904B9738450759}

The [!DNL iOS] SDK version 4.9.0 (May 5, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_0B3A0F44549C4DA48C7639048C030065"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Liens profonds </p> </td> 
   <td colname="2"> <p>Vous pouvez mettre en œuvre des liens profonds dans vos applications pour rediriger les utilisateurs vers les destinations des liens web ou des applications. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.6 {#section_0150641B44CF4F6CBE2B21002F8EAB30}

The [!DNL iOS] SDK version 4.8.6 (March 9, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_5175CFFCA30B4DDBACFB23532111CB8A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Suivi des plantages d’application </p> </td> 
   <td colname="2"> <p>The <span class="keyword"> iOS</span> SDK version 4.8.6 contains critical changes that prevent false crashes from being reported. Nous vous recommandons vivement d’installer la version 4.8.6. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.5 {#section_F42EB64F91024748893E89575F2E4487}

The [!DNL iOS] SDK version 4.8.5 (February 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AB225AF04A374421BDD8A972506ACD06"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Exclusion et paramètres de confidentialité </p> </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> iOS</span> SDK 4.8.5, privacy settings set via the <code> setPrivacyStatus</code> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span>, and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.0 {#section_2CF142C8C2D24B529559DAF76F851BBF}

The [!DNL iOS] SDK version 4.8.0 (November 2, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_9DB41F070D66498FACF1A9C135603C7A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Nouvelles méthodes du service d’identification des visiteurs Experience Cloud </td> 
   <td colname="2"> <p>Ajout des nouvelles méthodes suivantes : </p> 
    <ul id="ul_55D8F29ADE3746C484FEC7893FA9EF23"> 
     <li id="li_19F8AF546EEB45EBB5849EA6EB3CE6A3"><code> visitorSyncIdentifiers:authenticationState:</code> </li> 
     <li id="li_1AF1CF62B3ED442D81B438ECBF981583"><code> visitorSyncIdentifierWithType:identifier:authenticationState: </code> </li> 
     <li id="li_C116F0DA8E2A449A8B76637961C2100C"><code> visitorGetIDs</code> </li> 
    </ul> <p>Méthode <code>visitorSyncIdentifiers:identifiers</code> remplacée par <code>visitorSyncIdentifiers:</code> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Nouvelles méthodes TVJS </td> 
   <td colname="2"> <p>Ajout des nouvelles méthodes suivantes : </p> 
    <ul id="ul_4C7F4BB1CF744444ABAA9F13BA98749E"> 
     <li id="li_5DAB089D115843CCA0A53873D6D676F0"><code> visitorSyncIdentifiersAuthenticationState</code> </li> 
     <li id="li_EDE2D1301E8648DB88A18D8C9F6A22C5"><code> visitorSyncIdentifierWithTypeIdentifierAuthenticationState</code> </li> 
     <li id="li_2CCED3C707774597934A2F08BC690B15"><code> visitorGetIDsJs</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Nouvelle variable de configuration JSON ADBMobile </td> 
   <td colname="2"> <p>Ajout de la variable suivante : </p> 
    <ul id="ul_95065BC06FD540D2937D11111799F77F"> 
     <li id="li_7C8C68A41FBA4D098D6803E71D4CCF7A"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.7.0 {#section_B37B1CAF065346E9A2073A06AB7AFEC2}

The [!DNL iOS] SDK version 4.7.0 (October 15, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_3CCA327B859B498D828B2E056A075BEC"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Prise en charge de tvOS </td> 
   <td colname="2"> <p>tvOS est pris en charge pour Apple TV. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Prise en charge d’ATS (App Transport Security) </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> iOS</span> 9, Apple introduced App Transport Security, a set of requirements that conforms to best practices for secure connections. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Méthodes du plug-in PhoneGap</span> </p> </td> 
   <td colname="2"> <p>Ajout des nouvelles méthodes suivantes : </p> <p><b>Méthodes de configuration</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Méthodes de suivi</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">trackPushMessageClickthrough </li> 
     </ul> </p> <p>Nouvelle méthode Target : </p> <p> 
     <ul id="ul_E6A481FCD49D4CF48A4B0636312FCD19"> 
      <li id="li_6604FBB05C4E4988A04CB376D6667C79">targetClearCookies </li> 
     </ul> </p> <p><b>Méthodes d’acquisition</b> </p> <p> 
     <ul id="ul_2015BFF019E64D5685A25E20D4B4A79B"> 
      <li id="li_D450F60189904C43BDAC5D658324AEAA">acquisitionCampaignStartForApp </li> 
     </ul> </p> <p><b>Méthodes Audience Manager</b> </p> <p> 
     <ul id="ul_7D5F339A1A004593AE1D5C26A5A495C5"> 
      <li id="li_2F44037A508D49308F42961FDFB6486C">audienceGetVisitorProfile </li> 
      <li id="li_4F8F43C875384A74ADD48D4197C2ACFD">audienceGetDpuuid </li> 
      <li id="li_B38B6700AF2F4B9FA80CC6774B5B14E7">audienceGetDpid </li> 
      <li id="li_12579B472B404ABAA12DFBDBB22A0C30">audienceSetDpidAndDpuuid </li> 
      <li id="li_2CA997AF9FE241FD961BB0A9B50E14D9">audienceSignalWithData </li> 
      <li id="li_3545CB51B6B7409D8CE2B97E291267E6">audienceReset </li> 
     </ul> </p> <p><b>Méthodes du service d’identification des visiteurs</b> </p> <p> 
     <ul id="ul_746B8A36715D4075B11C42F9FE82F538"> 
      <li id="li_A15AFA632E8C4C8D931CAB48B9A29ADB">visitorGetMarketingCloudId </li> 
      <li id="li_D80DD8DDE6AB4CB6BEE37DAA9BB28A98">visitorSyncIdentifiers </li> 
     </ul> </p> <p><b>Extensions d’application et méthodes Apple Watch</b> </p> <p> 
     <ul id="ul_66B1E1AC4A6D4970B0C77A46EA14ABA7"> 
      <li id="li_1EA7A063FED04E0585D463837A7555CE">setAppGroup </li> 
      <li id="li_5869EAB018C94EE4AC28B3EE62D9F0EF">syncSettings </li> 
      <li id="li_983A98CAEBAD404EBCE1D70CB0B52BA3">initializeWatch </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.6 {#section_D091872501DA49C1A18CDC33C84B8256}

The [!DNL iOS] SDK version 4.6 (September 17, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_084C27B1A75A4A2EB84822242E37ED35"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p> <span class="keyword">Adobe Mobile Services</span> et le SDK <span class="keyword">Adobe Mobile</span> permettent d’envoyer des messages push vers les segments <span class="keyword">Analytics</span>. Le SDK permet également de créer rapidement des rapports sur les utilisateurs qui ont ouvert votre application suite à l’ouverture du message push. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Méthodes d’acquisition </p> </td> 
   <td colname="2"> <p>Permettent aux développeurs de lancer une campagne d’acquisition d’applications, comme si l’utilisateur avait cliqué sur un lien. Ceci s’avère utile pour créer des liens d’acquisition manuels et pour gérer vous-même les redirections de boutiques d’applications. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Postbacks </p> </td> 
   <td colname="2"> <p>Les postbacks permettent d’envoyer les données collectées par le kit SDK à un serveur tiers distinct. En mettant à profit les mêmes déclencheurs et caractéristiques que ceux que vous utilisez pour afficher un message in-app, vous pouvez configurer le SDK pour envoyer des données personnalisées vers une destination tierce. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Identifiants </p> </td> 
   <td colname="2"> <p>Ajout des nouveaux identifiants suivants : </p> <p> 
     <ul id="ul_22EF89556F6B481ABE0D1B9C5EE70B55"> 
      <li id="li_C41F6FAC0B334B89B8B5D1A517CA2301"> <code> setPushIdentifier</code> </li> 
      <li id="li_B7893FB0453340EDB4290BC0B47BF096"><code> setAdvertisingIdentifier</code> </li> 
      <li id="li_85EF5F2B8837497B90F782946283622E"><code>trackPushMessageClickThrough</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Prise en charge de WatchKit pour WatchOS 2 </p> </td> 
   <td colname="2"> <p>Ajout de la prise en charge de WatchKit pour WatchOS 2. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.5 {#section_53DFAF8CFD614F69B3168014EF84DE9F}

The [!DNL iOS] SDK version 4.5 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_A69D0B8DA45348B8A5D6A014126F97C2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Extension iOS</span> </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> iOS</span> SDK version 4.5, a new <span class="keyword"> iOS</span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS</span> extension apps. </p> <p>We strongly recommend that you use the <span class="keyword"> iOS</span> SDK rather than using your own wrapper. </p> <p>Apple fournit un ensemble d’API qui permet à l’application Watch de communiquer avec l’application contenante (envoi de demandes à l’application contenante et réception des réponses). </p> <p>Bien que vous puissiez envoyer les données de suivi en tant que dictionnaire de l’application Watch à l’application contenante et appeler ensuite n’importe quelle méthode de suivi sur l’application contenante pour envoyer les données, cette solution est limitée. </p> <p>Dans la plupart des cas, lorsqu’un utilisateur a recours à l’application Watch, l’application contenante s’exécute en arrière-plan et seules les méthodes <code>TrackActionInBackground</code>, <code>TrackLocation</code>, et <code>TrackBeacon</code> peuvent être appelées en toute sécurité. L’appel d’autres méthodes de suivi interfère avec les données de cycle de vie. Vous devez donc utiliser uniquement ces trois méthodes pour envoyer les données depuis l’application Watch. </p> <p>Even if these three tracking methods meet your requirements, we recommend using the <span class="keyword"> iOS</span> SDK because the SDK for watch app includes all <span class="keyword"> Mobile</span> features except in-app messaging. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.4 {#section_0B7A98761BF0400986C368E154A3B00B}

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Données personnalisées avec des mesures de cycle de vie </p> </td> 
   <td colname="2"> <p>Vous pouvez maintenant inclure des variables de données contextuelles personnalisées aux mesures de cycle de vie. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap</span> </p> </td> 
   <td colname="2"> <p>Les appels <code>trackBeacon</code> et <code>clearCurrentBeacon</code><span class="keyword"> sont maintenant disponibles dans PhoneGap</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.3 {#section_0FD2B2C4F54E4A9E8C6D0CD2F103BB9A}

Date de publication : **24 novembre 2014**

* Nouveau - Intégration d’Adobe Experience Cloud ID
* Journaux de débogage améliorés pour plus de clarté

## Version 4.2 {#section_806710F7720C410DAB46376C0A7A283E}

Date de publication : **16 octobre 2014**

* Nouveau – Capacités de la messagerie in-app.
* Nouveau – L’emplacement du fichier de configuration peut maintenant être spécifié au démarrage de l’application.
* Nouveau – Les points ciblés peuvent maintenant être mis à jour automatiquement sans qu’un nouveau fichier de configuration soit nécessaire.
* New - [!DNL Analytics] calls are now sent as HTTP POST requests.
* Nettoyage des messages du journal, ajout de la consignation de texte quand debugLogging est activé.
* Diverses améliorations des performances et de la stabilité.

## Version 4.1.3 {#section_8D679B676F604E0B9A64748569185368}

Date de publication : **18 septembre 2014**

* Resolved potential crash that could occur if Audience Manager Submit Signal call or [!DNL Target] Load Request call failed due to an unknown network error.

## Version 4.1.2 {#section_6128902E5AE142C4A95D2FB3053188F8}

Date de publication : **5 août 2014**

* Résolution d’un problème de blocage pouvant survenir avec la configuration spécifique de privacyStatus:optunknown et offlineEnabled:false

Date de publication : **4 août 2014**

* Résolution d’un problème en raison duquel l’accès du cycle de vie n’était pas envoyé quand le délai d’expiration du référent était supérieur ou égal à 5 secondes et que le suivi hors ligne était désactivé.

Date de publication : **17 avril 2014**

* Suivi des balises Bluetooth.
* Analyse de l’acquisition d’application.
* Dans les applications acceptant l’horodatage, les blocages comptabilisés sont antidatés à la session correcte.
* Dans les applications acceptant l’horodatage, la session précédente est envoyée dans un accès antidaté vers la session correcte (et plus dans la session précédente).
* Traitement par lot des accès.

## Version 4.0.2 {#section_B78AE82CDFAD44DCAC6D61E0B80BF4C8}

Date de publication : **20 février 2014**

* Résolution d’un problème provoquant un comportement incorrect quand le même élément de média était ouvert en séquence sans fermer l’élément précédent.

## Version 4.0.1 {#section_A6D017015BC742F69B6EE4A461D00FD7}

Date de publication : **30 janvier 2014**

* Résolution d’un problème susceptible d’engendrer l’envoi de plusieurs accès lorsque la base de données était endommagée.
* Résolution d’un problème susceptible de générer de longues moyennes de durée de session si les paramètres temporels d’un périphérique étaient incorrects.

## Version 3.3.2 {#section_6D12768F20C44BA4A0D1EA607D367147}

Date de publication : **30 janvier 2014**

* Résolution d’un problème susceptible de générer de longues moyennes de durée de session si les paramètres temporels d’un périphérique étaient incorrects.

## Version 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

Date de publication : **27 septembre 2013**

[!DNL iOS] SDK 4.x pour les solutions Experience Cloud est désormais disponible, avec les nouvelles fonctionnalités suivantes :

* Améliorations significatives des performances. Tout le traitement est accompli dans les threads en arrière-plan ; le SDK est « thread-safe ».
* Géolocalisation et points ciblés
* Valeur de durée de vie
* Événements minutés
* Gestion des inclusions/exclusions
* Prise en charge d’Audience Manager
* Lifecycle metrics passed to [!DNL Target] as mbox parameters
* Normalisation d’après les règles de traitement et les données contextuelles

## Version 3.3.0 {#section_28FB7CD64D6C49BF93E321587F1E8950}

Date de publication : **23 septembre 2013**

* Ajout de la prise en charge des architectures ARM64 et X64 Simulator (iPhone 5s)

## Version 3.2.1 {#section_3E73A76401664C54B32C7F3BE8BE36E3}

Date de publication : **16 août 2013**

* Optimisation en supprimant le code inutilisé.
* Correction d’un blocage potentiel survenant quand clearVars était utilisé dans un scénario à threads.

## Version 3.2 {#section_A51E0EB26EF246DABE27234C77598D99}

Date de publication : **6 août 2013**

* Prise en charge d’Adobe Audience Manager.
* Lifecycle data is now sent with [!DNL Target] Mbox requests when lifecycle tracking is enabled.

## Version 3.1.8 {#section_849BCD1D4379433D874B8A0E0099E2B1}

Date de publication : **20 juin 2013**

* Fixed a bug introduced in 3.1.7 that was causing issues with lifecycle on devices below [!DNL iOS] 5.0.

## Version 3.1.7 {#section_EC59B76EE3A343D5921E906EB0A8DB49}

Date de publication : **23 mai 2013**

* Ajout d’un code afin d’empêcher l’envoi d’accès de cycle de vie excessifs par le biais de notifications d’emplacement et de notifications Newsstand qui lancent une application.

## Version 3.1.6 {#section_4617D7A41D0841BEBD5829001DC74854}

Date de publication : **18 avril 2013**

* Correction d’un problème en raison duquel le calcul de la durée de la session précédente était parfois erroné.

## Version 3.1.5 {#section_620AA594868F47619A514AF3C1EAC93B}

Date de publication : **21 mars 2013**

* `ADMS_Measurement.visitorID` est maintenant prérenseigné avec la valeur par défaut.

## Version 3.1.4 {#section_B04D1A4858A84A19AA65A57609C9F53F}

Date de publication : **21 février 2013**

* Le paramètre `offlineThrottleDelay` est obsolète car il n’est plus nécessaire en raison de l’optimisation des threads. Ce paramètre existe toujours pour des raisons de compatibilité descendante, mais il n’a plus aucun effet.

## Version 3.1.3 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Date de publication : **novembre 2012**

* Correction d’un problème EXEC_BAD_Access potentiel quand la variable Produits est définie manuellement.
* Correction d’un blocage potentiel de sélecteur incorrect quand une mbox était temporisée.
* Ajout de la prise en charge du suivi des publicités pour la mesure des médias.

## Version 3.1.2 {#section_25C8A6B67AB9487BA5DEB4DB196AE4BC}

Date de publication : **octobre 2012**

* Ajout d’une variable de configuration `lifecycleSessionTimeout` qui permet de spécifier la durée, en secondes, qui doit s’écouler entre les lancements d’une application avant qu’un lancement ne soit considéré comme une nouvelle session.
* Correction d’une erreur dans le module média qui entraînait le remplacement des événements définis par le module par les événements définis sur l’objet de mesure.
* Fixed an issue that caused an exception when allocating an mbox through the [!DNL Target] integration.

## Version 3.1.0 {#section_0F3E939885DE4DF1B7430DF5F5749AD2}

Date de publication : **septembre 2012**

* Ajout de la prise en charge de l’architecture armv7s.
* Suppression de la prise en charge de l’architecture armv6.
* Minimum supported [!DNL iOS] SDK is now 4.3

## Version 3.0.2 {#section_1224693620524D6C8CCAB7707483536E}

Date de publication : **août 2012**

* Les clients qui utilisent le délégué de contrôle vidéo ne verront plus deux événements de fermeture. 
* Correction d’un problème qui entraînait parfois une condition de boucle dans le contrôle vidéo par des accès de fermeture.

## Version 3.0 {#section_D28F56359EC04EDC8521BE93750AE90D}

Date de publication : **juillet 2012**

Version initiale.

**Améliorations**

* Ajout de la fonctionnalité de suivi automatique.
* Diminution de la taille de la bibliothèque à environ 90 K dans la version finale.
* Ajout des méthodes trackEvents et trackAppState.
* Amélioration de la prise en charge et des fonctionnalités des données contextuelles. (Utilisation de données contextuelles recommandée pour toutes les informations envoyées) 
* Simplification du suivi pour qu’une mise en œuvre de suivi puisse être effectuée en 5 minutes.

**Modifications**

* [!DNL AppMeasurement]La classe s’appelle désormais ADMS_Measurement. 
* ADMS_Measurement joue le rôle désormais d’un Singleton.
* Remplacement des méthodes get et set par les variables eVar, prop, list, hier, pev.
* Toutes les variables transmises dans un appel track ne persistent que pour cet appel. 

**Modification des variables suivantes**

| Précédentes (version 2.x) | Actuelles (version 3.x) |
|---|---|
| account | reportSuiteIDs |
| dc | dataCenter |
| pageName | appState |
| contextData | persistentContextData |
| state | geoState |
| zip | geoZip |
| server | appSection |
| debugTracking | debugLogging |
| trackOffline | offlineTrackingEnabled |
| offlineLimit | offlineHitLimit |
| OfflineThrottleDelay | offlineThrottleDelay |

**Nouvel objet des variables suivantes :**

* linkURL (envoyée avec trackLinkURL:)
* linkName (envoyée avec trackLinkURL:)
* linkType (envoyée avec trackLinkURL:)
* lightProfileID (envoyée avec trackLight:)
* lightStoreForSeconds (envoyée avec trackLight:)
* lightIncrementBy (envoyée avec trackLight:)
* trackingServerSecure (trackingServer est utilisée lorsque ssl est activé)

**Suppression des variables suivantes :**

* timestamp
* userAgent
* dynamicVariablePrefix
* visitorNamespace
* pageURL
* pageType
* referrer
* linkLeaveQueryString
* usePlugins
* useBestPractices (gérée par AutoTracking)
* delegate
* retrieveLightData
* deleteLightProfiles
* retrieveLightProfiles

## Version d’iOS précédente (2.x) {#section_5F76C3DA854D4BAEA636A68B3811142B}

The following release notes apply to the 2.x version of [!DNL AppMeasurement] for [!DNL iOS]. Nous conseillons aux clients d’effectuer une mise à niveau vers la version 3.x dès que possible.

## Version 2.1.12 {#section_85C073B86B684D52A14E8038379F56DD}

Date de publication : **avril 2012**

* Ajout de la prise en charge de la mesure des vidéos 
* Correction des problèmes liés aux linktrackvars et données contextuelles.
* Plusieurs améliorations supplémentaires de performances.

## Version 2.1.11 {#section_F0AF2D4E5F504D798EEB95BE8FE61B4C}

Date de publication : **mars 2012**

* Correction d’un problème en raison duquel le suivi hors ligne arrêtait d’envoyer des données dans certains cas.

## Version 2.1.10 {#section_07C24EC83AA94A6AA6AB3DE7E8D6227F}

Date de publication : **février 2012**

* Correction d’un problème qui provoquait une exception EXC_BAD_ACCESS dans certaines circonstances lorsque plusieurs threads tentaient d’effectuer simultanément un appel de suivi.
* Ajout d’un horodatage aux variables utilisées avec les appels de suivi légers (trackLight).

## Version 2.1.8 {#section_ACC6974CE3F741E58786CA8048F04521}

Date de publication : **janvier 2012**

* Performance considérablement accrue de l’unité d’exécution de suivi.
* Déplacement de l’archivage des correspondances hors connexion vers un emplacement qui n’est pas synchronisé avec iCloud pour se conformer aux bonnes pratiques d’iCloud.
* Mise à jour de la bibliothèque au format binaire épais d’Apple afin que vous n’ayez plus à inclure la bibliothèque spécifique pour votre architecture.

## Version 2.1.6 {#section_63B4967C537847C28D33EBB92CC15695}

Date de publication : **novembre 2011**

* Added support for [!DNL iOS] 5.
* [!DNL AppMeasurement] pour [!DNL iOS] a été mis à jour afin de ne plus utiliser la valeur UDID obsolète comme valeur par défaut pour visitorID. Si vous définissez un ID visiteur personnalisé dans votre application (`s.visitorID = @12345`, par exemple), cette modification ne vous concerne pas. Si vous ne définissez pas de visitorID personnalisé, au lieu d’utiliser la valeur UDID pour le visitor ID, un ID aléatoire est généré lors du lancement initial et il est ensuite stocké dans une clé Paramètres par défaut de l’utilisateur. This key is used by [!DNL AppMeasurement] from that point forward. Elle sera également sauvegardée et restaurée au cours du processus de sauvegarde d’application standard.

* Updated calls from the [!DNL iOS] Best Practices plug-in that are not associated with a page view to send hits using trackLink. Cela permet d’éviter que ces accès n’enregistrent des pages vues avec la valeur par défaut du nom « nom de l’application/version ».

## Version 2.1.3 {#section_E39666D780554B7398900C39C285CDB8}

Date de publication : **octobre 2011**

* Amélioration de la gestion des délégués. This fixes an issue that caused the [!DNL iOS] Best Practices Plug-in to crash when bringing the application out of the background.

## Version 2.1.2 {#section_21014073AF804EFC8231047D8847485C}

Date de publication : **septembre 2011**

* Mise à jour de l’en-tête pour permettre l’utilisation des variables prop et eVar 51 à 75.

## Version 2.1.1 {#section_8FB3D7C77C884E2AB982103BF7E3312A}

Date de publication : **août 2011**

* Possibilité d’effectuer des recherches dans les suites de rapports et les mesures lors de l’exécution d’un rapport. 
* Prise en charge des données contextuelles qui pilotent les règles de traitement côté serveur (v15 uniquement).
* Prise en charge des appels de serveur léger (bêta).

