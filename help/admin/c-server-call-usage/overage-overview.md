---
description: 'null'
title: Aperçu de l’utilisation de l’appel au serveur
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Aperçu de l’utilisation de l’appel au serveur

## Pourquoi surveiller et alerter sur l’utilisation de l’appel au serveur ? {#section_060C29BF1D00444B85892AD1FCF55290}

Utilisation des appels Adobe Analytics Server répond à vos demandes de transparence dans les données d’utilisation des appels du navigateur et du serveur mobile. Il vous permet d’accéder aux éléments suivants :

* un tableau de bord de l’utilisation de l’appel au serveur qui suit les données relatives à votre consommation d’appels au serveur et les compare avec votre limite contractuelle. (**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* A Server Call Usage alert type in the Alert Builder that lets you set up alerts to prevent overages (**[!UICONTROL Analytics > Components >Alerts]**)

Les principaux avantages de l’utilisation des appels serveur sont les suivants :

* **Visibilité** des données de consommation et d’engagement d’appels au serveur, y compris la consommation mobile par rapport à votre limite d’utilisation d’appels au serveur contractuel.
* **Alertes** pour vous avertir du risque ou de l’occurrence d’un dépassement et vous préparer à la possibilité de survenance d’un dépassement.

Previously, while you could access monthly server call consumption data under  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Billing]** , this data was only updated 6 days after billing had closed for that month. De plus, les données n’incluaient pas la consommation mobile. Cette fonctionnalité remplacera également le **[!UICONTROL Billing Information]** rapport actuel sous **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** .

