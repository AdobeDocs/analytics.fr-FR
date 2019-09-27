---
description: Notes de mise à jour cumulées pour la bibliothèque mobile Android.
seo-description: Notes de mise à jour cumulées pour la bibliothèque mobile Android.
seo-title: Android
solution: Analytics,Experience Cloud
subtopic: Notes de mise à jour
title: Android
topic: Développeur et mise en œuvre
uuid: 32232d28-3459-4f78-bb00-ca3163c63461
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Android{#android}

Notes de mise à jour cumulées pour la bibliothèque mobile Android.

>[!NOTE]
>
>Pour trouver la version actuelle de la bibliothèque, activez la journalisation du débogage.

Les téléchargements de bibliothèque mobile sont disponibles sur [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) et sur [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-android-1).

## Version 4.13.4 {#section_E4743079D8E64B9C890180A025C94B44}

The [!DNL Android] SDK version 4.13.4 (Feb 16, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C0197701CB9B45E596818AF0BE5AC4F2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Messagerie in-app </p> </td> 
   <td colname="2"> <p> Correction d’un problème qui empêchait d’utiliser la version correcte de l’application lors de la détermination d’une audience. Ce problème survenait lorsqu’un utilisateur mettait à niveau une application sans relancer la fonctionnalité Cycle de vie. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Cycle de vie </p> </td> 
   <td colname="2"> <p> Correction d’un problème en raison duquel une mise à niveau d’application pouvait ne pas être correctement signalée. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Acquisition </p> </td> 
   <td colname="2"> <p> Correction d’un bogue en raison duquel les liens profonds différés n’étaient pas déclenchés au premier lancement. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.3 {#section_1C235192E9FB46E2A651017C1CF24A7F}

The [!DNL Android] SDK version 4.13.3 (Jan 19, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_5E744C8C9D064E999EB5055A8E3A99C5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Messagerie in-app </p> </td> 
   <td colname="2"> <p> Résolution d’un problème empêchant l’affichage des messages d’alerte sans bouton Clic publicitaire. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> Gestion améliorée de l’accès aux bases de données en lecture seule. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Liens universels </p> </td> 
   <td colname="2"> <p> Résolution d’un bogue entraînant la création différée de liens profonds associés aux données d’acquisition pour déclencher des lancements successifs. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.2 {#section_CEA2FF01EA414A32A8D164D981FBE71F}

The [!DNL Android] SDK version 4.13.2 (Nov 10, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Service d’identification des visiteurs </p> </td> 
   <td colname="2"> <p>Added timestamp and Experience Cloud Organization ID to <code> adobe_mc</code> parameter. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Lien profond </p> </td> 
   <td colname="2"> <p>Lors de l’appel de <code>trackAdobeDeepLink</code>, les variables dotées du préfixe "<code>adb</code>" ou "<code>ctx</code>" sont désormais correctement gérées. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.1 {#section_647C43BA95A3485381AC2E8DEAA6D2E4}

The [!DNL Android] SDK version 4.13.1 (Oct 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_1D1AFD90F8BB4F59869FD417ED9C45AB"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Acquisition </p> </td> 
   <td colname="2"> Le kit SDK prend désormais en charge les données d’acquisition personnalisées qui doivent être renvoyées de manière appropriée par les appels de <code>AdobeDataCallback</code>. </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Acquisition </p> </td> 
   <td colname="2"> Le kit SDK stocke désormais les variables de référent Google Play et les variables personnalisées et les renvoie de manière appropriée dans les appels de <code>AdobeDataCallback</code>. </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> Les paramètres du service d’identification des visiteurs sont désormais transmis dans les requêtes <span class="keyword">Target</span> requests via <code>mboxParams</code>. </td> 
  </tr> 
 </tbody> 
</table>

**Corrections de bogues**

* Correction d’un bogue en raison duquel le délai d’expiration des demandes de données au téléphone était parfois dépassé.

## Version 4.13.0 {#section_03370D8F93AE4B7A81C4B03910086556}

The [!DNL Android] SDK version 4.13.0 (Sept 15, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AACF8B9BE89A4057B0396F487F82CF99"> 
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
  <tr rowsep="1"> 
   <td colname="1"> <p>Suivi des liens profonds </p> </td> 
   <td colname="2"> <p>Nouvelle fonctionnalité : ajout de la possibilité d’activer le suivi des liens profonds tiers différés. </p> <p> 
     <ul id="ul_DA54F09098A546B6A320E6B9F2937DAD"> 
      <li id="li_B483AEBE02F34E21B2CC731FC77448E8"><code> processAdobeDeepLink</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.12.0 {#section_3FBC1C24267141C08A60E288662160D8}

The [!DNL Android] SDK version 4.12.0 (Aug 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_3BDD15254859475CBE5E27870619FF3A"> 
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
 </tbody> 
</table>

## Version 4.11.0 {#section_34B295F3697F4AD6B6A6B8DD70AD1ECA}

The [!DNL Android] SDK version 4.11.0 (June 22, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C3DC3890E81744828DE8946AE8067E1A"> 
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
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> loadRequest</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.10.0 {#section_262928ABA971490EA6B8E277E17BDD89}

The [!DNL Android] SDK version 4.10.0 (May 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_E6B19BD9903A41D9AAF0035CD66756B5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Méthodes Target </td> 
   <td colname="2"> <p>Ajout d’une nouvelle syntaxe et d’un exemple pour la méthode <code>loadRequest</code>. </p> <p>Ajout des nouvelles méthodes <span class="keyword">Target</span> suivantes : </p> <p> 
     <ul id="ul_B32C3B3931764F21948E36384B775642"> 
      <li id="li_3421E7F78F3A4DDA8FF004903FC8C75E">setThirdPartyID </li> 
      <li id="li_0836075699C5480EB3D6B742FCF6D508">getThirdPartyID </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.9.0 {#section_7393D3A5EA61431D9E7C07ECE176D17C}

The [!DNL Android] SDK version 4.9.0 (May 5, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_7D893A6E12554E9CA9AF2B03DA4C1A4B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Exclusion et paramètres de confidentialité </td> 
   <td colname="2"> <p>Vous pouvez mettre en œuvre des liens profonds dans vos applications pour rediriger les utilisateurs vers les destinations des liens web ou des applications. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.3 {#section_9BB3DFBECC434AC6B3D7C18AA9BC895C}

The [!DNL Android] SDK version 4.8.3 (February 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_6DE145BC30154B9FADCE584A9737018D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Exclusion et paramètres de confidentialité </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> Android</span> SDK 4.8.3, privacy settings set via the <code> setPrivacyStatus</code> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span> , and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.0 {#section_18FA091344644B43AA0E226241FF90DC}

The [!DNL Android] SDK version 4.8.0 (November 2, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C47B9AEB2BB649CFA1D5CF04093B497B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Nouvelles méthodes du service d’identification des visiteurs Experience Cloud </td> 
   <td colname="2"> <p>Ajout des méthodes suivantes : </p> 
    <ul id="ul_6B85F8A4826642BEB373225CA760D799"> 
     <li id="li_72B94B8CECB94229827BFCB06671DFC9"><code> syncIdentifer</code> </li> 
     <li id="li_CD0C6B6CEA064FDD8B109E01AEC63F5C"><code> syncIdentifiers</code> </li> 
     <li id="li_620A2D94F97A4451919F0867CA82B25D"><code> getIdentifiers</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Nouvelle variable de configuration JSON ADBMobile </td> 
   <td colname="2"> <p>Ajout de la variable suivante : </p> 
    <ul id="ul_7FF76521C59343A4ABC9573C3CD5DC38"> 
     <li id="li_1381E3EF082B4D7DBD131D8EC62F94D2"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"><span class="keyword"> Méthodes du plug-in PhoneGap</span> </td> 
   <td colname="2"> <p>Ajout des nouvelles méthodes suivantes </p> <p><b>Méthodes de configuration</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Méthodes Target</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">targetClearCookies </li> 
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
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.6.1 {#section_98CC97CF0F0C48F7855130044386845A}

The [!DNL Android] SDK version 4.6.1 (September 24, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_80693083398F472F8A4E7861606E602D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> SDK Android version 4.6.1</span> </p> </td> 
   <td colname="2"> <p>SDK 4.6.0 or earlier supports <span class="keyword"> Android</span> 2.2(API 8) - <span class="keyword"> Android</span> 5.1.1 (API 22) </p> <p>SDK 4.6.1 or later supports <span class="keyword"> Android</span> 2.3(API 9) or later </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.6 {#section_ADF6F871CF3C4E2381464D62DA6E1EB1}

The [!DNL Android] SDK version 4.6 (September 17, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_35D0692698EF49AE8204F2AEB57CABD7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p><span class="keyword">Adobe Mobile Services</span> et le SDK <span class="keyword">Adobe Mobile</span> permettent d’envoyer des messages push vers les segments <span class="keyword">Analytics</span>. Le SDK permet également de créer rapidement des rapports sur les utilisateurs qui ont ouvert votre application suite à l’ouverture du message push. </p> </td> 
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
     <ul id="ul_84AD959FC65C445BB119F69657AB4AF8"> 
      <li id="li_418FD9EE570F491F9704F72AC70EEE8D"><code> setPushIdentifier</code> </li> 
      <li id="li_B350606A504449E5AAE208B1E590E2CA"> <code> submitAdvertisingIdentifierTask</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.5 {#section_6E7614D4AEA24B7E81C4FC094882F062}

The [!DNL Android] SDK version 4.5 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_BF98A1E904EB4314828AC58A2A6E7016"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Extension Android Wearable</span> </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> Android</span> SDK version 4.5, a new <span class="keyword"> Android</span> extension lets you collect data from your <span class="keyword"> Android</span> Wearable app. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.4 {#section_8D7FC183081E4BCFA8ADC33FB55E057C}

The [!DNL Android] SDK version 4.4 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_E8628F3806E24A0FB7157847D97C7B7A"> 
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

## Version 4.3 {#section_789F3DA3DD3146CAA126B303F62D1A1A}

Date de publication : **24 novembre 2014**

* Nouveau - Intégration d’Adobe Experience Cloud ID
* Journaux de débogage améliorés pour plus de clarté
* Résolution des blocages potentiels en cas de vérification des messages in-app

## Version 4.2 {#section_EDF95BA0301C4B54AAE839768917D439}

Date de publication : **16 octobre 2014**

* Nouveau – Capacités de la messagerie in-app.
* Nouveau – L’emplacement du fichier de configuration peut maintenant être spécifié au démarrage de l’application.
* Nouveau – Les points ciblés peuvent maintenant être mis à jour automatiquement sans qu’un nouveau fichier de configuration soit nécessaire.
* New - [!DNL Analytics] calls are now sent as HTTP POST requests.
* Résolution d’un problème en raison duquel des blocages d’application ne faisaient pas toujours l’objet d’un suivi dans certains scénarios.
* Nettoyage des messages du journal, ajout de la consignation de texte quand debugLogging est activé.
* Diverses améliorations des performances et de la stabilité.

## Version 4.1.7 {#section_DD98F9A4F00A457AA79D223CB1113A06}

Date de publication : **4 août 2014**

* Résolution d’un problème en raison duquel l’accès du cycle de vie n’était pas envoyé quand le délai d’expiration du référent était supérieur ou égal à 5 secondes et que le suivi hors ligne était désactivé.

## Version 4.1.6 {#section_B665DF1A4FB249539D73569B52FA8786}

Date de publication : **17 juillet 2014**

* Ajout de protections autour des exceptions survenant si la base de données est endommagée ou n’a pas pu être créée.
* Ajout de protections pour les problèmes survenant quand la configuration ne peut pas être chargée (généralement en raison d’un contexte nul).
* Ajout de protections pour les exceptions pouvant survenir lors de la mise à jour des données contextuelles d’une action temporisée.

## Version 4.1.1 {#section_E5EFA05CEE9D486BA6B5C12B1102C117}

Date de publication : **23 avril 2014**

* Correction d’un problème potentiel pouvant survenir si le suivi du référent est activé et qu’un appel de suivi est invoqué préalablement au cycle de vie.

## Version 4.1.0 {#section_266B62F5B6A44F5F8E6AB8ED1870C4A3}

Date de publication : **17 avril 2014**

* Nouveau - Suivi des balises Bluetooth.
* Nouveau - Les applications dont l’horodatage est activé, les accès en cas de blocage sont antidatés à la session correcte.
* Nouveau - Dans les applications pour lesquelles l’horodatage est activé, la session précédente est envoyée dans un accès antidaté vers la session correcte. (et plus dans la session précédente).
* Nouveau - Traitement par lot des accès.
* Correction du suivi du référent Google Play avec un délai d’attente configurable pour permettre le report des données du référent Google.
* Resolved StrictMode warnings that could occur in specific scenarios.
* Resloved an issue that could very rarely cause the library to lock if certain methods were called in a specific order.

## Version 4.0.4 {#section_DCFAC758872D42F0BF0CCFCDDEA05E41}

Date de publication : **24 février 2014**

* Résolution d’un problème en raison duquel une chronologie du média étendue était lue si un arrêt était invoqué et si une fermeture était invoquée ultérieurement sans aucun appel entre les deux.
* Résolution d’un problème en raison duquel un accès de fermeture de média était envoyé même si le média n’était pas lu pendant n’importe quel laps de temps.

## Version 4.0.3 {#section_FCC3D7D22EBF4A2FA949A4E88AD89F5C}

Date de publication : **20 février 2014**

* Added safety to network code to prevent crash caused by [!DNL Android] bug: https://code.google.com/p/android/issues/detail?id=54072

## Version 4.0.2 {#section_5A7F4D5D9CBD4B79B3B590A2C3F4D0F9}

Date de publication : **30 janvier 2014**

* Résolution d’un problème susceptible d’engendrer l’envoi de plusieurs accès lorsque la base de données était endommagée.
* Résolution d’un problème susceptible de générer de longues moyennes de durée de session si les paramètres temporels d’un périphérique étaient incorrects.

## Version 3.2.5 {#section_A6E60DB42241481DA62F660344128F53}

Date de publication : **30 janvier 2014**

* Ajout de protections contre les bases de données endommagées engendrant la répétition d’accès.
* Ajout d’une durée limite de session maximale afin d’éviter des sessions extrêmement longues lorsque les paramètres temporels du périphérique étaient incorrects.

## Version 4.0.1 {#section_5F58DBABDAA049FE9070E46989B2E9A9}

Date de publication : **14 novembre 2013**

* Résolution d’une mise en forme incorrecte des données trackLocation avec certains paramètres régionaux.

## Version 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

Date de publication : **27 septembre 2013**

[!DNL Android] SDK 4.x pour les solutions Experience Cloud est désormais disponible, avec les nouvelles fonctionnalités suivantes :

* Améliorations significatives des performances. Tout le traitement est accompli dans les threads en arrière-plan ; le SDK est « thread-safe ».
* Géolocalisation et points ciblés
* Valeur de durée de vie
* Événements minutés
* Gestion des inclusions/exclusions
* Prise en charge d’Audience Manager
* Lifecycle metrics passed to [!DNL Target] as mbox parameters
* Normalisation d’après les règles de traitement et les données contextuelles

## Version 3.2.3 {#section_E3464DDC3B4844CF9CC5FC3E35C5C785}

Date de publication : **23 septembre 2013**

* Correction d’un bogue dans Audience Manager en raison duquel les valeurs ou clés nulles n’étaient pas autorisées dans un paramètre.

## Version 3.2.2 {#section_7D631AA2474F4DBAA043703629E3ECC6}

Date de publication : **12 septembre 2013**

* Correction d’un bogue en raison duquel les événements média dans linkTrackEvents n’étaient pas ajoutés à la demande.
* Correction d’une exception potentielle liée à la modification des données contextuelles après leur transmission dans un appel de suivi.

## Version 3.2.1 {#section_D269F9145B2844B6855423A30B125D5C}

Date de publication : **16 août 2013**

* Les connexions SSL utilisent maintenant une validation d’hôte stricte.
* Correction d’un bogue en raison duquel les accès étaient rapidement retentés pendant quelques secondes lorsqu’une connexion réseau était perdue et que offlineTracking était désactivé.

## Version 3.2 {#section_ABD4D192E3FF4240B1451262EAEE4F17}

Date de publication : **6 août 2013**

* Prise en charge d’Adobe Audience Manager.
* Les données du cycle de vie sont maintenant envoyées avec les demandes de mbox Target quand le suivi de cycle de vie est activé.
* Résolution d’un problème en raison duquel SQLite pouvait forcer les curseurs de fermeture, engendrant des entrées de journal superflues.

## Version 3.1.0 {#section_836B4F580B1C436FABD524A91857F882}

Date de publication : **13 juin 2013**

* Mise à jour du stockage hors ligne pour utiliser SQLite.
* Correction d’un bogue en raison duquel la limite hors ligne pouvait être réinitialisée à sa valeur par défaut (1 000).
* Mise à jour de startActivity afin d’accepter un contexte Activité ou Application.
* Correction d’un bogue en raison duquel, si le paramètre lifecycleSessionTimeout était défini sur 0, plusieurs événements de lancement étaient générés dans l’application.

## Version 3.0.8 {#section_51F50CD81C6A40C8BCF62F6F332A0800}

Date de publication : **18 avril 2013**

* Correction d’un problème de codage avec certains paramètres UTF8.

## Version 3.0.7 {#section_0F3FEE2886EB4AB7BA288891FF6B6BCD}

Date de publication : **18 avril 2013**

* Correction d’un problème en raison duquel le calcul de la durée de la session précédente était parfois erroné.
* Les nouveaux ID de visiteur ne dépendront plus de deviceID ni de subscriberID.
* Correction d’un blocage potentiel lors du codage de caractères spéciaux dans les variables.

## Version 3.0.6 {#section_72F3F9CB95BF4076AD882B3270F77B87}

Date de publication : **21 mars 2013**

* Correction d’un problème en raison duquel visitorID ne pouvait pas être lu sans être paramétré au préalable.
* Changement des conventions d’affection de noms dans certains messages du journal des erreurs pour plus de clarté.
* Changement de l’accessibilité de plusieurs classes de base afin d’éviter toute confusion.
* Plusieurs améliorations de performances.

## Version 3.0.5 {#section_0540FF6477D74D1F8274E9340EDE7E16}

Date de publication : **21 février 2013**

* Le paramètre `offlineThrottleDelay` est obsolète car il n’est plus nécessaire en raison de l’optimisation des threads. Ce paramètre existe toujours pour des raisons de compatibilité descendante, mais il n’a plus aucun effet.
* Correction d’un problème de synchronisation potentiel dans le cache des accès hors ligne.
* Clarification du message d’avertissement lors de la définition des variables hiérarchiques supérieures au numéro 5.
* Fixed issue that could cause OSVersion to be misreported on versions of [!DNL Android] &gt; 4.0.
* Plusieurs améliorations de performances.
* Correction d’une exception potentielle qui pouvait être générée par une URL incorrecte.

## Version 3.0.4 {#section_69ADA2ACD9DE436692152C3836B14EEF}

Date de publication : **novembre 2012**

* Ajout d’une variable de configuration `lifecycleSessionTimeout` qui permet de spécifier la durée, en secondes, qui doit s’écouler entre les lancements d’une application avant qu’un lancement ne soit considéré comme une nouvelle session.
* Possibilité de définir la valeur de délai d’expiration pour le calcul de la durée d’une session à l’aide d’un paramètre de configuration `lifecycleSessionTimeout`.
* Correction de problèmes de sécurité.

## Version 3.0.3 {#section_F16E1A36AE3F4CBC92E4925D6DCCFADE}

Date de publication : **octobre 2012**

* Prise en charge du [suivi des campagnes Google Play](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/android/referrer.html).

## Version 3.0.2 {#section_CB24859B34804F9391BA1BF8DF29CC86}

Date de publication : **septembre 2012**

* Correction d’un problème qui entraînait parfois une condition de boucle dans le contrôle vidéo par des accès de fermeture.

## Version 3.0.1 {#section_541CE15B340E414AA018A0EFAEE459F0}

Date de publication : **août 2012**

* Context override parameters are now sent in as `Hashmap<String, Object>` (they were formerly `Hashmap<String, String>`).

## Version 3.0 {#section_2955C0AF3A23476B8CF06C469DE3284C}

Date de publication : **juillet 2012**

Version initiale.

## Version d’Android précédente (1.x) {#section_F2CC015616184D55AC6D6529DFC9A18B}

The following release notes apply to the 1.x version of [!DNL AppMeasurement] for [!DNL Android]. Nous conseillons aux clients d’effectuer une mise à niveau vers la version 3.x dès que possible.

## Version 1.2.3 {#section_5189CCE11EEF4350844B1490D0A9F534}

Date de publication : **mars 2012**

* Correction d’un problème qui provoquait une exception dans certains cas lors du transfert de données à l’aide de données contextuelles.

## Version 1.2.2 {#section_C42925D94F3A429EB1299B96A6EEF6DF}

Date de publication : **février 2012**

Correction d’un problème en raison duquel les appels de suivi de lien doublaient l’encodage URL des valeurs pev1 - pev3.

Ajout d’un horodatage aux variables utilisées avec les appels de suivi légers (trackLight).

## Version 1.2.1 {#section_21845E8A7D0C48B38CB90F0D4C5696AF}

Date de publication : **janvier 2012**

* Added [!DNL Android] 3.x and 4.x compatibility.
* Implemented a UUID for visitor ID on [!DNL Android] devices that do not have SIM cards (For example, Kindle Fire).

## Version 1.2 {#section_EC83BE1F00BF481EA1C74A63E4B90F65}

Date de publication : **juin 2011**

* Mise à jour de la bibliothèque afin d’utiliser l’ID de l’appareil pour la valeur d’ID de visiteur de lorsqu’aucune carte SIM n’est insérée dans l’appareil. Par défaut, la bibliothèque utilise l’ID d’abonné comme ID de visiteur, qui est absent lorsqu’aucune carte SIM n’est insérée.

## Version 1.1.4 {#section_C602EC5C11594669A8797B736D240D2C}

Date de publication : **avril 2011**

* Prise en charge de toutes les tablettes, y compris Xoom.
* Possibilité d’effectuer des recherches dans les suites de rapports et les mesures lors de l’exécution d’un rapport. 
* Prise en charge des données contextuelles qui pilotent les règles de traitement côté serveur (v15 uniquement).
* Prise en charge des appels de serveur léger (bêta).
