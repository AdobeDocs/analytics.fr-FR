---
description: valeur nulle
seo-description: valeur nulle
seo-title: Mise en œuvre d'Analytics pour les assistants numériques
title: Mise en œuvre d'Analytics pour les assistants numériques
uuid: c 61 e 6 a 1 a-ec 08-4936-9053-5 f 57223 f 57 ff
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Mise en œuvre d'Analytics pour les assistants numériques

<!-- 

<p>https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper </p> 
<p>https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html </p> 
<p>Ticket: https://jira.corp.adobe.com/browse/AN-157750 </p>

 -->

Grâce aux récentes avancées en matière de cloud computing, d’apprentissage machine et de traitement du langage naturel, les assistants numériques ne sont plus de simples outils rudimentaires et deviennent des objets de la vie quotidienne. Les consommateurs commencent à parler à leurs appareils et s’attendent à ce qu’ils écoutent, comprennent et répondent de façon naturelle, à la manière d’un humain, à des phrases comme « Alexa, allume la lumière dans le salon » ou « OK Google, quel temps fait-il dehors ? ».

À mesure que ces plates-formes s’ancrent dans le marché, les marques peuvent présenter leurs services aux consommateurs avec le même réalisme. Par exemple, les clients peuvent poser les questions suivantes :

* « Alexa, demande à ma voiture quand il faut changer son huile. »
* « Cortana, quel est le solde de mon compte courant ? »
* « Siri, envoie 20 $ à John pour le dîner d’hier soir avec mon application bancaire. »

Ce livre blanc fournit une vue d’ensemble des meilleures façons d’utiliser Adobe Analytics Cloud afin de mesurer et d’optimiser ces types d’expériences.

## Vue d’ensemble de l’architecture de l’expérience digitale {#concept_26AC08D291724223A943C80B1C6F2333}

![](assets/Digital-Assitants.png)

À l’heure actuelle, la plupart des assistants numériques suivent la même architecture de niveau supérieur :

1. **Appareil :** il y a un appareil (tel qu’Amazon Echo ou un téléphone) équipé d’un micro qui permet à l’utilisateur de poser une question.
1. **Assistant numérique :** cet appareil interagit avec le service sur lequel repose l’assistant numérique. C’est en grande partie au niveau de ce service que la magie opère. C’est là que la parole est convertie en intentions que la machine peut comprendre et que les détails de la demande sont analysés. Une fois que l’intention de l’utilisateur est comprise, l’assistant numérique la transmet avec les détails de la demande à l’application qui gère cette demande.
1. **Application :** il peut s’agir d’une application sur le téléphone ou d’une application vocale. L’application a la responsabilité de répondre à la demande. Elle répond à l’assistant numérique qui répond ensuite à l’utilisateur.

## Où mettre en œuvre Analytics {#concept_F53A0566589042658DEA5B86B22C10CB}

