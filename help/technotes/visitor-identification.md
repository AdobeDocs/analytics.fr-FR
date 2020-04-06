---
description: Adobe utilise un cookie pour effectuer le suivi des navigateurs/appareils uniques.
keywords: Analytics Implementation
subtopic: Visitors
title: Identification des visiteurs uniques
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Identification des visiteurs uniques

Adobe utilise un cookie pour effectuer le suivi des navigateurs/appareils uniques.

## Classement des identifiants visiteur Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics fournit plusieurs mécanismes permettant d’identifier les visiteurs, Le tableau suivant  les différentes manières d’identifier un dans Analytics (par ordre de préférence) :

| Ordre utilisé | Paramètre  (méthode de collecte) | Présenter quand |
|---|---|---|
| 1 | vid (s.visitorID) | s.visitorID est défini. |
| 2 | aid (cookie s_vi) | Le visiteur avait un cookie s_vi existant avant le déploiement du service d’identification des visiteurs, ou vous avez configuré une période de grâce d’identification des visiteurs. |
| 3 | mid (cookie AMCV_ défini par le service d’identification des visiteurs d’Experience Cloud) | Le navigateur du visiteur accepte les cookies (propriétaires). |
| 4 | fid (cookie de secours) | Le navigateur du visiteur accepte les cookies (propriétaires). |
| 5 | Adresse IP, Agent utilisateur, Adresse IP de passerelle | Le navigateur du visiteur n’accepte pas les cookies. |

Dans de nombreux cas, vous pouvez voir 2 ou 3 identifiants différents lors d’un appel, mais Analytics utilisera le premier identifiant présent dans le tableau précédent comme identifiant de officiel. Par exemple, si vous définissez un identifiant visiteur personnalisé (y compris dans le paramètre de requête « vid »), cet identifiant sera utilisé avant les autres identifiants susceptibles d’être présents pour ce même accès.

>[!NOTE] Chaque identifiant visiteur Analytics est associé à un profil de visiteur sur les serveurs Adobe. Les profils de visiteur sont supprimés après au moins 13 mois d’inactivité, quelle que soit la date d’expiration des cookies d’identifiant de visiteur.

## Identifiant visiteur personnalisé

Vous pouvez mettre en œuvre une méthode personnalisée pour identifier les visiteurs en définissant la variable s.visitorID.

Un ID de personnalisé peut être utilisé sur les sites où vous disposez d’un moyen unique d’identifier les. Il s’agit, par exemple, de l’identifiant généré lorsqu’un utilisateur se connecte à un site web à l’aide de son nom d’utilisateur et de son mot de passe.

Si vous avez la possibilité de dériver et de gérer les utilisateurs [!UICONTROL visitor IDs] de votre site, vous pouvez utiliser les méthodes suivantes pour définir l’ID :

