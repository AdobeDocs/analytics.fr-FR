---
description: 'null'
title: Aperçu de l’utilisation de l’appel au serveur
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Aperçu de l’utilisation de l’appel au serveur

## Pourquoi surveiller et alerter sur l’utilisation de l’appel au serveur ? {#section_060C29BF1D00444B85892AD1FCF55290}

L’utilisation de l’appel au serveur d’Adobe Analytics répond à vos demandes de transparence concernant les données d’utilisation d’appel du navigateur et du serveur mobile. Il vous permet d’accéder à :

* un tableau de bord de l’utilisation de l’appel au serveur qui suit les données relatives à votre consommation d’appels au serveur et les compare avec votre limite contractuelle. (**[!UICONTROL Analytics > Admin > Utilisation de l’appel au serveur]**)
* Un type d’alerte d’utilisation des appels au serveur dans le Générateur d’alertes qui vous permet de configurer des alertes pour prévenir les dépassements (**[!UICONTROL Analytics > Composants > Alertes]**).

Les principaux avantages de l’utilisation de l’appel au serveur incluent :

* **Visibilité** de votre consommation d’appels au serveur et des données d’engagement, y compris votre consommation mobile, par rapport à votre limite contractuelle d’utilisation de l’appel au serveur.
* **Alertes** afin d’être notifié en cas de risque ou de dépassement pour vous permettre de vous préparer/d’agir le cas échéant.

Auparavant, vous pouviez accéder aux données mensuelles relatives à la consommation de l’appel au serveur sous **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Facturation]**. Ces données n’étaient mises à jour que six jours après la clôture de la facturation. De plus, les données n’incluaient pas la consommation mobile. Cette fonctionnalité remplacera également le rapport actuel **[!UICONTROL Informations de facturation]** sous **[!UICONTROL Analytics]** > **[!UICONTROL Rapports]** .

