---
description: La migration des visiteurs est une procédure par laquelle le cookie d’identifiant visiteur passe d’un domaine à un autre.
keywords: Mise en œuvre d’Analytics
title: Migration des visiteurs
topic-fix: Developer and implementation
feature: Analytics Basics
exl-id: d44628c8-902f-4e60-b819-41d5537407d8
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 62%

---

# Migration des visiteurs

>[!NOTE]
>
>Si vous avez déjà mis en oeuvre le service d’identification des visiteurs Experience Cloud, la période de grâce ne s’applique pas à vous et ne doit pas être activée.

La migration des visiteurs est un processus par lequel le cookie (s_vi) de l’identifiant visiteur est migré d’un domaine à un autre.

La migration des visiteurs vous permet de conserver les cookies d’identification des visiteurs lors du changement des domaines de collecte de données, ce qui peut se produire pour les raisons suivantes :

* Passer de `2o7.net` à `adobedc.net`.

* Vous mettez en œuvre le [service dʼidentification des visiteurs dʼExperience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr) et passez dʼun domaine de collecte de données propriétaire/CNAME à un domaine `adobedc.net`, `2o7.net` ou `omtrdc.net`.

* Passage à une collecte de données propriétaire/CNAME ([Cookies propriétaires)](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=fr).

* Passage d’un CNAME à un autre (changement de domaines).

Une fois la migration des visiteurs configurée, si un utilisateur se rend sur le nouveau domaine sans cookie Identifiant visiteur, le serveur le redirige vers le nom d’hôte de collecte de données antérieur, récupère tout cookie Identifiant visiteur disponible, puis le redirige vers le nouveau domaine. Si aucun identifiant visiteur n’est trouvé sur le nom d’hôte précédent, un nouvel identifiant est généré. Cela ne se produit qu’une seule fois par visiteur.

## Processus de migration des visiteurs  {#process}

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
   <td colname="col1"> <p> <b>Pour commencer</b> : contactez le <a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html"  >service à la clientèle</a> pour communiquer le(s) domaine(s) à faire migrer, ainsi que la période de migration que vous souhaitez activer (30, 60 ou 90 jours). Veillez à inclure les domaines sécurisés et non sécurisés. </p> </td> 
   <td colname="col3"> <p>Créez une liste en utilisant la syntaxe <i>exacte</i> pour les domaines sources et cibles de la migration. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>Les noms d’hôte de migration sont configurés sur le serveur de collecte de données Adobe. Une fois le changement effectué, l’assistance clientèle vous en informera afin que vous puissiez planifier l’étape suivante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>6 heures ou plus après le changement de configuration</b> : mettez à jour les variables <code> s.trackingServer</code> et <code> s.trackingServerSecure</code> dans votre code JavaScript Analytics pour utiliser les nouveaux serveurs de collecte de données. </p> </td> 
   <td colname="col3"> <p>Après avoir apporté cette modification, utilisez lʼ<a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr">Experience Cloud Debugger</a> pour vérifier que la demande dʼimage Analytics est adressée au serveur de collecte de données mis à jour. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Immédiatement après avoir mis à jour le code Analytics</b> : testez votre site afin de vérifier que la redirection vers l’ancien domaine de collecte de données a bien lieu. </p> </td> 
   <td colname="col3"> <p>Utilisez un <a href="../implement/validate/packet-monitor.md"> moniteur de paquets </a> pour vérifier que, lorsque vous accédez à votre site pour la première fois, ou après avoir nettoyé les cookies, deux codes d’état HTTP 302 (redirection) s’affichent avant le code d’état HTTP 200 (OK). S’il manque l’une de ces redirections, contactez immédiatement l’assistance clientèle afin de vous assurer que la migration est correctement configurée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pendant toute la durée de la migration</b> : faites en sorte que l’enregistrement DNS du nom d’hôte précédent reste actif. </p> </td> 
   <td colname="col3"> <p>Le nom d’hôte précédent doit être résolu par DNS, sans quoi la migration des cookies n’aura pas lieu. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Tâche | Description |
|--- |--- |
| Pour commencer : contactez l’assistance clientèle avec le ou les domaines que vous souhaitez migrer et la période de migration que vous souhaitez activer (30, 60 ou 90 jours). Veillez à inclure les domaines sécurisés et non sécurisés. | Créez une liste avec la syntaxe exacte des domaines à partir desquels vous souhaitez migrer.<ul><li>example.112.2o7.net > metrics.example.com</li><li>example.102.112.2o7.net > smetrics.example.com</li></ul>Les noms d’hôte de migration sont configurés sur le serveur de collecte de données Adobe. Une fois le changement effectué, l’assistance clientèle vous en informera afin que vous puissiez planifier l’étape suivante. |
| 6 heures ou plus après le changement de configuration : mettez à jour les variables `s.trackingServer` et `s.trackingServerSecure` dans votre code JavaScript Analytics pour utiliser les nouveaux serveurs de collecte de données. | Après avoir apporté cette modification, utilisez le [débogueur Experience Cloud](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr) pour vérifier que la demande d’image Analytics est adressée au serveur de collecte de données mis à jour. |
| Immédiatement après la mise à jour de votre code Analytics : testez votre site pour vérifier que la redirection vers le domaine de collecte de données précédent a bien lieu. | Utilisez un [moniteur de paquets](../implement/validate/packet-monitor.md) pour vérifier que, lorsque vous accédez à votre site pour la première fois, ou après avoir nettoyé les cookies, deux codes d’état HTTP 302 (redirection) s’affichent avant le code d’état HTTP 200 (OK). S’il manque l’une de ces redirections, contactez immédiatement l’assistance clientèle afin de vous assurer que la migration est correctement configurée. |
| Pour toute la période de migration : laissez l’enregistrement DNS actif pour le nom d’hôte précédent. | Le nom d’hôte précédent doit être résolu par DNS, sans quoi la migration des cookies n’aura pas lieu. |