---
description: La migration des visiteurs est une procédure par laquelle le cookie d’identifiant visiteur passe d’un domaine à un autre.
keywords: Mise en œuvre d’Analytics
seo-description: La migration des visiteurs est une procédure par laquelle le cookie d’identifiant visiteur passe d’un domaine à un autre.
seo-title: Migration des visiteurs
solution: Analytics
title: Migration des visiteurs
topic: Développeur et mise en œuvre
uuid: af 31928 c -85 d 7-407 f-a 583-0 c 8 f 2852 ceb 3
translation-type: tm+mt
source-git-commit: 85dbc654643f63e30cb20df7e6e9e4cff8660c05

---


# Migration des visiteurs

La migration des visiteurs est une procédure par laquelle le cookie Identifiant visiteur passe d’un domaine à un autre.

La migration des visiteurs vous permet de conserver les cookies d’identification des visiteurs lors du changement des domaines de collecte de données, ce qui peut se produire pour les raisons suivantes :

* Moving from `2o7.net` to `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/)).

* You are implementing the [Experience Cloud Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) and are moving from a CNAME/first-party data collection domain to `2o7.net` or `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/))

* Moving from `2o7.net` or `omtrdc.net` to a cname/first-party data collection ( [First-Party Cookies)](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/).

* Passage d’un CNAME à un autre (changement de domaines).

Une fois la migration des visiteurs configurée, si un utilisateur se rend sur le nouveau domaine sans cookie Identifiant visiteur, le serveur le redirige vers le nom d’hôte de collecte de données antérieur, récupère tout cookie Identifiant visiteur disponible, puis le redirige vers le nouveau domaine. Si aucun identifiant visiteur n’est trouvé sur le nom d’hôte précédent, un nouvel identifiant est généré. Cela ne se produit qu’une seule fois par visiteur. 

## Processus de migration des visiteurs {#section_FF0C5C5CAEF343FFA1892B29311F7160}

Les tâches nécessaires à la migration des visiteurs sont répertoriées dans le tableau suivant :

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tâche </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Pour commencer</b> : contactez le <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="http" scope="external">service à la clientèle</a> pour communiquer le(s) domaine(s) à faire migrer, ainsi que la période de migration que vous souhaitez activer (30, 60 ou 90 jours). Veillez à inclure les domaines sécurisés et non sécurisés. </p> </td> 
   <td colname="col3"> <p>Créez une liste en utilisant la syntaxe <i>exacte</i> pour les domaines sources et cibles de la migration. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>Les noms d’hôte de migration sont configurés sur le serveur de collecte de données Adobe. Une fois le changement effectué, le service à la clientèle vous en informera afin que vous puissiez planifier l’étape suivante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>6 heures ou plus après le changement de configuration</b> : mettez à jour les variables <code>s.trackingServer</code> et <code>s.trackingServerSecure</code> dans votre code JavaScript Analytics pour utiliser les nouveaux serveurs de collecte de données. </p> </td> 
   <td colname="col3"> <p>After you make this change, use a <a href="../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258" format="dita" scope="local"> Packet Analyzer</a> to verify that the Analtyics image request is going to the updated data collection server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Immédiatement après avoir mis à jour le code Analytics</b> : testez votre site afin de vérifier que la redirection vers l’ancien domaine de collecte de données a bien lieu. </p> </td> 
   <td colname="col3"> <p>Utilisez un <a href="../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258" format="dita" scope="local"> Analyseur de paquets</a> pour vérifier que lorsque vous accédez à votre site pour la première fois, ou après avoir effacé les cookies, deux codes d'état HTTP 302 (redirection) sont répertoriés avant le code d'état HTTP 200 (OK). S’il manque l’une de ces redirections, contactez immédiatement le service à la clientèle afin de vous assurer que la migration est correctement configurée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pendant toute la durée de la migration</b> : faites en sorte que l’enregistrement DNS du nom d’hôte précédent reste actif. </p> </td> 
   <td colname="col3"> <p>Le nom d’hôte précédent doit être résolu par DNS, sans quoi la migration des cookies n’aura pas lieu. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables visitorMigrationKey et visitorMigrationServer obsolètes {#section_32FCEE2575944D039EA0FEBFB5814259}

As of March 2013, the `visitorMigrationKey`, `visitorMigrationServer`, and `visitorMigrationServerSecure` data collection variables are deprecated and no longer used. Les données contenues précédemment dans ces variables seront stockées dans les serveurs Adobe afin d’offrir un niveau de sécurité accru.