## Conditions préalables {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Permissions :** pour accéder au tableau de bord de l’utilisation de l’appel au serveur et au générateur/créateur d’alertes, vous devez être un administrateur Adobe Analytics.
* **Permissions :** les administrateurs peuvent également accorder l’accès à des non-administrateurs. La permission est appelée **[!UICONTROL Utilisation de l’appel au serveur]**. Reportez-vous à [Permission de l’utilisation de l’appel au serveur](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## Terminologie importante {#section_CBA348A039F34563B097CD8890AB358D}

Voici une brève introduction à la terminologie essentielle à l’utilisation de l’appel au serveur :

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Terme </th> 
   <th colname="col2" class="entry"> Définition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Appel au serveur </p> </td> 
   <td colname="col2"> <p>Un appel au serveur, nommé également « Accès » ou « Demande d’image », est une instance dans laquelle des données sont envoyées vers les serveurs Adobe pour traitement. La page vue constitue le type d’appel serveur le plus courant. On parle de page vue lorsqu’un visiteur consulte une page sur votre site web et qu’un appel au serveur est généré vers Adobe. Des informations sont alors collectées, traitées et incluses dans vos mesures de rapport. </p> <p>Il existe d’autres types d’appels au serveur, tels que des liens de sortie et des téléchargements de fichiers. Dans ce cas, des données sont envoyées à Adobe pour traitement, mais elles ne sont pas enregistrées en tant que nouvelle page vue. Même les pages vues « exclues » (c’est-à-dire exclues de vos rapports par une plage d’adresses IP que vous avez configurée, par exemple) sont des appels au serveur, étant donné qu’Adobe les reçoit et les traite. Cependant, elles n’apparaissent jamais dans vos rapports. </p> <p><b>Appel au serveur principal</b> : Requêtes transmises directement par les navigateurs des visiteurs du site web ou l’API d’insertion de données. Inclut les accès principaux (pages vues), les événements personnalisés principaux, les événements de téléchargement principaux et les événements de sortie principaux. </p> <p><b>Appel au serveur secondaire</b> : Copies des appels au serveur principal créées par des balises multi-suite ou copiées/déplacées par une règle VISTA. Si un appel au serveur secondaire a été déplacé (et non copié) vers une suite de rapports différente par une règle VISTA, l’accumulation des appels au serveur secondaire sera déduite des appels au serveur principal. </p> <p><b>Appel au serveur principal mobile</b> </p> <p>Demandes reçues directement de l’un des kits SDK mobiles. Incluez trackAction, trackState, blocages trackApp, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Appel au serveur secondaire mobile</b> </p> <p>Copies des appels au serveur principal créées par des balises multi-suite ou copiées/déplacées par une règle VISTA. Si un appel au serveur secondaire a été déplacé (et non copié) vers une suite de rapports différente par une règle VISTA, l’accumulation des appels au serveur secondaire sera déduite des appels au serveur principal. </p> <p>Remarque : si votre société n’a le droit, en vertu du contrat, qu’aux appels au serveur mobile (principal ou secondaire), votre utilisation web et mobile sera décomptée de votre engagement mobile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Société de facturation (ID de facturation) </p> </td> 
   <td colname="col2"> <p>L’entité légale qui sera facturée pour les appels au serveur. Par exemple : adobe.com. Chaque société de facturation possède un ID de facturation utilisé uniquement pour identifier le client de facturation. De plus, un ID de facturation pourrait être associé à plusieurs organisations Experience Cloud, il ne s’agit pas toujours d’une relation 1:1 entre l’organisation et l’ID de facturation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Société de connexion </p> </td> 
   <td colname="col2"> <p>Une société de facturation peut avoir <a href="https://helpx.adobe.com/fr/analytics/kb/multiple-login-companies.html">plusieurs sociétés de connexion </a>. Une connexion de société est une collecte de suites de rapports utilisée par votre organisation. Certaines organisations sont dotées de plusieurs sociétés de connexion qui s’appliquent à différentes parties de l’organisation. Ceci s’avère particulièrement utile pour les grandes entreprises qui traitent différentes unités opérationnelles qui gèrent des suites de rapports qui leur sont propres. </p> <p>Il s’agit souvent des filiales régionales d’une société. L’exemple suivant montre les sociétés de connexion et leurs suites de rapports associées : </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide : RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us : RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in : RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de : RS4 </li> 
    </ul> <p>Remarque : les données de l’utilisation de l’appel au serveur pour <u>toutes</u> les suites de rapports d’une société de facturation sont visibles par tous les utilisateurs disposant d’une <a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">permission</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organisation Experience Cloud </p> </td> 
   <td colname="col2"> <p>Une organisation est l’entité qui permet à un administrateur de configurer des groupes et des utilisateurs et de contrôler l’authentification unique dans Experience Cloud. L’organisation fonctionne comme une société de connexion qui s’étend sur tous les produits et solutions Experience Cloud. </p> <p>L’organisation correspond le plus souvent au nom de votre société. Toutefois, une société peut détenir plusieurs organisations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Engagement d’appel au serveur </p> </td> 
   <td colname="col2"> <p>Lorsque votre société signe un contrat avec Adobe, l’équipe de vente d’Adobe identifie avec vous les clients, les types d’appels (principal, secondaire, principal mobile, secondaire mobile) et le nombre approximatif d’appels au serveur que vous prévoyez au cours de la durée du contrat. Il s’agit de votre engagement total d’appel au serveur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Période d’utilisation </p> </td> 
   <td colname="col2"> <p>Pour des besoins de surveillance de l’utilisation de l’appel au serveur, cet engagement total d’appel au serveur peut être ventilé en périodes d’utilisation plus petites (trois mois par exemple) pour faciliter la comparaison d’une année à l’autre. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée du contrat </p> </td> 
   <td colname="col2"> <p>La durée du contrat peut s’étendre sur plusieurs années. Disons que votre société s’engage à 6 millions d’appels au serveur pour un contrat de trois ans. Pour des besoins de surveillance de l’utilisation de l’appel au serveur, cette période de trois ans peut être ventilée en périodes d’utilisation plus petites pour faciliter la comparaison d’une année à l’autre. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Permission de l’utilisation de l’appel au serveur {#section_FCC58EB635954A32990D4E67B52B4369}

La permission de l’utilisation de l’appel au serveur est automatiquement accordée aux administrateurs Analytics. Elle permet aux utilisateurs de voir le tableau de bord et de créer des alertes d’appel au serveur. Les administrateurs peuvent choisir d’accorder cette permission à des non-administrateurs.

> [!NOTE] Votre société peut choisir quelles sociétés de connexion ont accès à l’utilisation de l’appel au serveur.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom de la permission </th> 
   <th colname="col3" class="entry"> Accorder une autorisation si vous êtes connecté à Adobe Analytics (compte hérité) </th> 
   <th colname="col4" class="entry"> Accorder une autorisation si vous êtes connecté à Adobe Experience Cloud </th> 
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

