---
description: Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.
keywords: Implémentation d'Analytics ; faq ; questions fréquentes ; expiration d'evar ; la visibilité des événements personnalisés ; timestamp ; période de grâce d'identification des visiteurs ; identifiant visiteur ; Identifiant visiteur Experience Cloud ; identifiant visiteur Analytics ; dtm ; pulsation ; cookies ; serveur de suivi ; performances ; javascript ; collecte de données ; s_ code version ; s_ code debug ; suivre les types de lien ; track vidéo ; suivre les applications mobiles ; cookie direct ; certificat ssl ; expiration de certification ; expiration du certificat ; modules externes ; API d'insertion de données ; 500 erreur ; 500 ; Gérer les utilisateurs ; gérer le groupe ; utilisateurs ; groupes
seo-description: Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.
seo-title: FAQ sur la mise en œuvre d’Analytics
solution: Analytics
title: FAQ sur la mise en œuvre d’Analytics
topic: Développeur et mise en œuvre
uuid: 983 d 759 a-c 4 f 2-4021-84 c 8-0486 dbb 951 b 8
translation-type: tm+mt
source-git-commit: 0143edbcbab3450f6932367f51e9e4c79bc1ae63

---


# FAQ sur la mise en œuvre d’Analytics

Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.

<table id="table_91790388C2DE4C5E8AEF0B9981AFFE27"> 
 <tbody> 
  <tr> 
   <td> <b>Question</b> </td> 
   <td> <b>Réponse</b> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Comment gérer les groupes et les utilisateurs Analytics ? </p> </td> 
   <td colname="col3"> <p>For information about managing users and groups, refer to <a href="https://marketing.adobe.com/resources/help/en_US/reference/user_management.html" format="html" scope="external"> User and Product Management </a> in the Adobe Experience Cloud help. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Expiration des eVar. Pourquoi les eVar sont-elles définies sur la valeur « Aucun » ou « Néant » dans les rapports ? </p> </td> 
   <td colname="col3"> <p> <span class="uicontrol"> Expire après</span> indique une période, ou un événement, à l’issue de laquelle (ou duquel) la valeur eVar arrive à expiration (elle ne reçoit plus de crédit pour les événements de succès). Si un événement de succès se produit après l’expiration de l’eVar, la valeur Aucun reçoit le crédit pour l’événement (aucune valeur eVar n’était active). Si vous sélectionnez un événement comme valeur d’expiration, la variable arrive uniquement à expiration si l’événement a lieu. Dans le cas contraire, la variable n’expire jamais. <a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html" format="https" scope="external"> [Plus...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Visibilité des événements personnalisés. Pourquoi les événements personnalisés n’apparaissent-ils pas dans le menu des rapports ? </p> </td> 
   <td colname="col3"> <p>Dans la colonne Visibilité, vous pouvez masquer les mesures (intégrées) standard, les événements personnalisés et les événements intégrés dans le menu, les sélecteurs de mesure, le créateur de mesures calculées et le créateur de segments. Ce paramètre n’a aucun impact sur la collecte des données pour cette mesure ou cet événement ; il affecte uniquement sa visibilité dans l’interface utilisateur. <a href="https://marketing.adobe.com/resources/help/en_US/reference/metric-visibility.html" format="https" scope="external"> [Plus...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Horodatages. De quoi dois-je tenir compte avant de modifier les paramètres d’horodatage ? </p> </td> 
   <td colname="col3"> <p>Avec l’option Horodatages (facultatif), vous pouvez combiner des données horodatées et non horodatées sans aucune perte de données. Les données hors ligne horodatées générées par un appareil mobile peuvent être combinées à des données en direct non horodatées d’une page Web, ou intégrées aux données d’une plateforme quelconque à l’aide d’un appel d’horodatage côté client. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/timestamps-overview.html" format="https" scope="external"> [Plus...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Identifiant visiteur. Comment fonctionne la période de grâce de l’identifiant visiteur et comment est-elle activée ? </p> </td> 
   <td colname="col3"> <p>Si plusieurs fichiers JavaScript envoient des données à la même suite de rapports ou si vous avez recours à d’autres technologies sur votre site, par exemple la mesure vidéo Flash, nous vous recommandons de configurer une période de grâce. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html" format="https" scope="external"> [Plus...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Identifiant visiteur. Quelle est la différence entre l’identifiant visiteur Experience Cloud et l’identifiant visiteur Analytics ? </p> </td> 
   <td colname="col3"> <p>Le service d'identité attribue un identifiant persistant unique à tous les visiteurs de votre site. Avec cet ID, les visiteurs et leurs données peuvent être partagés dans les solutions Experience Cloud. En outre, cet identifiant peut remplacer ou fonctionner avec des identifiants spécifiques à une solution, tel l’identifiant visiteur Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-overview.html" format="https" scope="external"> [Plus...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Identifiant visiteur. Comment est défini l’identifiant visiteur si les cookies sont bloqués ? </p> </td> 
   <td colname="col3"> <p>Si le cookie s_vi standard n’est pas disponible, un cookie de secours est créé sur le domaine du site web avec un identifiant unique généré de façon aléatoire. Ce cookie, appelé s_fid, est défini avec une date d’expiration de 2 ans et est utilisé comme méthode d’identification de secours. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html" format="https" scope="external"> [Plus...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Dynamic Tag Management. Pourquoi ma règle de Dynamic Tag Management se déclenche-t-elle ? </p> </td> 
   <td colname="col3"> <p>Si votre règle basée sur un événement n’est pas déclenchée, le problème est probablement lié au sélecteur ou à la condition de la règle. Dans votre site, recherchez l’élément sur lequel l’action d’événement se produit, cliquez dessus avec le bouton droit, puis sélectionnez Contrôler l’élément. Examinez le script mis en surbrillance dans la zone qui s’ouvre, puis vérifiez que vous ciblez l’élément adéquat. <a href="https://marketing.adobe.com/resources/help/en_US/dtm/c_Troubleshooting.html" format="https" scope="external"> [Plus...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Comment mettre en œuvre le suivi des vidéos Pulsation ? </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/" format="https" scope="external">Cette section</a> comprend des instructions sur le téléchargement des SDK de pulsation vidéo et des guides à l’intention des développeurs concernant votre plateforme. Quand vous téléchargez le SDK, veillez à télécharger également le guide de développeur qui se trouve dans le dossiers docs, car il contient des instructions de mise en œuvre spécifiques pour la pulsation vidéo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Comment ajouter des cookies au sous-domaine approprié ? </p> </td> 
   <td colname="col3"> <span class="varname"> La </span> variable cookiedomainperiods détermine le domaine sur lequel les cookies s_ cc et s_ sq Analytics sont définis en établissant le nombre de points contenus dans le domaine de l'URL de la page. Elle est également utilisée par certains modules externes pour déterminer le domaine correct afin de définir le cookie du module externe. Voir [Variables de configuration] (/help/implementation/js-implementation/c-variables/configuration-variables. md) </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Serveur de suivi. Comment renseigner correctement mon serveur de suivi ? </p> </td> 
   <td colname="col3"> <p>Quand vous configurez une mise en œuvre pour envoyer des données aux serveurs Adobe Analytics, vous devez les envoyer à l’emplacement approprié. Sinon, le nombre des visiteurs risque d’être gonflé ou des données perdues. <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"> [Plus...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Performances. Un échec de chargement du fichier JavaScript Adobe externe (en raison d’un problème de connexion Internet, d’un proxy, d’un pare-feu ou d’une interruption de service chez Adobe) peut-il affecter les performances ? </p> </td> 
   <td colname="col3"> <p>Non. Le fichier JavaScript n’est pas hébergé sur les serveurs Adobe. Par conséquent, une panne des serveurs Adobe n’affecte pas l’exécution du fichier JavaScript. Si vous avez recours à Dynamic Tag Management, le fichier JavaScript est hébergé par Akamai ou sur un serveur à un emplacement déterminé par les clients. </p> <p>Voir <i>Dynamic Tag Management va-t-elle réduire les performances de mon site web ?</i> dans les <a href="https://marketing.adobe.com/resources/help/en_US/dtm/faq.html" format="https" scope="external">questions fréquentes sur Dynamic Tag Management </a>. </p> <p>En outre, si vous ne vous fiez pas au réseau de diffusion de contenu d’Akamai, vous pouvez héberger votre propre fichier central de Dynamic Tag Management. Voir <a href="https://marketing.adobe.com/resources/help/en_US/dtm/?f=deployment" format="https" scope="external">Code incorporé et options d’hébergement </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Performances. Le chargement du fichier JavaScript Adobe externe peut-il réduire les performances ? </p> </td> 
   <td colname="col3"> <p> Le fichier JavaScript est mis en cache dans le navigateur du visiteur après son chargement initial. En règle générale, il n’est pas téléchargé plus d’une fois par session. Il n’est pas téléchargé sur chaque page, même s’il est utilisé par toutes les pages du site. Sur la plupart des sites Web, les utilisateurs visualisent, en moyenne, plus de quelques pages par session. Dès lors, le transfert de code JavaScript utilisé plusieurs fois dans ce fichier peut générer un nombre moins important de données téléchargées globales. </p> <p> JavaScript pour [! Compression DNL appmeasurement] Si le poids de la page (taille) du client JavaScript Adobe vous préoccupe, Adobe vous conseille de compresser le fichier à l'aide de GZIP. GZIP est pris en charge par les principaux navigateurs du marché ; il offre de meilleures performances que la compression JavaScript pour compresser et décompresser le fichier JavaScript principal <span class="filepath">s_code.js</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Performances. L’envoi de données du navigateur vers les services Adobe peut-il réduire les performances ? </p> </td> 
   <td colname="col3"> <p> Le fichier JavaScript Adobe crée un objet image dans la page HTML, puis le navigateur demande l’objet image auprès des serveurs Adobe. Si les serveurs Adobe sont lents ou ne répondent pas, le thread gérant cette demande est retardé jusqu’à ce que l’image réapparaisse ou qu’une temporisation se produise. Les navigateurs gèrent les images avec plusieurs threads. Pour cette raison, les pannes de serveurs Adobe ont peu d’incidence sur le temps de chargement de la page puisqu’un seul thread est concerné tandis que les autres continuent à fonctionner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Performances. Un événement JavaScript côté Adobe peut-il se répercuter sur le comportement ou les fonctionnalités du système ? </p> </td> 
   <td colname="col3"> <p>Non. Voir les réponses précédentes sur les performances. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Comment changer les données collectées, d’après les conditions définies par moi-même ? </td> 
   <td colname="col3"> L’utilisation des règles de traitement simplifie la collecte de données et gère le contenu lorsqu’il est envoyé pour la création de rapports. <a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html" format="https" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Quelle est la dernière version du fichier s_code ? </td> 
   <td> Cette section contient un historique des versions pour [! Bibliothèques DNL appmeasurement] sur les plateformes web et mobiles. Vous pouvez télécharger la dernière version de chaque bibliothèque sous Reports &amp; Analytics &gt; Outils d’administration &gt; Gestionnaire de code. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/?f=c_release_notes_javascript" format="http" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Comment déboguer un fichier s_code ? </td> 
   <td> L’Adobe Debugger (anciennement DigitalPulse Debugger) est un outil fourni gratuitement par Adobe, qui permet d’afficher les données collectées sur votre site dans une page déterminée. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=debugger" format="http" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Comment effectuer le suivi de différents types de liens ? </td> 
   <td> Il est possible d’effectuer le suivi automatique des téléchargements de fichiers et des liens de sortie en fonction des paramètres définis dans le fichier AppMeasurement pour JavaScript. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=function_tl" format="http" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Comment effectuer le suivi d’une vidéo ? </td> 
   <td> Vous pouvez utiliser JavaScript pour effectuer un suivi sur divers lecteurs. Pour assurer un suivi à l’aide de JavaScript, vous ajoutez du code à la page Web qui contient le lecteur, puis effectuez un suivi sur le lecteur à l’aide des gestionnaires d’événements. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js" format="http" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Comment effectuer le suivi d’une application mobile ? </td> 
   <td> Il est possible de générer des liens d’acquisition avec des codes de suivi uniques dans Adobe Mobile Services. Lorsqu’un utilisateur télécharge et exécute une application à partir de l’App Store d’Apple après avoir cliqué sur le lien généré, le SDK collecte et envoie automatiquement les données d’acquisition à Adobe Mobile Services. <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=acquisition" format="http" scope="external"> iOS</a> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=acquisition" format="http" scope="external">Android </a> </td> 
  </tr> 
  <tr> 
   <td> Comment mettre en œuvre le suivi des vidéos ? </td> 
   <td> Vous pouvez effectuer un suivi sur les lecteurs média en créant des fonctions liées aux gestionnaires d’événements du lecteur vidéo. Vous pouvez ainsi invoquer les événements Media.open, Media.play, Media.stop et Media.close aux moments appropriés. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js_events" format="http" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Comment configurer le cookie direct ? </td> 
   <td> Analytics utilise les cookies afin de fournir des informations sur les variables et les composants qui ne persistent pas entre les demandes d’images et les sessions de navigateur. Ces cookies inoffensifs, issus d’un domaine hébergé par Adobe, sont des cookies tiers. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_cert" format="http" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Comment obtenir un certificat SSL ? </td> 
   <td> Déterminez si votre site utilise le protocole https://. Si tel est le cas, vous devez solliciter une demande de signature de certificat (CSR) et acheter un certificat SSL. Remarque : Aucun certificat SSL n’est requis si vous ne possédez pas de pages ou de contenu sécurisés. Cette étape peut être ignorée si vous utilisez uniquement le protocole https:// sur votre site. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_cert" format="http" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Où trouver des informations sur l’avis d’expiration de la certification ? </td> 
   <td> Les certificats SSL expirent chaque année, ce qui signifie qu’Adobe nécessite une demande de certificat mise à jour chaque fois que ceci se produit. Le spécialiste FCP fournit un avertissement avant que ceci ne se produise. Toutefois, il est recommandé de bien contrôler l’expiration et de fournir ce certificat mis à jour à Adobe. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_renewals" format="http" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Que sont les modules externes ? </td> 
   <td> Les modules externes AppMeasurement pour JavaScript sont des programmes ou des fonctions qui effectuent plusieurs fonctions avancées. Ces modules externes étendent les capacités de votre fichier JavaScript en apportant des fonctionnalités qui ne sont pas disponibles avec l’implémentation de base. Adobe propose de nombreux autres modules dans le cadre de solutions avancées. Contactez votre gestionnaire de compte si vous souhaitez capturer des données à l’aide de JavaScript, mais ne savez pas comment procéder. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=impl_plugins" format="http" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Informations au sujet de l’API d’insertion de données ? </td> 
   <td> Adobe a élaboré plusieurs méthodes d’envoi de données dans Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=usecase_sending_data_to_sc" format="http" scope="external"> [Plus...] </a> </td> 
  </tr> 
  <tr> 
   <td> Qu’est-ce qu’une erreur 500 ? </td> 
   <td> Il s’agit d’informations au sujet de l’erreur de serveur interne à l’origine de l’état « Erreur de requête 500 ». <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=pageType" format="http" scope="external">Voir Variable pagetype </a> </td> 
  </tr> 
 </tbody> 
</table>

| Question | Réponse |
|---|---|
| Comment gérer les groupes et les utilisateurs Analytics ? | Pour plus d'informations sur la gestion des utilisateurs et des groupes, consultez [la section Gestion des utilisateurs et des produits](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) Experience Cloud dans l'aide des services principaux Adobe Experience Cloud. |
| Expiration des eVar. Pourquoi les eVar sont-elles définies sur la valeur « Aucun » ou « Néant » dans les rapports ? | `Expire After` Spécifie une période ou un événement après lequel la valeur d'evar expire (ne reçoit plus le crédit des événements de réussite). Si un événement de succès se produit après l’expiration de l’eVar, la valeur Aucun reçoit le crédit pour l’événement (aucune valeur eVar n’était active). Si vous sélectionnez un événement comme valeur d’expiration, la variable arrive uniquement à expiration si l’événement a lieu. Dans le cas contraire, la variable n’expire jamais. [[Plus...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Visibilité des événements personnalisés. Pourquoi les événements personnalisés n’apparaissent-ils pas dans le menu des rapports ? | Dans la colonne Visibilité, vous pouvez masquer les mesures (intégrées) standard, les événements personnalisés et les événements intégrés dans le menu, les sélecteurs de mesure, le créateur de mesures calculées et le créateur de segments. Ce paramètre n’a aucun impact sur la collecte des données pour cette mesure ou cet événement ; il affecte uniquement sa visibilité dans l’interface utilisateur. [[Plus...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/metric-visibility.html) |
| Horodatages. De quoi dois-je tenir compte avant de modifier les paramètres d’horodatage ? | Avec l’option Horodatages (facultatif), vous pouvez combiner des données horodatées et non horodatées sans aucune perte de données. Les données hors ligne horodatées générées par un appareil mobile peuvent être combinées à des données en direct non horodatées d’une page Web, ou intégrées aux données d’une plateforme quelconque à l’aide d’un appel d’horodatage côté client. [[Plus...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/timestamps-overview.html) |
| Identifiant visiteur. Comment fonctionne la période de grâce de l’identifiant visiteur et comment est-elle activée ? | Si plusieurs fichiers JavaScript envoient des données à la même suite de rapports ou si vous avez recours à d’autres technologies sur votre site, par exemple la mesure vidéo Flash, nous vous recommandons de configurer une période de grâce.  [Plus…](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html) |
| Identifiant visiteur. Quelle est la différence entre l’identifiant visiteur Experience Cloud et l’identifiant visiteur Analytics ? | Le service d'identité attribue un identifiant persistant unique à tous les visiteurs de votre site. Avec cet ID, les visiteurs et leurs données peuvent être partagés dans les solutions Experience Cloud. En outre, cet identifiant peut remplacer ou fonctionner avec des identifiants spécifiques à une solution, tel l’identifiant visiteur Analytics.  [Plus...](https://docs.adobe.com/content/help/en/id-service/using/intro/overview.html) |
| Identifiant visiteur. Comment est défini l’identifiant visiteur si les cookies sont bloqués ? | Si le cookie s_vi standard n’est pas disponible, un cookie de secours est créé sur le domaine du site web avec un identifiant unique généré de façon aléatoire. Ce cookie, appelé s_fid, est défini avec une date d’expiration de 2 ans et est utilisé comme méthode d’identification de secours.  [Plus…](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/unique-visitors/visid-fallback.html) |
| Dynamic Tag Management. Pourquoi ma règle de Dynamic Tag Management se déclenche-t-elle ? | Si votre règle basée sur un événement n’est pas déclenchée, le problème est probablement lié au sélecteur ou à la condition de la règle. Dans votre site, recherchez l’élément sur lequel l’action d’événement se produit, cliquez dessus avec le bouton droit, puis sélectionnez Contrôler l’élément. Examinez le script mis en surbrillance dans la zone qui s’ouvre, puis vérifiez que vous ciblez l’élément adéquat.  [Plus...](https://docs.adobe.com/content/help/en/dtm/using/admin/c-troubleshooting.html) |
| Comment mettre en œuvre le suivi des vidéos Pulsation ? | [Cette section](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) comprend des instructions sur le téléchargement des SDK de pulsation vidéo et des guides à l’intention des développeurs concernant votre plateforme. Quand vous téléchargez le SDK, veillez à télécharger également le guide de développeur qui se trouve dans le dossiers docs, car il contient des instructions de mise en œuvre spécifiques pour la pulsation vidéo. |
| Comment ajouter des cookies au sous-domaine approprié ? | La variable cookieDomainPeriods détermine le domaine sur lequel les cookies s_cc et s_sq Analytics sont définis en établissant le nombre de points contenus dans le domaine de l’URL de la page. Elle est également utilisée par certains modules externes pour déterminer le domaine correct afin de définir le cookie du module externe. See [Configuration Variables](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/configuration-variables.html) |
| Serveur de suivi. Comment renseigner correctement mon serveur de suivi ? | Quand vous configurez une mise en œuvre pour envoyer des données aux serveurs Adobe Analytics, vous devez les envoyer à l’emplacement approprié. Sinon, le nombre des visiteurs risque d’être gonflé ou des données perdues. [Plus...](https://helpx.adobe.com/analytics/kb/determining-data-center.html) |
| Performances. Un échec de chargement du fichier JavaScript Adobe externe (en raison d’un problème de connexion Internet, d’un proxy, d’un pare-feu ou d’une interruption de service chez Adobe) peut-il affecter les performances ? | Non. Le fichier JavaScript n’est pas hébergé sur les serveurs Adobe. Par conséquent, une panne des serveurs Adobe n’affecte pas l’exécution du fichier JavaScript. |
| Performances. Le chargement du fichier JavaScript Adobe externe peut-il réduire les performances ? | Le fichier JavaScript est mis en cache dans le navigateur du visiteur après son chargement initial. En règle générale, il n’est pas téléchargé plus d’une fois par session. Il n’est pas téléchargé sur chaque page, même s’il est utilisé par toutes les pages du site. Sur la plupart des sites Web, les utilisateurs visualisent, en moyenne, plus de quelques pages par session. Dès lors, le transfert de code JavaScript utilisé plusieurs fois dans ce fichier peut générer un nombre moins important de données téléchargées globales. <br>Compression JavaScript pour AppMeasurement : si le poids (taille) de la page du client JavaScript Adobe vous préoccupe, Adobe vous recommande de compresser le fichier à l’aide de GZIP. GZIP est pris en charge par les principaux navigateurs du marché ; il offre de meilleures performances que la compression JavaScript pour compresser et décompresser le fichier JavaScript principal `s_code.js`. |
| Performances. L’envoi de données du navigateur vers les services Adobe peut-il réduire les performances ? | Le fichier JavaScript Adobe crée un objet image dans la page HTML, puis le navigateur demande l’objet image auprès des serveurs Adobe. Si les serveurs Adobe sont lents ou ne répondent pas, le thread gérant cette demande est retardé jusqu’à ce que l’image réapparaisse ou qu’une temporisation se produise. Les navigateurs gèrent les images avec plusieurs threads. Pour cette raison, les pannes de serveurs Adobe ont peu d’incidence sur le temps de chargement de la page puisqu’un seul thread est concerné tandis que les autres continuent à fonctionner. |
| Performances. Un événement JavaScript côté Adobe peut-il se répercuter sur le comportement ou les fonctionnalités du système ? | Non. Voir les réponses précédentes sur les performances. |
| Comment changer les données collectées, d’après les conditions définies par moi-même ? | L’utilisation des règles de traitement simplifie la collecte de données et gère le contenu lorsqu’il est envoyé pour la création de rapports.  ([Plus...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| Quelle est la dernière version du fichier s_code ? | Cette section comprend un historique des versions des bibliothèques AppMeasurement sur les plateformes Web et mobiles. La dernière version de chaque bibliothèque peut être téléchargée dans Analytics &gt; Admin &gt; Gestionnaire de code. [Plus…](/help/implement/appmeasurement-release-notes/c-release-notes-mjs.md) |
| Comment déboguer un fichier s_code ? | Le débogueur Experience Cloud est un outil gratuit fourni par Adobe qui permet d'afficher les données collectées à partir de votre site sur une page donnée. [Plus…](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) |
| Comment effectuer le suivi de différents types de liens ? | Il est possible d’effectuer le suivi automatique des téléchargements de fichiers et des liens de sortie en fonction des paramètres définis dans le fichier AppMeasurement pour JavaScript. [Plus…](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/function-tl.html) |
| Comment effectuer le suivi d’une vidéo ? | Vous pouvez utiliser JavaScript pour effectuer un suivi sur divers lecteurs. Pour assurer un suivi à l’aide de JavaScript, vous ajoutez du code à la page Web qui contient le lecteur, puis effectuez un suivi sur le lecteur à l’aide des gestionnaires d’événements. [Plus…](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) |
| Comment effectuer le suivi d’une application mobile ? | Il est possible de générer des liens d’acquisition avec des codes de suivi uniques dans Adobe Mobile Services. Lorsqu’un utilisateur télécharge et exécute une application à partir de l’App Store d’Apple après avoir cliqué sur le lien généré, le SDK collecte et envoie automatiquement les données d’acquisition à Adobe Mobile Services. [Ios](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html), [Android](https://docs.adobe.com/content/help/en/mobile-services/android/overview.html) |
| Comment mettre en œuvre le suivi des vidéos ? | Vous pouvez effectuer un suivi sur les lecteurs média en créant des fonctions liées aux gestionnaires d’événements du lecteur vidéo. Vous pouvez ainsi invoquer les événements Media.open, Media.play, Media.stop et Media.close aux moments appropriés. [Plus…](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) |
| Comment configurer le cookie direct ? | Analytics utilise les cookies afin de fournir des informations sur les variables et les composants qui ne persistent pas entre les demandes d’images et les sessions de navigateur. Ces cookies inoffensifs, issus d’un domaine hébergé par Adobe, sont des cookies tiers. [Plus…](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| Comment obtenir un certificat SSL ? | Determine whether your site uses the `https://` protocol. Si tel est le cas, vous devez solliciter une demande de signature de certificat (CSR) et acheter un certificat SSL. Remarque : Aucun certificat SSL n’est requis si vous ne possédez pas de pages ou de contenu sécurisés. This entire step may be skipped if you use only `https://` protocol on your site.  [Plus…](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| Où trouver des informations sur l’avis d’expiration de la certification ? | Les certificats SSL expirent chaque année, ce qui signifie qu’Adobe nécessite une demande de certificat mise à jour chaque fois que ceci se produit. Le spécialiste FCP fournit un avertissement avant que ceci ne se produise. Toutefois, il est recommandé de bien contrôler l’expiration et de fournir ce certificat mis à jour à Adobe. [Plus…](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) |
| Que sont les modules externes ? | Les modules externes AppMeasurement pour JavaScript sont des programmes ou des fonctions qui effectuent plusieurs fonctions avancées. Ces modules externes étendent les capacités de votre fichier JavaScript en apportant des fonctionnalités qui ne sont pas disponibles avec l’implémentation de base. Adobe propose de nombreux autres modules dans le cadre de solutions avancées. Contactez votre gestionnaire de compte si vous souhaitez capturer des données à l’aide de JavaScript, mais ne savez pas comment procéder. [Plus…](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md) |
| Comment trouver des informations sur l'API d'insertion de données ? | Adobe a élaboré plusieurs méthodes d’envoi de données dans Analytics. [Plus…](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
| Qu’est-ce qu’une erreur 500 ? | Informations sur l'erreur de serveur interne qui provoquait l'affichage d'un état « Erreur de requête 500 » à la [variable pagetype](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables.html#concept_F67870238EF74491B5D3909A33CDB985). |