## Conditions préalables {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Permissions :** pour accéder au tableau de bord de l’utilisation de l’appel au serveur et au générateur/créateur d’alertes, vous devez être un administrateur Adobe Analytics.
* **Autorisations :** Les administrateurs peuvent accorder l’accès aux non-administrateurs : la permission est appelée **[!UICONTROL Server Call Usage]**. Reportez-vous à [Permission de l’utilisation de l’appel au serveur](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## Terminologie importante {#section_CBA348A039F34563B097CD8890AB358D}

Voici un bref résumé de la terminologie essentielle de l&#39;utilisation des appels serveur :

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Terme </th> 
   <th colname="col2" class="entry"> Définition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Appel serveur </p> </td> 
   <td colname="col2"> <p>Un appel serveur, également appelé "accès" ou "demande d’image", est une instance dans laquelle les données sont envoyées aux serveurs Adobe pour traitement. Le type d’appel serveur le plus courant est un  de page. On parle de page vue lorsqu’un visiteur consulte une page sur votre site web et qu’un appel au serveur est généré vers Adobe. Des informations sont alors collectées, traitées et incluses dans vos mesures de rapport. </p> <p>Il existe d’autres types d’appels serveur, notamment des liens de sortie et des téléchargements de fichiers, dans lesquels les données sont envoyées à Adobe pour traitement, mais elles ne sont pas enregistrées en tant que nouvelle  de page. Même les  de page "exclus" (exclus de vos rapports par une plage d’adresses IP que vous configurez, par exemple) sont des appels serveur car ils sont reçus et traités par Adobe, mais ne s’affichent jamais dans vos rapports. </p> <p><b>Appel</b>du serveur principal : Demandes reçues directement des navigateurs de de site Web ou de l’API d’insertion de données. Inclut les accès principaux ( de page), le personnalisé principal, le de téléchargement principal et le de sortie principal. </p> <p><b>Appel</b>serveur secondaire : Copies des appels serveur principaux créées par des balises multi-suite ou copiées/déplacées par une règle VISTA. Si un appel du serveur secondaire a été déplacé (et non copié) vers une autre suite de rapports par une règle VISTA, les appels secondaires cumulés sont déduits des appels du serveur principal. </p> <p><b>Appel du serveur principal mobile </b> </p> <p>Demandes reçues directement de l’un des kits SDK mobiles. Incluez trackAction, trackState, blocages trackApp, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Appel au serveur secondaire mobile</b> </p> <p>Copies des appels au serveur principal créées par des balises multi-suite ou copiées/déplacées par une règle VISTA. Si un appel du serveur secondaire a été déplacé (et non copié) vers une autre suite de rapports par une règle VISTA, les appels secondaires cumulés sont déduits des appels du serveur principal. </p> <p>Remarque : si votre société n’a le droit, en vertu du contrat, qu’aux appels au serveur mobile (principal ou secondaire), votre utilisation web et mobile sera décomptée de votre engagement mobile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> de facturation (ID de facturation) </p> </td> 
   <td colname="col2"> <p>Entité juridique facturée pour les appels au serveur. Par exemple, adobe.com. Chaque  de facturation comporte un ID de facturation qui est utilisé pour identifier de manière unique le client de facturation. Un ID de facturation peut être lié à plusieurs organisations Experience Cloud ; il n’existe pas toujours de relation 1:1 entre une organisation et un ID de facturation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>de connexion  </p> </td> 
   <td colname="col2"> <p>Une société de facturation peut avoir <a href="https://helpx.adobe.com/fr/analytics/kb/multiple-login-companies.html">plusieurs sociétés de connexion </a>. Un de connexion est un ensemble de suites de rapports utilisées par votre organisation. Certaines organisations disposent de plusieurs de connexion qui s’appliquent à différentes parties de l’organisation. Cela s’avère particulièrement utile pour les grandes entreprises qui traitent de différentes unités commerciales lorsque de nombreuses suites de rapports ne s’appliquent pas aux autres dans le . </p> <p>Souvent, ce sont les filiales régionales d'un . Cet exemple montre les  de connexion et les suites de rapports associées : </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.world : RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us : RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in : RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de : RS4 </li> 
    </ul> <p>Remarque : les données de l’utilisation de l’appel au serveur pour <u>toutes</u> les suites de rapports d’une société de facturation sont visibles par tous les utilisateurs disposant d’une <a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">permission</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organisation Experience Cloud </p> </td> 
   <td colname="col2"> <p>Une organisation est l’entité qui permet à un administrateur de configurer des groupes et des utilisateurs et de contrôler l’authentification unique dans Experience Cloud. L’organisation fonctionne comme une société de connexion qui s’étend sur tous les produits et solutions Experience Cloud. </p> <p>La plupart du temps, une organisation est votre  de nom. Cependant, un peut avoir de nombreuses organisations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Engagement d'appel du serveur </p> </td> 
   <td colname="col2"> <p>Lorsque votre signe un contrat avec Adobe, l’équipe des ventes Adobe identifie avec vous, le client, les types (principal, secondaire, principal mobile, secondaire mobile) et le nombre approximatif d’appels serveur que vous prévoyez d’effectuer au cours de la période du contrat. Il s’agit de votre engagement d’appel au serveur total. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Période d’utilisation </p> </td> 
   <td colname="col2"> <p>Aux fins de la surveillance de l’utilisation des appels serveur, ce total des appels serveur est ventilé en périodes d’utilisation plus petites (3 mois, par exemple) afin de faciliter les comparaisons d’une année à l’autre. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Période du contrat </p> </td> 
   <td colname="col2"> <p>Les périodes de contrat peuvent s’étaler sur plusieurs années. Disons que votre a un engagement d'appel de 6 millions d'appels pour un contrat de 3 ans. Pour des besoins de surveillance de l’utilisation de l’appel au serveur, cette période de trois ans peut être ventilée en périodes d’utilisation plus petites pour faciliter la comparaison d’une année à l’autre. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Permission de l’utilisation de l’appel au serveur {#section_FCC58EB635954A32990D4E67B52B4369}

L’autorisation d’utilisation des appels serveur est automatiquement accordée aux administrateurs d’Analytics. Il permet aux utilisateurs de  le  du et de créer des alertes d’appel serveur. Les administrateurs peuvent choisir d’accorder cette autorisation aux non-administrateurs.

>[!NOTE] Votre société peut choisir quelles sociétés de connexion ont accès à l’utilisation de l’appel au serveur.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom de l’autorisation </th> 
   <th colname="col3" class="entry"> Octroyez l’autorisation si vous êtes connecté à Adobe Analytics (connexion héritée). </th> 
   <th colname="col4" class="entry"> Octroyez l’autorisation si vous êtes connecté à Adobe Experience Cloud. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utilisation des appels au serveur </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Connectez-vous à Analytics via sc.omniture.com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Accédez à <span class="ignoretag"> <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Gestion des utilisateurs </span> &gt; <span class="uicontrol"> Groupes </span> &gt; <span class="uicontrol"> Modifier tous les accès aux rapports </span> &gt; <span class="uicontrol"> Outils Analytics </span> &gt; <span class="uicontrol"> Personnaliser </span> &gt; <span class="uicontrol"> Utilisation de l’appel au serveur </span> </span>. </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Connectez-vous à login.experiencecloud.adobe.com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Cliquez sur <span class="uicontrol">Analytics </span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Accédez à <span class="ignoretag"> <span class="uicontrol"> Produits</span> &gt; <span class="uicontrol"> Profil du produit </span> &gt; <span class="uicontrol"> Permissions </span> &gt; <span class="uicontrol"> Outils Analytics </span> &gt; <span class="uicontrol"> Utilisation de l’appel au serveur </span> </span>. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