L’application est l’un des meilleurs emplacements où Analytics peut être mis en œuvre. L’application reçoit l’[intention](../../implement/c-analytics-digital-assistants/digital-assistants-white-paper.md#section_BB339BDB5C3D40C6B5C426B0E092B48A) et les détails correspondants de la part de l’assistant numérique et décide de la réponse.

L’appel d’Analytics Cloud peut être utile à deux moments différents du cycle de vie d’une demande.

1. Lorsque la demande est envoyée à l’application. Si vous avez besoin de davantage de contexte concernant l’utilisateur avant de répondre à la demande, vous devriez tirer parti de la fonction Audience Manager afin d’obtenir les segments auxquels il appartient.
1. Après que la demande est renvoyée par l’application. Si vous souhaitez uniquement enregistrer ce qui s’est passé avec le client à des fins d’optimisation future, envoyez une demande à Adobe Analytics une fois la réponse renvoyée. De cette façon, vous disposez de l’ensemble du contexte incluant ce qu’était la demande et la façon dont le système a répondu.

## Nouvelles installations {#section_FD63267479DB47C2A081244A3E65A0CC}

Pour certains des assistants numériques, vous obtiendrez une notification lorsque quelqu’un installera la compétence. C’est le cas en particulier en présence d’une authentification. À l’heure actuelle, vous devriez envoyer à Adobe un événement *`Install`* en définissant les données contextuelles à `a.InstallEvent=1`. Notez que cette option n’est pas disponible sur toutes les plates-formes, mais qu’elle est utile pour observer la rétention. L’exemple de code suivant envoie un événement *`Install`*, *`Install Date`* et *`AppID`*.

**Exemple de code**

```
GET 
/b/ss/[rsid]/0?vid=[UserID]&c.a.InstallEvent=1&amp;c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c .OSType=Alexa&pageName=install 
HTTP/1.1 
Host:  
<xref href="https: sc.omtrdc.net="" " format="http"  scope="external">
  sc.omtrdc.net 
 Cache-Control: no-cache 
</xref href="https:>
```

## Plusieurs assistants ou applications {#section_81740741752E4142BE42DA4C9DDEEDF5}

Il est probable que vous développerez des applications pour plusieurs plates-formes. La bonne pratique consiste à inclure un ID d’application dans chaque demande. Vous pouvez le définir dans les données contextuelles `a.AppID`. Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2

**Exemple de code**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1 
Host: [prefix].sc.omtrdc.net 
Cache-Control: no-cache
```

```
 GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Identification de l’utilisateur/du visiteur {#section_7CE70FEB43C44B90954702CA30F87D58}

The Analytics Cloud uses the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) (ECID) service to tie interactions across time to the same person. Most of the digital assistants will return a *`userID`* that you can use to keep the activity for different users separate in the ECID service. Dans la majorité des cas, voici ce que vous devriez transmettre au service ECID. Certaines plates-formes renvoient un *`userID`* qui est supérieur à la limite de 100 caractères autorisée par Analytics. If that is the case, Adobe recommends that you hash the *`userId`* to a fixed-length value using a standard hashing algorithm, such as MD5 or Sha1.

Vous pouvez utiliser le service ECID à cet effet, mais cela n’est bénéfique que si vous essayez de mapper des ECID à travers différents appareils (par exemple, web et assistant numérique). Si votre application est mobile (par exemple, un lien profond), vous devriez utiliser le SDK tel quel et envoyez les informations. L’ *`userID`* peut être joint au service ECID à l’aide de la méthode setCustomerID qui permet un meilleur regroupement des appareils. However, if your app is a service, use the *`userID`* provided by the service as the ECID, as well as setting it in the setCustomerID. Cela vous permet de voir comment les personnes utilisent l’assistant numérique au fil du temps.

**Exemple de code**

```
GET /b/ss/[rsid]/0?vid=[UserID]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Sessions {#section_BA4F996F976043B8993F2F7D24FE27FB}

Les assistants numériques étant conversationnels, ils font souvent appel au concept de session. Par exemple :

**Consommateur :** « OK Google, appelle-moi un taxi. »

**Google :** « Bien sûr, pour quelle heure ? ».

**Consommateur :** « 20 h 30 »

**Google :** « Très bien. Le taxi sera là à 20 h 30. »

Ces sessions sont importantes pour le contexte. Elles permettent de recueillir davantage de détails et rendent les assistants numériques plus naturels.

Lorsque vous mettez Analytics en œuvre sur une conversation, vous devriez effectuer deux actions au démarrage d’une nouvelle session :

1. **Contacter Audience Manager :** obtenir les segments pertinents dont fait partie l’utilisateur de façon à personnaliser la réponse. (Par exemple, cette personne a actuellement droit à la remise multi-canal.)
1. **Envoyer un nouvel événement de lancement ou de session :** quand vous envoyez la première réponse à Analytics, incluez un événement de lancement. Vous pouvez généralement l’envoyer en définissant les données contextuelles de `a.LaunchEvent=1`.

**Exemple de code pour[!DNL Launch, by Adobe]**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Intentions {#section_BB339BDB5C3D40C6B5C426B0E092B48A}

Chacun des assistants numériques possède des algorithmes qui détectent les intentions et les transmettent ensuite à l’application afin qu’elle sache quoi faire. Ces intentions constituent une représentation succincte de la demande.

Par exemple, si un utilisateur dit « Siri, envoie 20 $ à John pour le dîner d’hier soir avec mon application bancaire. », l’intention serait du type *`sendMoney`*.

En envoyant chacune de ces demandes sous la forme d’une eVar, vous pourrez exécuter des rapports de cheminement sur chaque intention pour les applications conversationnelles. Vous devrez également vous assurer que l’application peut gérer les demandes sans intention. Nous recommandons de transmettre *`No Intent Specified`* plutôt que de laisser la valeur vide.

**Exemple de code**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

ou

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Paramètres/emplacements/entités {#section_041CD1730F9E4096BE75DFF2CC810852}

Outre l’intention, l’assistant numérique disposera souvent d’un ensemble de paires valeur/clé détaillant l’intention. Il s’agit d’emplacements, d’entités ou de paramètres. Par exemple :

« Siri, envoie 20 $ à John pour le dîner d’hier soir avec mon application bancaire. » présenterait les paramètres suivants :

* Qui = John
* Montant = 20
* Pourquoi = dîner

Il existe généralement un nombre fini de ces éléments dans votre application. Pour effectuer leur suivi dans Analytics, envoyez-les dans les données contextuelles et mappez ensuite chacun des paramètres à une eVar.

**Exemple de code**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Session {#section_17D69D6B298E46E88E175F62F1ACD831}

Même si toutes les applications ne génèrent pas de revenu, il est important de définir la succès et d’inclure des mesures pour l’évaluer. Adobe Analytics peut mesurer les recettes, les impressions publicitaires et d’autres formes de succès, de même que le comportement de l’utilisateur.

## États d’erreur {#section_E8EFF8D610B24DC899C34E50B058864D}

Parfois, l’assistant numérique fournira à l’application des données qu’elle ne sait pas gérer. Par exemple :

« Siri, envoie 20 sacs de charbon à John pour le dîner d’hier soir avec mon application bancaire. »

Dans ce cas, l’application devrait demander une clarification. De plus, lorsqu’elle répond à une demande de ce type, vous devriez envoyer à Analytics un événement indiquant que l’application a rencontré un état d’erreur ainsi qu’une eVar spécifiant le type de l’erreur.

Veillez à inclure les erreurs où les données en entrée ne sont pas correctes ainsi que celles où l’application a rencontré un problème.

**Exemple de code**

```
GET /b/ss/[rsid]/0/?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent] HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Fonctionnalités des appareils {#section_6770D82A3B0E4AD5A2172A7E67B0DF20}

La plupart des plates-formes n’exposent pas l’appareil auquel l’utilisateur a parlé, mais elles exposent les fonctionnalités de l’appareil comme les interfaces disponibles (par exemple, audio, écran, vidéo, etc.). Ces informations sont utiles en ce qu’elles définissent le type de contenu qui peut être utilisé pour interagir avec vos utilisateurs. Lorsque vous mesurez les interfaces, il est préférable de les concaténer (dans l’ordre alphabétique).

Exemple: `:Audio:Camera:Screen:Video:`

Remarquez les deux-points au début et à la fin. These help when creating segments (for example, give me all interactions with `:Audio:` capabilities).

Fonctionnalités Amazon : [https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)

Fonctionnalités Google : [https://developers.google.com/actions/assistant/surface-capabilities](https://developers.google.com/actions/assistant/surface-capabilities)

## Création de rapports Analytics pour les assistants numériques {#concept_265BC8E99C5545D0A9B9412C11EE58CC}

Une fois votre application d’assistant numérique mise en œuvre, vous pouvez exploiter toute la puissance Adobe Analytics. Vous trouverez ci-dessous juste un aperçu limité des possibilités d’Analytics.

## Surveillance des intentions {#section_6632D9F2EF9045A7A1A4263D3561C78F}

La majorité des applications comprennent plusieurs intentions et activités possibles. You could easily use [!UICONTROL Analysis Workspace] to keep track of the top intents by instances and by users

<!-- 

<p>--- Image of Intents --- </p>

 -->

De cette façon, vous voyez les fonctions les plus fréquemment utilisées et pouvez envisager l’adoption de nouvelles fonctions.

## Demandes avec des erreurs {#section_CF1A79003E784F88A03F4EEF6CDC7A7C}

Vous pourrez surveiller les erreurs afin de déterminer si les utilisateurs rencontrent des problèmes aux mêmes endroits.

<!-- 

<p>--- Image of Errors --- </p>

 -->

## Flux entre les événements {#section_08FA8EBD384D41ED8CA52EFE438C8CD2}

L’une des fonctionnalités les plus puissantes est l’observation du flux d’intention. Il peut vous aider de deux façons. Pour commencer, vous pouvez observer dans une session la façon dont les personnes passent d’une intention à l’autre au fil d’une conversation. Enfin, vous pouvez analyser la manière dont les personnes passent d’une intention à l’autre au cours de périodes plus longues afin de voir l’évolution de leur utilisation de l’application.

## Exemple {#concept_2B13D5E7A8E042D1A4B7BB80BBAACD12}

**Application préinstallée**

<table id="table_70BF4E41D0BE4482BD925FB3A1768CE0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Personne </th> 
   <th colname="col2" class="entry"> Réponse de l’appareil </th> 
   <th colname="col3" class="entry"> Action/intention </th> 
   <th colname="col4" class="entry"> Demande GET </th> 
   <th colname="col5" class="entry"> Données d’analyse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Jouer Spoofify </p> </td> 
   <td colname="col2"> <p> « OK, je joue Spoofify » </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. a. launchevent = 1 &amp; c. Intent = Play &amp; pagename = playapp HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_E80B0BBEBE764023BB9B49FE5F15B918"> 
      <li id="li_9BC2CCABB0ED4246A57C37633666CDE2">Visitor ID </li> 
      <li id="li_1E7F9E979A3D49CE90899CE82C70BCD0">Version de l’application </li> 
      <li id="li_C4BD7653B0FA47F6A3E4F1FF18138F10">Nombre de lancements </li> 
      <li id="li_B7FA47CBD75747E8A8A25E228C90E524">Intention </li> 
      <li id="li_48274BA200704730A22C85FD682AE3B0">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Change de chanson </p> </td> 
   <td colname="col2"> <p> « OK, quelle chanson voulez-vous ? » </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changesong &amp; pagename = askforsong HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_AE8CF669F06547FDA68801F20BD8CBCE"> 
      <li id="li_5A03E41891AF4F37A3BE05BC11F197BC">Visitor ID </li> 
      <li id="li_435FF7DEB169466E8C3F9258C91315D1">Version de l’application </li> 
      <li id="li_AB2B602D9DC74B3D951A0942B6CF8B39">Intention </li> 
      <li id="li_C9F87F3BB7104C9C978BB046C5DB9092">*Liste de lecture vide </li> 
      <li id="li_FB762962468A44A18DF93488EC2CB848">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Joue « My heart will go on » de Céline Dion </p> </td> 
   <td colname="col2"> <p> « OK, je joue “My heart will go on” de Céline Dion » </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplaysong &amp; c. songid = [012345] HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_2AFEE1E928A8499E96B1BC6C5CC21F81"> 
      <li id="li_4BDF8093373A4DA1BB24A608FAC5B7CF">Visitor ID </li> 
      <li id="li_79B4FACCD333472EB9FC1F94B904AFB4">Version de l’application </li> 
      <li id="li_3EDAB6208CB24213A934167BD08BD1AE">Intention </li> 
      <li id="li_C8E6609F9E0A45A8AED15F73374F40B2">Song ID </li> 
      <li id="li_C4D99387C4D748189E15476F5E03BB76">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Change de liste de lecture </p> </td> 
   <td colname="col2"> <p> « OK, quelle liste de lecture voulez-vous ? » </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = askforplaylist HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_913CF31C3EB34BDB819AD54D28F9DE5D"> 
      <li id="li_93036A142FB34A73A95B8AB114EA99C3">Visitor ID </li> 
      <li id="li_F699CDD7866C4EB4BECFF0FAA4689736">Version de l’application </li> 
      <li id="li_6AB1FF7ED6A247FAA8922390410F2F5F">Intention </li> 
      <li id="li_9DF30E2E1958468783FF753D014F1A5F">*Liste de lecture vide </li> 
      <li id="li_B1106A51B8CD49DD8B566B946176F854">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Joue Usher </p> </td> 
   <td colname="col2"> <p> « OK, je joue Usher » </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplayplaylist &amp; c. Playlist = Usher HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_B70E7C9BEFA54C2FA8B7485F9BC7CEE7"> 
      <li id="li_2B0319D20189497D8C9981F871D4FBC4">Visitor ID </li> 
      <li id="li_78C28F34FC7C41589EB111ADCC5A0D66">Version de l’application </li> 
      <li id="li_8ACF819CF80E4E8F942E0903DF75AE33">Intention </li> 
      <li id="li_49F407E43F474356A5F131F82B6C4EB9">Liste de lecture </li> 
      <li id="li_7380EC51B0DE420EB5DD48BCE21B0567">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Arrête la musique </p> </td> 
   <td colname="col2"> <p> *Pas de réponse, la musique s’arrête. </p> </td> 
   <td colname="col3"> <p> Off </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = Off &amp; pagename = turnsoffmusic HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BCA19F2A98CC42788A23E668B260F553"> 
      <li id="li_12A9DA8684B2479D90F3C357AE4F1D15">Visitor ID </li> 
      <li id="li_9E543F7F12D247D0900E5B1BE8EB0F61">Version de l’application </li> 
      <li id="li_9627816FE3594C418EC52DAD42501BCA">Intention </li> 
      <li id="li_5D59C5D8D0F34F5193F592A867AE5639">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Si l’utilisateur doit installer l’application**

<table id="table_C178E3A2C87043A0A2B8C365869102A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Personne </th> 
   <th colname="col2" class="entry"> Réponse de l’appareil </th> 
   <th colname="col3" class="entry"> Action/intention </th> 
   <th colname="col4" class="entry"> Demande GET </th> 
   <th colname="col5" class="entry"> Données d’analyse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Installe Spoofify </p> </td> 
   <td colname="col2"> <p> *Pas de réponse </p> </td> 
   <td colname="col3"> <p> Install </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; amp ; amp ; c. a. installevent = 1 &amp; c. a. installdate = 2017-04-24 &amp; c. a. appid = Spoofify 1.0 &amp; c. ostype = Alexa &amp; c. Intent = Install &amp; pagename = Installer HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_83A7731E5EA84477906AF4BFB3B50F48"> 
      <li id="li_A23A342B0D5745B3854B90ADFDD15EB2">Visitor ID </li> 
      <li id="li_E2F89B771B5F445B995E30C7E76BF2D2">Date </li> 
      <li id="li_03378BC9365F4020B7E28461AFDCB160">Intention </li> 
      <li id="li_6E1ECC9AF55141D1857688DA6A33DEEA">Version du SE </li> 
      <li id="li_A4D06A0DFBC247499D9586F6B76571C4">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Jouer Spoofify </p> </td> 
   <td colname="col2"> <p> « OK, je joue Spoofify » </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. a. launchevent = 1 &amp; c. Intent = Play &amp; pagename = playapp HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_8FCA2B1357A8496DAF563775F019404F"> 
      <li id="li_78E84586A5284164B5B577B68A113394">Visitor ID </li> 
      <li id="li_977915DC425A43BDA69D9F76ADFBAB0C">Version de l’application </li> 
      <li id="li_12725E1D4540485B8A3DB2EC82C6AD4C">Nombre de lancements </li> 
      <li id="li_5B7F4487682241C38071A7037157F473">Intention </li> 
      <li id="li_A6AC81D56BF44E07B2FC0F2740CAB237">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Change de chanson </p> </td> 
   <td colname="col2"> <p> « OK, quelle chanson voulez-vous ? » </p> </td> 
   <td colname="col3"> <p>ChangeSong </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changesong &amp; pagename = askforsong HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C0FCB407A1344527A532A1EAEF0387E4"> 
      <li id="li_8905BCF15F0F493D90B5F1135AEC149C">Visitor ID </li> 
      <li id="li_2D1FAAF35CE24CE49D1AE3F24E4A5A86">Version de l’application </li> 
      <li id="li_A7D11680A9554414878E6CBD03B66DC4">Intention </li> 
      <li id="li_64308721D00441FBB7E6EA6EDF93C100">*Liste de lecture vide </li> 
      <li id="li_A1B2C4E27F9E4B61AAA6373DA8CEB8F2">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Joue « My heart will go on » de Céline Dion </p> </td> 
   <td colname="col2"> <p> « OK, je joue “My heart will go on” de Céline Dion » </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplaysong &amp; c. songid = [012345] HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_5D782E44875144BF96877897E1180D18"> 
      <li id="li_CB5009ED407A4D4ABF3AAFE73133CC66">Visitor ID </li> 
      <li id="li_D15D65E315964E0CBF75A87CF3FCF9B5">Version de l’application </li> 
      <li id="li_055D7621BE1D44BA8B8C50E2E45DA6DF">Intention </li> 
      <li id="li_1D52C0AB9C12483E9CD7DC216D809E44">Song ID </li> 
      <li id="li_5CFB748D02E84050AE216FDC55C680E2">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Change de liste de lecture </p> </td> 
   <td colname="col2"> <p> « OK, quelle liste de lecture voulez-vous ? » </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = askforplaylist HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_7167AE13BBC64CC99E4A81B1FF6C9208"> 
      <li id="li_15554F7C8AC3487797A2FB65C8C1E636">Visitor ID </li> 
      <li id="li_11254FBCFA60436FB705D5FE4C313CC5">Version de l’application </li> 
      <li id="li_4F3AE5B191DB4E73A2C08065A3D75188">Intention </li> 
      <li id="li_7F03D76A26254E65AAEB8E7D647895CA">*Liste de lecture vide </li> 
      <li id="li_DFB50E6BCEAF440D942B30A56CDD1503">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Joue Usher </p> </td> 
   <td colname="col2"> <p> « OK, je joue Usher » </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplayplaylist &amp; c. Playlist = Usher HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BE5815D13CFA48408B4612D220356518"> 
      <li id="li_716EA824A56241A282FD1774A51CF52C">Visitor ID </li> 
      <li id="li_02CC3C2A66E44BB4BA865893F3206A6C">Version de l’application </li> 
      <li id="li_558B15EC8605495B8DC01E644602FC4F">Intention </li> 
      <li id="li_21599097A3B14E368693C77CC7BA8ADD">Liste de lecture </li> 
      <li id="li_70F4254A33704DA18D4D22028A1656E4">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Arrête la musique </p> </td> 
   <td colname="col2"> <p> *Pas de réponse, la musique s’arrête. </p> </td> 
   <td colname="col3"> <p> Off </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0 ? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = Off &amp; pagename = turnsoffmusic HTTP/1.1 
 Hôte : sc. omtrdc. net 
 Cache-Control : no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C623E19496DD466DA299AD610CE5ED1D"> 
      <li id="li_6A7AEF89A74C431C84D107E4F23AE223">Visitor ID </li> 
      <li id="li_B8CFF6AAB2E2476786026A98337589AF">Version de l’application </li> 
      <li id="li_534596CB56B24B729AAA801A7B4D9D31">Intention </li> 
      <li id="li_CA3328E5FFF442BAA0F11C51DF2ED53F">Réponse </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

