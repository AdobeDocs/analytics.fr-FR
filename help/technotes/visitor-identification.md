---
description: Adobe utilise un cookie pour effectuer le suivi des navigateurs/appareils uniques.
keywords: Analytics Implementation
subtopic: Visitors
title: Identification des visiteurs uniques
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: ht
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Identification des visiteurs uniques

Adobe utilise un cookie pour effectuer le suivi des navigateurs/appareils uniques.

## Classement des identifiants visiteur Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics fournit plusieurs mécanismes permettant d’identifier les visiteurs, répertoriés dans le tableau suivant par ordre de préférence :

| Ordre utilisé | Paramètre de requête (méthode de collecte) | Présent quand |
|---|---|---|
| 1 | vid (s.visitorID) | s.visitorID est défini. |
| 2 | aid (cookie s_vi) | Le visiteur avait un cookie s_vi existant avant le déploiement du service d’identification des visiteurs, ou vous avez configuré une période de grâce d’identification des visiteurs. |
| 3 | mid (cookie AMCV_ défini par le service d’identification des visiteurs d’Experience Cloud) | Le navigateur du visiteur accepte les cookies (propriétaires). |
| 4 | fid (cookie de secours) | Le navigateur du visiteur accepte les cookies (propriétaires). |
| 5 | Adresse IP, Agent utilisateur, Adresse IP de passerelle | Le navigateur du visiteur n’accepte pas les cookies. |

Dans de nombreux scénarios, il se peut qu’il y ait 2 ou 3 identifiants distincts pour un appel ; Analytics utilisera comme identifiant visiteur officiel le premier identifiant présent de cette liste. Par exemple, si vous définissez un identifiant visiteur personnalisé (y compris dans le paramètre de requête « vid »), cet identifiant sera utilisé avant les autres identifiants susceptibles d’être présents pour ce même accès.

> [!NOTE] Chaque identifiant visiteur Analytics est associé à un profil de visiteur sur les serveurs Adobe. Les profils de visiteur sont supprimés après au moins 13 mois d’inactivité, quelle que soit la date d’expiration des cookies d’identifiant de visiteur.

## Identifiant visiteur personnalisé

Vous pouvez mettre en œuvre une méthode personnalisée pour identifier les visiteurs en définissant la variable s.visitorID.

Vous pouvez utiliser un identifiant visiteur personnalisé sur des sites pour lesquels vous avez un moyen unique d’identifier les visiteurs. Il s’agit, par exemple, de l’identifiant généré lorsqu’un utilisateur se connecte à un site web à l’aide de son nom d’utilisateur et de son mot de passe.

Si vous pouvez dériver et gérer les [!UICONTROL identifiants visiteur] de vos utilisateurs, vous pouvez utiliser les méthodes suivantes pour définir l’identifiant :