| Méthode | Description |
|---|---|
| Variable [s.visitorID](../implement/vars/config-vars/visitorid.md) | Si JavaScript est utilisé dans le navigateur ou si vous utilisez une autre bibliothèque AppMeasurement, vous pouvez définir l’ID du dans une variable de collecte de données. |
| Paramètre de chaîne de  sur la demande d’image | Vous pouvez ainsi transmettre le fichier [!UICONTROL visitor ID] à Adobe via le [!UICONTROL vid query string] paramètre d’une demande d’image codée en dur. |
| API d’insertion de données | Sur les périphériques utilisant des protocoles sans fil qui n’acceptent pas JavaScript, vous pouvez envoyer une publication XML contenant l’élément XML `<visitorid/>` aux serveurs de collecte d’Adobe depuis vos serveurs. |
| Réécriture d’URL et VISTA | Certaines architectures de déploiement prennent en charge l’utilisation de la réécriture d’URL pour gérer l’état de session lorsqu’un cookie ne peut pas être défini. Dans de tels cas, les services d’ingénierie d’Adobe peuvent implémenter une règle [!DNL VISTA] qui recherche la valeur de session dans l’URL de la page, puis la formate et la place dans les valeurs [!UICONTROL visid]. |
>[!CAUTION]
>**Les identifiants visiteur personnalisés doivent être suffisamment granulaires/uniques ** : une mise en œuvre non valide des identifiants visiteur personnalisés peut être à l’origine de données incorrectes et de mauvaises performances en termes de création de rapports. Si l’identifiant visiteur personnalisé n’est pas suffisamment granulaire ou unique, ou s’il est incorrectement défini sur une valeur par défaut commune, telle que la chaîne « NULL » ou « 0 », les accès de nombreux visiteurs différents seront considérés par Adobe Analytics comme un visiteur unique. Cette situation génère des données incorrectes, le nombre de visiteurs étant trop faible et les segments ne fonctionnant pas correctement pour ce visiteur. Un identifiant visiteur personnalisé qui n’est pas suffisamment granulaire empêche également la diffusion correcte des données sur les nœuds de la grappe de rapports Analytics. Dans ce cas, un nœud devient surchargé et ne peut pas traiter les demandes de rapport en temps voulu. Tous les rapports de la suite de rapports vont alors échouer.<br>Il est possible que les identifiants visiteur personnalisés mal implémentés n’aient aucune incidence immédiate sur les performances de création de rapports, étant donné qu’Analytics peut souvent gérer plusieurs mois de données déséquilibrées. Toutefois, avec le temps, une valeur d’identifiant visiteur personnalisé mal mise en œuvre peut devenir problématique au point qu’Analytics doive désactiver le traitement pour les suites de rapports concernées.</br><br>Les implémenteurs doivent suivre la directive selon laquelle une seule valeur d’identifiant visiteur personnalisé ne doit jamais être créditée pour plus de 1 % du trafic de votre suite de rapports. Bien que la recommandation de 1 % soit suffisante pour la plupart des suites de rapports, la limite réelle susceptible d’affecter les performances des rapports peut être inférieure à 1 % pour les suites de rapports très volumineuses.</br>

## Identifiant visiteur Analytics

Lorsqu’un utilisateur visite votre site, le serveur web d’Adobe définit un cookie persistant en l’incluant dans la réponse HTTP au navigateur. Ce cookie est défini sur le domaine de collecte de données spécifié.

Lors de l’envoi d’une demande au serveur de collecte de données d’Adobe, le cookie de l’identifiant visiteur `s_vi` est recherché dans l’en-tête. S’il est présent dans la demande, il est utilisé pour identifier le visiteur. Si le cookie ne figure pas dans la requête, le serveur génère un ID de unique, le définit comme un cookie dans l’en-tête de réponse HTTP et le renvoie avec la requête. Le cookie est stocké dans le navigateur et renvoyé au serveur de collecte de données au cours des visites suivantes sur le site, ce qui permet d’identifier le entre plusieurs visites.

### Cookies tiers et enregistrements CNAME {#section_61BA46E131004BB2B75929C1E1C93139}

Certains navigateurs, comme Apple Safari, ne stockent plus les cookies définis dans l’en-tête HTTP provenant de domaines qui ne correspondent pas au domaine du site web actuel (il s’agit d’un cookie utilisé dans un contexte tiers ou d’un cookie tiers). Supposons que vous visitiez le site `mysite.com` et que votre serveur de collecte de données soit `mysite.omtrdc.net`. Dans ce cas, le cookie renvoyé dans l’en-tête HTTP en provenance de `mysite.omtrdc.net` risque d’être rejeté par le navigateur.

Pour éviter ce cas de figure, de nombreux clients ont implémenté des enregistrements CNAME pour leurs serveurs de collecte de données dans le cadre d’une [implémentation de cookies propriétaires](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-first-party.translate.html). Si un enregistrement CNAME est configuré pour associer un nom d’hôte sur le domaine du client au serveur de collecte de données (mappage de `metrics.mysite.com` sur `mysite.omtrdc.net`, par exemple), le cookie Identifiant visiteur est stocké, étant donné que le domaine de collecte de données correspond désormais à celui du site web. Cela a pour effet d’augmenter la probabilité de stockage du cookie Identifiant visiteur. Cependant, cette méthode s’accompagne d’une surcharge de travail, dans la mesure où vous devez configurer des enregistrements CNAME et gérer des certificats SSL pour les serveurs de collecte de données.

