---
description: La plupart des périphériques mobiles acceptent les cookies des navigateurs. Néanmoins, dans les cas où les périphériques n’acceptent pas les cookies, une autre méthode est utilisée pour identifier de manière unique les périphériques sans fil.
keywords: Mise en œuvre d’Analytics
seo-description: La plupart des périphériques mobiles acceptent les cookies des navigateurs. Néanmoins, dans les cas où les périphériques n’acceptent pas les cookies, une autre méthode est utilisée pour identifier de manière unique les périphériques sans fil.
seo-title: Identification des périphériques mobiles
solution: Analytics
title: Identification des périphériques mobiles
topic: Développeur et mise en œuvre
uuid: 22587 dd 1-cead -485 b-a 4 d 8-94 dfb 7 cd 9662
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Identification des périphériques mobiles

La plupart des périphériques mobiles acceptent les cookies des navigateurs. Néanmoins, dans les cas où les périphériques n’acceptent pas les cookies, une autre méthode est utilisée pour identifier de manière unique les périphériques sans fil.

Adobe a identifié un certain nombre d’[en-têtes d’identifiant abonné](../../../implement/js-implementation/c-unique-visitors/visid-mobile.md#section_60D6EAC0D16945A89DD5A7ADF3B8298D) HTTP qui identifient, de façon unique, la majorité des périphériques mobiles. Ces en-têtes comprennent souvent le numéro de téléphone du périphérique (ou une version hachée du numéro) ou d’autres identifiants. La majorité des périphériques actuels possèdent un ou plusieurs en-têtes qui les identifient de façon unique. Tous les serveurs de collecte de données Adobe utilisent automatiquement ces en-têtes au lieu d’un identifiant visiteur.

In a typical image request, a '1' in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). Néanmoins, si le périphérique est reconnu en tant que périphérique mobile sur la base des en-têtes HTTP, un « 5 » est transmis à la place du « 1 », ce qui indique qu’une image au format wbmp doit être retournée et que notre liste d’en-têtes sans fil reconnus (pas un cookie) doit être utilisée pour identifier le périphérique.

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
   <td colname="col2"> <p>Valeur par défaut :  </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">Identifiant visiteur personnalisé </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">En-tête d’identifiant abonné </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> Adresse IP-Agent utilisateur-Adresse IP de passerelle </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>Périphérique qui a été identifié en tant que périphérique sans fil, ou <code>/5/</code> a été envoyé manuellement dans la demande d’image : </p> 
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

## En-têtes d’identifiant abonné {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

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

Vous pouvez utiliser [les variables dynamiques](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262) pour extraire des valeurs spécifiques d’un en-tête.