| Méthode | Description |
|---|---|
| Variable [s.visitorID](../implement/vars/config-vars/visitorid.md) | Si JavaScript est utilisé dans le navigateur, ou si vous utilisez toute autre bibliothèque AppMeasurement, vous pouvez définir l’identifiant visiteur dans une variable de collecte de données. |
| Paramètre de chaîne de requête dans la demande d’image | Elle permet de transmettre l’[!UICONTROL identifiant visiteur] à Adobe via le paramètre de [!UICONTROL chaîne de requête vide] dans une demande d’image codée en dur. |
| API d’insertion de données | Sur les périphériques utilisant des protocoles sans fil qui n’acceptent pas JavaScript, vous pouvez envoyer une publication XML contenant l’élément XML `<visitorid/>` aux serveurs de collecte d’Adobe depuis vos serveurs. |
| Réécriture d’URL et VISTA | Certaines architectures de déploiement prennent en charge l’utilisation de la réécriture d’URL pour gérer l’état de session lorsqu’un cookie ne peut pas être défini. Dans de tels cas, les services d’ingénierie d’Adobe peuvent implémenter une règle [!DNL VISTA] qui recherche la valeur de session dans l’URL de la page, puis la formate et la place dans les valeurs [!UICONTROL visid]. |
>[!CAUTION]
>**Les identifiants visiteur personnalisés doivent être suffisamment granulaires/uniques ** : une mise en œuvre non valide des identifiants visiteur personnalisés peut être à l’origine de données incorrectes et de mauvaises performances en termes de création de rapports. Si l’identifiant visiteur personnalisé n’est pas suffisamment granulaire ou unique, ou s’il est incorrectement défini sur une valeur par défaut commune, telle que la chaîne « NULL » ou « 0 », les accès de nombreux visiteurs différents seront considérés par Adobe Analytics comme un visiteur unique. Cette situation génère des données incorrectes, le nombre de visiteurs étant trop faible et les segments ne fonctionnant pas correctement pour ce visiteur. Un identifiant visiteur personnalisé qui n’est pas suffisamment granulaire empêche également la diffusion correcte des données sur les nœuds de la grappe de rapports Analytics. Dans ce cas, un nœud devient surchargé et ne peut pas traiter les demandes de rapport en temps voulu. Tous les rapports de la suite de rapports vont alors échouer.<br>Il est possible que les identifiants visiteur personnalisés mal implémentés n’aient aucune incidence immédiate sur les performances de création de rapports, étant donné qu’Analytics peut souvent gérer plusieurs mois de données déséquilibrées. Toutefois, avec le temps, une valeur d’identifiant visiteur personnalisé mal mise en œuvre peut devenir problématique au point qu’Analytics doive désactiver le traitement pour les suites de rapports concernées.</br><br>Les implémenteurs doivent suivre la directive selon laquelle une seule valeur d’identifiant visiteur personnalisé ne doit jamais être créditée pour plus de 1 % du trafic de votre suite de rapports. Bien que la recommandation de 1 % soit suffisante pour la plupart des suites de rapports, la limite réelle susceptible d’affecter les performances des rapports peut être inférieure à 1 % pour les suites de rapports très volumineuses.</br>

## Identifiant visiteur Analytics

Lorsqu’un utilisateur visite votre site, le serveur web d’Adobe définit un cookie persistant en l’incluant dans la réponse HTTP au navigateur. Ce cookie est défini sur le domaine de collecte de données spécifié.

Lors de l’envoi d’une demande au serveur de collecte de données d’Adobe, le cookie de l’identifiant visiteur `s_vi` est recherché dans l’en-tête. S’il est présent dans la demande, il est utilisé pour identifier le visiteur. Dans le cas contraire, le serveur génère un identifiant visiteur unique, le définit comme cookie dans l’en-tête de réponse HTTP, puis le renvoie avec la demande. Le cookie est stocké dans le navigateur et renvoyé au serveur de collecte de données lors des visites ultérieures, ce qui permet d’identifier le visiteur au cours de différentes visites.

### Cookies tiers et enregistrements CNAME {#section_61BA46E131004BB2B75929C1E1C93139}

Certains navigateurs, comme Apple Safari, ne stockent plus les cookies définis dans l’en-tête HTTP provenant de domaines qui ne correspondent pas au domaine du site web actuel (il s’agit d’un cookie utilisé dans un contexte tiers ou d’un cookie tiers). Supposons que vous visitiez le site `mysite.com` et que votre serveur de collecte de données soit `mysite.omtrdc.net`. Dans ce cas, le cookie renvoyé dans l’en-tête HTTP en provenance de `mysite.omtrdc.net` risque d’être rejeté par le navigateur.

Pour éviter ce cas de figure, de nombreux clients ont implémenté des enregistrements CNAME pour leurs serveurs de collecte de données dans le cadre d’une [implémentation de cookies propriétaires](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-first-party.translate.html). Si un enregistrement CNAME est configuré pour associer un nom d’hôte sur le domaine du client au serveur de collecte de données (mappage de `metrics.mysite.com` sur `mysite.omtrdc.net`, par exemple), le cookie Identifiant visiteur est stocké, étant donné que le domaine de collecte de données correspond désormais à celui du site web. Cela a pour effet d’augmenter la probabilité de stockage du cookie Identifiant visiteur. Cependant, cette méthode s’accompagne d’une surcharge de travail, dans la mesure où vous devez configurer des enregistrements CNAME et gérer des certificats SSL pour les serveurs de collecte de données.