### Cookies sur les périphériques mobiles {#section_7D05AE259E024F73A95C48BD1E419851}

Lorsque vous effectuez le suivi des périphériques mobiles à l’aide de cookies, vous pouvez utiliser certains paramètres pour modifier le mode d’exécution des mesures. La durée de vie par défaut d’un cookie est de 5 ans, mais vous pouvez utiliser la variable de paramètre de requête CL (`s.cookieLifetime`) pour la modifier. Pour définir l’emplacement du cookie pour les implémentations cname, utilisez la chaîne de requête CDP `s.cookieDomainPeriods`. La valeur par défaut est 2 si aucune valeur n’est spécifiée. et l’emplacement par défaut est domain.com. Pour les implémentations qui n’utilisent pas CNAME, l’emplacement du cookie ID de se trouve dans le domaine 207.net.

## Identity Service

The Identity Service replaces the legacy Analytics visitor ID mechanism, and is required by [!UICONTROL Heartbeat] video measurement, Analytics for Target, and future Experience Cloud core services and integrations.

Voir [Identity Service](https://marketing.adobe.com/resources/help/fr_FR/mcvid/) pour consulter la documentation produit de ce service.

## Identification des appareils mobiles

La plupart des périphériques mobiles acceptent les cookies des navigateurs. Toutefois, lorsque les périphériques n’acceptent pas les cookies, une autre méthode est utilisée pour identifier de manière unique les périphériques sans fil.

Adobe a identifié un certain nombre d’en-têtes d’identifiant abonné HTTP qui identifient, de façon unique, la majorité des périphériques mobiles. Ces en-têtes comprennent souvent le numéro de téléphone du périphérique (ou une version hachée du numéro) ou d’autres identifiants. La majorité des périphériques actuels comporte un ou plusieurs en-têtes qui identifient de manière unique le périphérique. Tous les serveurs de collecte de données Adobe utilisent automatiquement ces en-têtes à la place d’un ID de.

In a typical image request, a &#39;1&#39; in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). Cependant, si le périphérique est reconnu comme un périphérique mobile basé sur les en-têtes HTTP, un &quot;5&quot; est transmis à la place du &quot;1&quot;, ce qui indique qu’une image au format wbmp doit être renvoyée et que notre d’en-têtes sans fil reconnus (et non un cookie) doit être utilisé pour identifier le périphérique.

Le tableau suivant  l’ordre des méthodes d’ID utilisées en fonction de la valeur de type d’image renvoyée (&quot;1&quot; ou &quot;5&quot;) dans le chemin d’accès :

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Ordre de la méthode d’ID </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>Valeur par défaut : </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">Identifiant visiteur personnalisé </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">En-tête d’ID d’abonné </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> Adresse IP-Agent utilisateur-Adresse IP de passerelle </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>Appareil qui a été identifié en tant qu’appareil sans fil, ou <code> /5/</code> a été envoyé manuellement dans la demande d’image : </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">Identifiant visiteur personnalisé </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">En-tête d’ID d’abonné </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">Adresse IP-Agent utilisateur-Adresse IP de passerelle </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Vous pouvez également transmettre un &quot;1&quot; ou un &quot;5&quot; dans les demandes d’image manuelles, mais gardez à l’esprit que ces codes sont mutuellement exclusifs. Par conséquent, le fait de toujours transmettre &quot;5&quot; n’utilise pas de cookie lorsqu’il est pris en charge. Vous pouvez incorporer votre propre mécanisme pour déterminer si un périphérique prend en charge les cookies et, dans l’affirmative, transmettre un &quot;1&quot; dans l’image plutôt qu’un &quot;5&quot;. Dans cette situation, l’amélioration en termes de précision est limitée au nombre de périphériques mobiles prenant en charge les cookies.

### En-têtes d’identifiant abonné {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

La méthode d’ID d’abonné est généralement plus fiable qu’un cookie pour l’identification des utilisateurs en raison de la suppression de cookies, des problèmes d’acceptation de cookies et des problèmes de gestion des cookies de passerelle.

Vous pouvez améliorer les modifications d’identification d’un en ajoutant le blanc de l’opérateur utilisé par vos mobiles. Pour accéder à l’ID d’de l’opérateur, contactez l’opérateur pour ajouter votre domaine à son blanc. Si vous êtes sur le  blanc d’un opérateur, vous avez également accès aux en-têtes d’ID d’abonné auxquels vous ne pourriez peut-être pas accéder autrement.

Le d&#39;en-têtes suivant est utilisé pour identifier les périphériques sans fil. L’algorithme de traitement des en-têtes est le suivant :

1. extraire la clé d’en-tête HTTP (nom de l’en-tête, par exemple, &quot;X-Up-Calling-Line-ID&quot;) ;
1. supprimer tous les caractères non alphanumériques (A-Z et a-z) ;
1. convertir la clé d’en-tête en minuscules
1. comparez la fin de la clé à celles du tableau suivant pour rechercher une correspondance :

| En-tête | Type | Exemple |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID : 8613802423312 |
| subno | ID | x-up-subno : swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID : eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid : a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid : 595961714786 |
| deviceid | ID | rim-device-id : 200522ae |
| redirigé pour | ID ou adresse IP | X-Forwarded-For : 127.0.0.1 |
| msisdn | ID ou adresse IP | X-Wap-msisdn : 8032618185 |
| clientip | Adresse IP | Client-ip : 10.9.41.2 |
| wapipaddr | Adresse IP | X-WAPIPADDR : 10.48.213.162 |
| huaweinasip | Adresse IP | x-huawei-NASIP : 211.139.172,70 |
| userip | Adresse IP | UserIP : 70.214.81.241 |
| ipaddress | Adresse IP | X-Nokia-ipaddress : 212.97.227.125 |
| subscriberinfo | Adresse IP | X-SUBSCRIBER-INFO : IP=10.103.132.128 |

Par exemple, « callinglineid » correspond à « X-Up-Calling-Line-ID » et « nokia-callinglineid ». Le type d’en-tête indique ce qu’il doit contenir. L’ordre de priorité de l’en-tête est répertorié ici (si un en-tête &quot;callinglineid&quot; est présent, il est utilisé à la place de &quot;subno&quot;).

You can use [Dynamic Variables](../implement/vars/page-vars/dynamic-variables.md) to extract specific values from a header.

## Méthodes d’identifiant de secours

Si les autres méthodes d’identification des visiteurs échouent, Adobe définit un cookie de secours ou utilise une combinaison de l’adresse IP et de l’agent utilisateur pour identifier le visiteur.

### Méthode d’identification des visiteurs de secours {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement pour JavaScript 1.x et JavaScript H.25.3 (publié en janvier 2013) contient une nouvelle méthode d’identification des visiteurs de secours destinée aux visiteurs dont le navigateur bloque le cookie défini par les serveurs de collecte d’Adobe (appelé `s_vi`). Auparavant, lorsqu’un cookie ne pouvait pas être défini, les utilisateurs étaient identifiés à l’aide d’une combinaison de l’adresse IP et de la chaîne de l’agent utilisateur lors de la collecte des données.

Avec cette mise à jour, si le cookie `s_vi` standard n’est pas disponible, un cookie de secours est créé sur le domaine du site web avec un identifiant unique généré de façon aléatoire. Ce cookie, appelé `s_fid`, est défini avec une date d’expiration de 2 ans et est utilisé comme méthode d’identification de secours. Cette modification devrait entraîner une exactitude accrue de la comptabilisation des visites et des visiteurs dans les cas où le cookie principal (`AMCV_` ou `s_vi`) ne peut pas être défini.

Le total des visites inclut tous les visiteurs qui sont identifiés par le cookie `s_vi` ou à l’aide d’une méthode de secours.

### Adresse IP, Agent utilisateur, Adresse IP de passerelle {#section_104819D74C594ECE879144FCC5DEF4BF}

. Si les cookies `AMCV_`, `s_vi` ou `s_fid` ne peuvent pas être définis, les visiteurs sont identifiés à l’aide d’une combinaison de l’adresse IP et de l’agent utilisateur.