### Cookies sur les périphériques mobiles {#section_7D05AE259E024F73A95C48BD1E419851}

Lorsque vous effectuez le suivi des périphériques mobiles à l’aide de cookies, vous pouvez utiliser certains paramètres pour modifier le mode d’exécution des mesures. La durée de vie par défaut d’un cookie est de 5 ans, mais vous pouvez utiliser la variable de paramètre de requête CL (`s.cookieLifetime`) pour la modifier. Pour définir l’emplacement du cookie pour les implémentations cname, utilisez la chaîne de requête CDP `s.cookieDomainPeriods`. Si aucune valeur n’est spécifiée, le paramètre par défaut est 2 et l’emplacement par défaut est domain.com. Dans le cas des implémentations qui n’utilisent pas CNAME, l’emplacement du cookie Identifiant visiteur est le domaine 207.net.

## Identity Service

Identity Service remplace le mécanisme d’identification des visiteurs hérité d’Analytics. Il est requis avec la mesure Vidéo – [!UICONTROL Pulsation], avec Analytics pour Target, ainsi qu’avec les services principaux et les intégrations à venir d’Experience Cloud.

Voir [Identity Service](https://marketing.adobe.com/resources/help/fr_FR/mcvid/) pour consulter la documentation produit de ce service.

## Identification des appareils mobiles

La plupart des périphériques mobiles acceptent les cookies des navigateurs. Néanmoins, dans les cas où les périphériques n’acceptent pas les cookies, une autre méthode est utilisée pour identifier de manière unique les périphériques sans fil.

Adobe a identifié un certain nombre d’en-têtes d’identifiant abonné HTTP qui identifient, de façon unique, la majorité des périphériques mobiles. Ces en-têtes comprennent souvent le numéro de téléphone du périphérique (ou une version hachée du numéro) ou d’autres identifiants. La majorité des périphériques actuels possèdent un ou plusieurs en-têtes qui les identifient de façon unique. Tous les serveurs de collecte de données Adobe utilisent automatiquement ces en-têtes au lieu d’un identifiant visiteur.

Dans une demande d’image habituelle, un « 1 » figurant dans le chemin (`/b/ss/rsid/1`) donne l’ordre aux serveurs Adobe de retourner une image gif et de tenter de définir un cookie d’[!UICONTROL identifiant visiteur] persistant (`AMCV_` ou `s_vi`). Néanmoins, si le périphérique est reconnu en tant que périphérique mobile sur la base des en-têtes HTTP, un « 5 » est transmis à la place du « 1 », ce qui indique qu’une image au format wbmp doit être retournée et que notre liste d’en-têtes sans fil reconnus (pas un cookie) doit être utilisée pour identifier le périphérique.

Le tableau suivant répertorie l’ordre des méthodes d’identifiant utilisées sur la base de la valeur du type d’image de retour (« 1 » ou « 5 ») dans le chemin :

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Ordre de la méthode d’identifiant </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>Valeur par défaut : </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">Identifiant visiteur personnalisé </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">En-tête d’identifiant abonné </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> Adresse IP-Agent utilisateur-Adresse IP de passerelle </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>Appareil qui a été identifié en tant qu’appareil sans fil, ou <code> /5/</code> a été envoyé manuellement dans la demande d’image : </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">Identifiant visiteur personnalisé </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">En-tête d’identifiant abonné </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">Adresse IP-Agent utilisateur-Adresse IP de passerelle </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Vous pouvez également transmettre un « 1 » ou un « 5 » dans les demandes d’image manuelles mais gardez à l’esprit que ces codes sont mutuellement exclusifs. De ce fait, toujours transmettre « 5 » ne produit pas de cookie lorsqu’il est pris en charge. Vous pouvez incorporer votre propre mécanisme pour déterminer si un périphérique prend en charge les cookies, et si c’est le cas, transmettre « 1 » dans l’image plutôt que « 5 ». Dans cette situation, l’amélioration en termes de précision est limitée au nombre de périphériques mobiles prenant en charge les cookies.

### En-têtes d’identifiant abonné {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

S’agissant de l’identification des utilisateurs, la méthode de l’identifiant abonné se révèle généralement plus fiable qu’un cookie, compte tenu des problèmes de suppression et d’acceptation des cookies, ainsi que de ceux liés à la gestion des cookies de passerelle.

Vous pouvez améliorer les changements d’identification d’un visiteur ajouté à la liste blanche pour l’opérateur utilisé par vos visiteurs mobiles. Pour accéder à l’identifiant visiteur de l’opérateur, contactez ce dernier pour qu’il ajoute votre domaine à sa liste blanche. Si vous figurez sur la liste blanche de l’opérateur, vous avez également accès aux en-têtes d’identifiant abonné auxquels vous ne pourriez peut-être pas accéder autrement.

La liste ci-dessous d’en-têtes est utilisée pour identifier les périphériques sans fil. L’algorithme de traitement des en-têtes consiste à

1. extraire la clé d’en-tête HTTP (nom de l’en-tête, tel que « X-Up-Calling-Line-ID ») ;
1. supprimer tous les caractères non alphanumériques (A-Z et a-z) ;
1. convertir la clé d’en-tête en minuscules ;
1. comparer la fin de la clé à celles du tableau suivant afin de trouver une correspondance :

| En-tête | Type | Exemple |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid: 595961714786 |
| deviceid | ID | rim-device-id: 200522ae |
| forwardedfor | ID ou adresse IP | X-Forwarded-For: 127.0.0.1 |
| msisdn | ID ou adresse IP | X-Wap-msisdn: 8032618185 |
| clientip | Adresse IP | Client-ip: 10.9.41.2 |
| wapipaddr | Adresse IP | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | Adresse IP | x-huawei-NASIP: 211.139.172.70 |
| userip | Adresse IP | UserIP: 70.214.81.241 |
| ipaddress | Adresse IP | X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | Adresse IP | X-SUBSCRIBER-INFO: IP=10.103.132.128 |

Par exemple, « callinglineid » correspond à « X-Up-Calling-Line-ID » et « nokia-callinglineid ». Le type d’en-tête indique ce qu’il doit contenir. L’ordre de priorité des en-têtes est répertorié ici (si un en-tête « callinglineid » est présent, il est utilisé à la place de « subno »).

Vous pouvez utiliser [les variables dynamiques](../implement/vars/page-vars/dynamic-variables.md) pour extraire des valeurs spécifiques d’un en-tête.

## Méthodes d’identifiant de secours

Si les autres méthodes d’identification des visiteurs échouent, Adobe définit un cookie de secours ou utilise une combinaison de l’adresse IP et de l’agent utilisateur pour identifier le visiteur.

### Méthode d’identification des visiteurs de secours {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement pour JavaScript 1.x et JavaScript H.25.3 (publié en janvier 2013) contient une nouvelle méthode d’identification des visiteurs de secours destinée aux visiteurs dont le navigateur bloque le cookie défini par les serveurs de collecte d’Adobe (appelé `s_vi`). Auparavant, lorsqu’un cookie ne pouvait pas être défini, les utilisateurs étaient identifiés à l’aide d’une combinaison de l’adresse IP et de la chaîne de l’agent utilisateur lors de la collecte des données.

Avec cette mise à jour, si le cookie `s_vi` standard n’est pas disponible, un cookie de secours est créé sur le domaine du site web avec un identifiant unique généré de façon aléatoire. Ce cookie, appelé `s_fid`, est défini avec une date d’expiration de 2 ans et est utilisé comme méthode d’identification de secours. Cette modification devrait entraîner une exactitude accrue de la comptabilisation des visites et des visiteurs dans les cas où le cookie principal (`AMCV_` ou `s_vi`) ne peut pas être défini.

Le total des visites inclut tous les visiteurs qui sont identifiés par le cookie `s_vi` ou à l’aide d’une méthode de secours.

### Adresse IP, Agent utilisateur, Adresse IP de passerelle {#section_104819D74C594ECE879144FCC5DEF4BF}

. Si les cookies `AMCV_`, `s_vi` ou `s_fid` ne peuvent pas être définis, les visiteurs sont identifiés à l’aide d’une combinaison de l’adresse IP et de l’agent utilisateur.
