---
description: Ce que vous devez savoir sur la migration des ID utilisateur d’Analytics vers l’Admin Console dans un environnement Adobe Experience Cloud.
title: Migration des utilisateurs d’Analytics vers l’Admin Console
uuid: 7d020713-693b-4945-aa52-3669a631aacb
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Migration des utilisateurs d’Analytics vers l’Admin Console {#analytics-user-migration-to-the-admin-console}

Ce que vous devez savoir sur la migration des ID utilisateur d’Analytics vers l’Admin Console dans un environnement Adobe Experience Cloud.

Pour obtenir une aide d’ordre général sur les rubriques de la Console d’administration (qui ne sont pas liées à la migration Analytics), consultez le Guide [de l’utilisateur de la Console d’](https://helpx.adobe.com/fr/enterprise/administering/user-guide.html)administration.

Une fois la migration effectuée, vous pouvez [gérer les utilisateurs et les produits](https://docs.adobe.com/content/help/fr-FR/core-services/interface/manage-users-and-products/admin-getting-started.html) Experience Cloud dans la console d’administration.

## Qu’est-ce que la migration des ID utilisateur d’Analytics ? {#section-adbe49aba10c4e62afa836a97894107c}

La migration des identifiants utilisateur Analytics permet aux administrateurs de migrer facilement les comptes d’utilisateurs d’Analytics User Management vers la console d’administration Adobe. Une fois vos utilisateurs migrés, ils auront accès aux solutions et aux services principaux disponibles dans Experience Cloud. La migration est déployée par phases pour les clients.

L’utilisation de la console d’administration offre les avantages suivants :

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Avantage </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Authentification unique </p> </td> 
   <td colname="col2"> <p>Les utilisateurs d’Analytics peuvent se connecter à Experience Cloud et à toutes les solutions à l’aide de leur Adobe ID ou Enterprise ID. Cette connexion permet d’accéder aux solutions intégrées et aux services principaux dans Experience Cloud. </p> <p>Après la migration, les utilisateurs qui tentent de se connecter via les comptes hérités (<span class="filepath"> my.omniture.com</span> et <span class="filepath"> sc.omniture.com</span>) sont redirigés vers <span class="filepath"> experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestion de l’identité des utilisateurs et des autorisations </p> </td> 
   <td colname="col2"> <p>Les administrateurs d’Analytics peuvent gérer les utilisateurs et les autorisations exclusivement dans l’<a href="http://adminconsole.adobe.com/enterprise/">Admin Console</a> (http://adminconsole.adobe.com/enterprise/). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestion des produits et des services principaux </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Invitation de nouveaux utilisateurs </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Créer un de produits  </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Octroi aux utilisateurs d’autorisations sur des produits et services spécifiques </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Accédez aux <a href="https://docs.adobe.com/content/help/fr-FR/core-services/interface/experience-cloud.html">services principaux inter-solutions</a> disponibles dans l’environnement Adobe Experience Cloud </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Que savoir et que faire avant de migrer des ID utilisateur (FAQ) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

Réponses aux questions que vous pourriez avoir avant la migration.

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question /  </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Je suis administrateur Analytics et ai reçu un courrier électronique de pré-migration. Que fais-je en premier ? </p> </td> 
   <td colname="col2"> <p>Vérifiez que vous disposez d’un Adobe ID et que vous pouvez accéder à l’<a href="https://adminconsole.adobe.com/enterprise/">Admin Console de l’environnement Experience Cloud</a>. </p> <p>Si ce n’est pas le cas, contactez l’<a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html">assistance clientèle d’Adobe</a>. (Vous devez tout d’abord contacter votre administrateur système ou produit qui peut vous inviter au sein de l’organisation appropriée.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intégrations d’AEM à Analytics </p> </td> 
   <td colname="col2"> <p> Les utilisateurs AEM ayant une intégration à Analytics devront modifier leur configuration pour utiliser le secret partagé Analytics au lieu du mot de passe. </p> <p> Vous devez effectuer cette opération avant d’activer la migration. Une fois la migration désactivée, le mot de passe initialement configuré ne sera plus valide. </p> <p><b>Pour obtenir le secret partagé dans Analytics</b> </p> <p> Vous pouvez obtenir le secret partagé dans Analytics (<span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> Gestion des utilisateurs</span>).Celui-ci est différent pour chaque utilisateur. </p> <p><b>Mise à jour de votre configuration AEM avec le secret partagé</b> </p> <p>Voir <a href="https://helpx.adobe.com/fr/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html"> Connecting to Adobe Analytics and Creating Frameworks</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mise à jour de Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Important : mettez à jour <a href="https://marketing.adobe.com/resources/help/fr_FR/arb/t_install_arb.html"> Report Builder</a> vers la dernière version. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quand la migration commence-t-elle ? </p> </td> 
   <td colname="col2"> <p>Adobe avertit les administrateurs d’Analytics par courrier électronique avec des instructions sur le moment auquel la migration commencera. </p> <p>Les migrations vers la console d’administration se produisent dans les. Le jour de la migration, Adobe avertit les administrateurs d’Analytics et leur accorde l’accès à l’outil de migration. Une fois qu’un de connexion répond aux critères définis pour chaque vague de migration, Adobe : </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Définissez les dates de  et de fin de la migration . </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Envoyez une notification par courrier électronique au  les administrateurs actuels d’Analytics, environ 30 jours avant leur migration. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Affichez une notification intégrée au produit informant les administrateurs de la date de  de la migration. </li> 
    </ul> <p> Le jour de la migration, vos anciens groupes d’autorisations sont automatiquement copiés dans la console d’administration. Vous ne pourrez plus inviter de nouveaux utilisateurs ou créer des groupes dans les Outils d’administration Analytics. </p> <p>Après la migration : </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Les administrateurs utiliseront la Console d’administration pour gérer leurs utilisateurs et autorisations Analytics. (Vous n’utiliserez plus l’interface de gestion des utilisateurs dans Analytics &gt; Admin &gt; Gestion des utilisateurs.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Les utilisateurs accéderont à Analytics à l’aide de leur Adobe ID ou Enterprise ID par l’intermédiaire de l’environnement Experience Cloud, au lieu de <span class="filepath"> my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Que se passera-t-il à la date de  de la migration ? </p> </td> 
   <td colname="col2"> <p>À 10h00 UTC le jour  de la migration: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Vos groupes d’autorisations existants dans Analytics seront automatiquement répliqués dans la console d’administration sous forme de  de produit, y compris leur description et leurs autorisations granulaires dans les suites de rapports, les mesures, les dimensions, Analytics et les outils de suite de rapports. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Si l’un de vos utilisateurs actuels d’Analytics a été créé dans la Console d’administration (c’est-à-dire s’ils ont un ID Adobe/Enterprise lié), ils seront ajoutés au de produits approprié dans la Console d’administration. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">La section Gestion utilisateur de l’onglet Admin d’Analytics est définie sur <span class="term"> lecture seule</span>. Vous ne pourrez plus créer d’utilisateurs ou de groupes d’autorisations dans cette section et devrez effectuer ces actions via l’Admin Console. Pour plus d’informations, voir <a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56"> Fonctionnalités d’Analytics non prises en charge par l’Admin Console</a>. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">En tant qu’administrateur, vous aurez accès à l’outil <a href="https://marketing.adobe.com/resources/help/fr_FR/experience-cloud/admin-console/analytics-migration/t_migrate-users.html">de migration des identifiants</a>utilisateur. De plus, une notification intégrée au produit s’affiche, qui comprend la date de fin de la migration (généralement 60 jours dans le futur), en plus des liens vers le contenu de l’aide et les FAQ. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Vous aurez accès à un onglet Autorisations de la Console d’administration qui vous permettra de créer des  de produits avec toutes les options granulaires que vous connaissez dans Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Comment migrer les ID utilisateur ? </p> </td> 
   <td colname="col2"> <p> Click <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrate User IDs</a> on the Admin page, under User Management. Utilisez l’outil pour ajouter des utilisateurs aux  de produits dans la Console d’administration (répliquée à partir de groupes d’autorisations dans Analytics). Vous pouvez migrer les ID utilisateur à votre propre rythme. </p> <p>Des privilèges d’administration sont requis. Une fois la migration terminée, elle ne peut plus être annulée. </p> <p>À la date de fin de la migration, l’accès à <span class="filepath"> my.omniture.com</span> est désactivé pour les utilisateurs dans leur société de connexion. Les utilisateurs (y compris ceux qui doivent encore être migrés) sont redirigés vers une interface de connexion via l’URL d’Experience Cloud (<span class="filepath"> experiencecloud.adobe.com</span>) </p> <p>Remarque : Adobe recommande d’en profiter pour effectuer un audit des utilisateurs et des groupes avant la migration. Supprimez les comptes anciens et non utilisés ou bien les comptes qui ne doivent plus avoir accès au produit (par exemple les employés n’appartenant plus à l’organisation). </p> <p>Sujet connexe : <a href="/help/admin/user-management2/user-migration/migrate-enterprise.md"> Migration de comptes utilisateurs Analytics sous la forme d’Enterprise ID et de Federated ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La migration affectera-t-elle ma mise en oeuvre Analytics ou la manière dont les données sont collectées ? </p> </td> 
   <td colname="col2"> <p>Non. </p> <p>La finalité de l’outil de migration est de vous aider à transférer les ID utilisateur et les autorisations de la Gestion utilisateur d’Analytics vers l’<a href="https://adminconsole.adobe.com/enterprise/">Admin Console de l’environnement Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Combien de temps dure le processus de migration ? </p> </td> 
   <td colname="col2"> <p>Tous les administrateurs actuels d’Analytics recevront un courrier électronique de notification de pré-migration quatre semaines avant la migration. (La date de  réelle apparaît dans l’interface d’Analytics.) </p> <p>Lorsque la migration commence, les administrateurs disposent de 60 jours pour terminer le processus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je accélérer ma migration ? </p> </td> 
   <td colname="col2"> <p>Oui. Toutefois, Adobe vous recommande d’utiliser le temps avant que la migration ne commence à : </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Vérifiez que vous êtes un administrateur de produit Analytics dans la Console d’administration. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Indiquez à votre base d’utilisateurs que leur expérience de connexion changera au début de la migration. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Contrôlez vos utilisateurs et autorisations actuels et effectuez  nettoyage . </li> 
    </ul> <p>Pour accélérer votre migration, contactez votre gestionnaire de succès client via l’<a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html">assistance clientèle d’Adobe</a> et soumettez une demande de date de début anticipée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Je suis un administrateur Analytics qui n’a pas accès à la Console d’administration. Qui peut m'aider à accéder à la Console d'administration ? </p> </td> 
   <td colname="col2"> <p>Tout administrateur système ou produit disposant d’un accès à l’Admin Console de votre organisation peut vous accorder cet accès. Si vous ne savez pas qui dans votre organisation dispose des privilèges administrateur de la console, contactez l’<a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html">assistance clientèle d’Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je retarder la date de début de la migration ? </p> </td> 
   <td colname="col2"> <p>Oui. Pour ce faire, contactez l’<a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html">assistance clientèle d’Adobe</a>. </p> 
    <draft-comment> 
     <p>Voir ci-dessous la description des modifications apportées à votre gestion actuelle des utilisateurs et des autorisations d’Analytics à la date de début. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maintenant que mon migre vers la console d’administration, où puis-je créer de nouveaux utilisateurs et groupes d’autorisations avant la date  de la migration ? </p> </td> 
   <td colname="col2"> <p>Avant la date de votre  de migration, vous pouvez créer des utilisateurs dans la Console d’administration ou dans Analytics &gt; Gestion des utilisateurs. </p> <p>Une fois la migration commencée, vous pouvez créer des utilisateurs et des groupes d’autorisations uniquement dans la Console d’administration. </p> 
    <draft-comment> 
     <p>voir la section Migration ci-dessous pour plus d’informations sur ce qui se passe à la date de début de la migration). </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Quand puis-je mettre en oeuvre l’authentification unique à l’aide d’ID fédérés ? </p> </td> 
   <td colname="col2"> <p> Un outil qui permettra de transformer les Adobe ID en Federated ID sera bientôt disponible dans l’Admin Console. Pendant la migration, vous ne pouvez pas migrer les utilisateurs sous forme d’ID fédérés. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Que savoir au cours de la migration (FAQ) {#section-d394524aa6d046d79025bbd7499792bc}

Informations importantes sur le processus de migration et son impact sur la gestion actuelle des utilisateurs.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Comment les groupes d’autorisations sont-ils répliqués dans la console d’administration ? Et mes utilisateurs ? </p> </td> 
   <td colname="col2"> <p>Un groupe Analytics migré est appelé un de <i>produits</i> dans la console d’administration. Les paramètres d’autorisation du groupe d’origine sont conservés dans la migration. Toutefois, les utilisateurs affectés au groupe ne sont pas migrés. Lorsqu’un utilisateur appartenant à ce groupe est migré à l’aide de l’outil de migration, cet utilisateur est affecté à cet  de produits. </p> <p>Par exemple, un groupe d’autorisations Opérations de la côte ouest qui a autorisé ses membres à accéder au créateur de rapports et à l’espace de travail  (avec certaines suites de rapports, mesures et dimensions) deviendra un de produits Opérations de la côte ouest. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je déléguer l’effort de migration à un autre administrateur ? </p> </td> 
   <td colname="col2"> <p>Une fois la migration commencée, tout administrateur qui accède à votre instance Analytics via Experience Cloud peut utiliser l’outil de migration pour commencer (ou continuer) la migration des utilisateurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je mettre à jour l’appartenance à un groupe d’autorisations pour les utilisateurs non migrés ? </p> </td> 
   <td colname="col2"> <p>Oui. Vous pouvez modifier l’appartenance au groupe des utilisateurs non migrés dans la section Gestion des utilisateurs d’Analytics. </p> 
    <draft-comment> 
     <p>En attente d’éclaircissements d’Ashok sur ce qui a été fait. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je créer des utilisateurs et des groupes d’autorisations dans Analytics après le début de ma migration, puis utiliser l’outil de migration pour les déplacer vers la console d’administration ? </p> </td> 
   <td colname="col2"> <p> Non. Une fois la migration commencée, tous les nouveaux utilisateurs et groupes d’autorisations (appelés  de produits dans la Console d’administration) doivent être créés dans la Console d’administration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les utilisateurs que je migre à l’aide de l’outil de migration se verront-ils attribuer les mêmes autorisations que celles dont ils disposaient dans Analytics ? </p> </td> 
   <td colname="col2"> <p>Oui. Les utilisateurs migrés à l’aide de l’outil se verront octroyer les autorisations dont ils disposent actuellement dans Analytics. En outre, ils conservent l’accès à leurs ressources Analytics (tels que les segments, les projets, les mesures calculées, etc.) lorsqu’ils accèdent à Analytics par le biais d’Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les utilisateurs que je migre vers l’Admin Console continuent-ils d’avoir accès à Analytics par l’intermédiaire de <span class="filepath">my.omniture.com</span> ? </p> </td> 
   <td colname="col2"> <p>Oui. Les utilisateurs migrés continuent d’avoir accès à Analytics à l’aide de leurs nom d’utilisateur et mot de passe actuels par l’intermédiaire de <span class="filepath"> my.omniture.com</span> jusqu’à la date de fin de la migration, sauf si vous désactivez leur accès au compte hérité via l’outil de migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deux utilisateurs ou plus ont le même ID de courrier électronique dans leur enregistrement Analytics. Que se passe-t-il si je les migre ? </p> </td> 
   <td colname="col2"> <p>Les comptes d’utilisateurs de la Console d’administration nécessitant des ID de courrier électronique uniques, vous risquez de rencontrer une erreur "ID de courrier électronique " lorsque vous tentez de migrer plusieurs de ces utilisateurs. Vous pouvez mettre à jour les ID de courrier électronique des utilisateurs non migrés dans la section Gestion des utilisateurs (héritée) avant de relancer la migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Que faire après la migration de mes utilisateurs ? </p> </td> 
   <td colname="col2"> <p>Désactivez l’accès de leur compte hérité à <span class="filepath"> my.omniture.com</span>. Vous ne pourrez pas désactiver la connexion héritée à moins qu’ils n’aient été migrés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je suivre le processus de migration ? </p> </td> 
   <td colname="col2"> <p>L’outil de migration comprend un  qui affiche le nombre d’utilisateurs qui ont réussi la migration et le nombre d’entre eux dont la connexion héritée est désactivée. </p> <p> Dans l’idéal, vous aurez migré avec succès votre de connexion vers la console d’administration lorsqu’un groupe de 100 % de vos utilisateurs ont effectué une migration et que leurs anciennes connexions ont été désactivées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Je dois gérer les utilisateurs et les autorisations pendant la migration. Quel outil puis-je utiliser pour effectuer cette  de ? </p> </td> 
   <td colname="col2"> <p>Une fois la migration commencée, vous utiliserez la Console d’administration pour créer et gérer de nouveaux utilisateurs et des  de produits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Que vivent mes utilisateurs lorsque je les migre à l’aide de l’outil ? </p> </td> 
   <td colname="col2"> <p>Ils recevront un courrier électronique de bienvenue à l’ID de courrier électronique dans leur enregistrement utilisateur Analytics, leur indiquant leur nouvelle méthode d’accès à Analytics via Experience Cloud. S’ils ne possèdent pas d’Adobe ID existant, ils sont invités à en créer un, après quoi ils pourront accéder à la solution à l’aide de leur Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je utiliser les API pour migrer mes utilisateurs au lieu d’utiliser l’outil de migration ? </p> </td> 
   <td colname="col2"> <p>Non. Vous devez utiliser l’outil de migration pour vous assurer que tous vos utilisateurs existants sont migrés vers la Console d’administration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quelles fonctionnalités de gestion des utilisateurs d’Analytics ne sont pas disponibles dans la console d’administration ? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Transfert de ressources </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Expiration de l’utilisateur </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Journaux utilisateur </li> 
    </ul> <p>Elles resteront disponibles dans la gestion des utilisateurs d’Analytics. </p> <p>Pour plus d’informations, voir <a href="/help/admin/user-management2/user-migration/c-migration-tool.md"> Fonctionnalités d’Analytics non prises en charge par l’Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nous avons créé plusieurs configurations dans la Console d’administration et les avons mises en correspondance avec des groupes d’autorisations Analytics. Qu’adviendra-t-il de ces configurations lorsque la migration commencera ? </p> </td> 
   <td colname="col2"> <p>Les groupes d’autorisations Analytics sont recréés dans la Console d’administration en tant que  de produit, comme tous les autres groupes. Cela signifie que vous verrez deux  de produits dans la console qui ont essentiellement des autorisations de . Vous pouvez supprimer  de produits  de la Console d'administration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quelle est l’étape suivante après la migration de l’utilisateur ? </p> </td> 
   <td colname="col2"> <p>Une fois que vous avez migré l’utilisateur ou un ensemble d’utilisateurs, l’étape suivante est de désactiver leur compte hérité par l’intermédiaire de <span class="filepath"> my.omniture.com</span>. Pour ce faire, sélectionnez ces utilisateurs dans l’outil de migration et cliquez sur l’option contextuelle "Désactiver la connexion héritée" qui apparaît en haut de l’écran. Notez que cette option n’est visible que lorsque vous sélectionnez un utilisateur ou un ensemble d’utilisateurs qui ont tous été migrés avec succès vers la Console d’administration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Que se passe-t-il à la date de fin de la migration ? </p> </td> 
   <td colname="col2"> <p>Après la date de fin de la migration (60 jours à compter du  de la migration), tous les utilisateurs de votre de connexion  sont redirigés vers la connexion via la page de connexion d’Experience Cloud à l’aide de leurs Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Je n’ai pas pu migrer tous mes utilisateurs à la date de fin de la migration. Les utilisateurs non migrés perdraient-ils leur accès à Analytics ? </p> </td> 
   <td colname="col2"> <p>Les utilisateurs qui n’ont pas été migrés à la date de fin sont redirigés vers la page de connexion de l’environnement Experience Cloud (experiencecloud.adobe.com) et ne pourront pas accéder à Analytics. Néanmoins, vous continuerez à avoir accès à l’outil de migration afin de pouvoir trouver et migrer ces utilisateurs dans le but de restaurer leur accès. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Que savoir après la migration (FAQ) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question / Problème </th> 
   <th colname="col2" class="entry"> Réponses </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Suppression d’utilisateurs de la console d’administration </p> </td> 
   <td colname="col2"> <p> Dans Analytics, un utilisateur qui a été supprimé est marqué comme étant <span class="term"> expiré</span>, mais le compte correspondant existe toujours. La conservation du compte permet de transférer des actifs, tels que des segments, des mesures calculées, des rapports planifiés, des projets, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration du compte </p> </td> 
   <td colname="col2"> <p> Vous pouvez définir manuellement une date d’expiration de compte dans Analytics dans les outils d’administration. Une fois la date d’expiration atteinte, l’utilisateur ne pourra plus accéder à Analytics, mais à son compte utilisateur Experience Cloud (par exemple, Adobe ID, Enterprise ID, Federated ID, etc.). n’expire pas. Ils peuvent toujours se connecter à Experience Cloud, ils ne pourront simplement pas cliquer sur Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Fonctionnalités d’Analytics non prises en charge par l’Admin Console {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>Étudiez les problèmes suivants qui peuvent se produire lors de la migration.

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question / Problème </th> 
   <th colname="col2" class="entry"> Réponses </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Connexion en tant que </p> </td> 
   <td colname="col2"> <p> Les administrateurs qui effectuent la migration vers la console d’administration ne pourront plus utiliser la fonction "Se connecter en tant que" pour accéder aux comptes d’utilisateurs non-administrateurs qui ont été migrés vers la console d’administration. Cette fonctionnalité est en cours de désapprobation d’Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration utilisateur et transfert de ressources </p> </td> 
   <td colname="col2"> <p> La console d’administration ne prend pas en charge l’expiration des utilisateurs ni le transfert de ressources. Les administrateurs utiliseront la section Utilisateurs et ressources d’Analytics sous Outils d’administration dans Analytics pour les deux fonctions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dernier accès (dernière connexion) </p> </td> 
   <td colname="col2"> <p> Les détails relatifs à la date et à l’heure de dernière connexion d’un utilisateur sont disponibles dans le lien Utilisateurs et ressources d’Analytics et non dans la console d’administration. La date de dernière connexion à Analytics correspond à la date à laquelle les utilisateurs ont réellement accédé à Analytics depuis Experience Cloud et ne correspond pas à la date/heure à laquelle ils se sont connectés à l’environnement Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>API de gestion des utilisateurs <a href="https://helpx.adobe.com/fr/enterprise/using/identity.html"> Types d’identité pris en charge par Adobe</a> </p> </td> 
   <td colname="col2"> <p> Les administrateurs migrant vers l’Admin Console doivent configurer les <a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html">API de gestion des utilisateurs</a> fournies par Adobe I/O pour un accès programmatique aux comptes utilisateur dans l’Admin Console. </p> <p>Les API d’autorisation d’Analytics seront désactivées lorsque vous serez activé pour la migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Informations de connexion aux services Web </p> </td> 
   <td colname="col2"> <p> Les informations d’identification du service Web des utilisateurs (et leur secret partagé) ne seront pas disponibles dans la console d’administration et vous pouvez y accéder en cliquant sur l’utilisateur spécifique dans la section Utilisateurs et ressources d’Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Authentification unique </p> </td> 
   <td colname="col2"> <p> Les configurations de connexion unique d’Analytics sont supprimées lorsque vous avez terminé la migration. Ils resteront actifs pendant la migration. Les clients qui utilisent la connexion unique Analytics doivent effectuer une mise à niveau vers <a href="https://helpx.adobe.com/fr/enterprise/using/identity.html"> Adobe Federated ID</a>. </p> <p>Analytics vous recommande de migrer vos utilisateurs en tant qu’ID Adobe d’abord pour créer facilement les comptes Experience Cloud, puis de les convertir en utilisateurs à authentification unique fédérés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Téléchargement de groupes d’autorisations </p> </td> 
   <td colname="col2"> <p> Le téléchargement des informations du groupe d’autorisations ne sera plus pris en charge dans les outils d’administration Analytics ou dans la console d’administration Adobe. Les clients doivent utiliser les API de gestion des utilisateurs d’adobe.io pour obtenir des informations de groupe d’autorisations en bloc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date de création du compte </p> </td> 
   <td colname="col2"> <p>Les informations sur la date de création du compte ne sont plus prises en charge dans les outils d’administration Analytics ou dans la console d’administration Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Courrier électronique en masse </p> </td> 
   <td colname="col2"> <p>Les courriers électroniques en masse envoyés aux utilisateurs ne seront plus pris en charge dans la console d’administration Analytics ni dans la console d’administration Adobe. Les clients peuvent exporter en masse l’adresse électronique de leurs utilisateurs à partir d’Adobe Admin Console et envoyer un courrier électronique à l’aide de tout client de messagerie souhaité. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comment avertir vos utilisateurs de la migration {#section-f3b25f672a3a4d03b0559656fd99d20a}

Vous pouvez souhaiter communiquer de manière proactive ce plan de migration à vos utilisateurs actuels. Voici un modèle que vous pouvez personnaliser pour envoyer tous vos utilisateurs Analytics actuels :

Pour envoyer un courrier électronique à tous les utilisateurs, accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > Utilisateurs [de](https://marketing.adobe.com/resources/help/fr_FR/reference/t_email_users.html)messagerie électronique.

**Objet :** Très bientôt - Nouveau mode de connexion à Adobe Analytics et Adobe Experience Cloud.

**Corps :** Chers utilisateurs Adobe Analytics,

Notre société va commencer à migrer tous les comptes Adobe Analytics depuis [!DNL https://my.omniture.com/login/] vers l’environnement Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/)). Avec cette migration, votre compte Adobe Analytics sera mis à niveau pour permettre l’accès à Analytics via Adobe Experience Cloud. Bien que la méthode d’accès à Analytics soit modifiée, toutes vos autorisations existantes sur vos suites de rapports et outils seront conservées.

**Étapes suivantes :** nous commencerons à migrer les utilisateurs le **INSÉRER LA DATE**. Recherchez un message de bienvenue avec votre nouvelle connexion à l’ID de courrier électronique répertorié sous votre compte Analytics. Si vous n’avez pas configuré d’ID [](https://helpx.adobe.com/fr/x-productkb/global/adobe-id-account-change.html) Adobe associé à votre adresse électronique, vous serez invité à configurer un compte.

**Ressources utiles :**

[Connexion et gestion des paramètres du profil](https://marketing.adobe.com/resources/help/fr_FR/mcloud/getting-started-experience-cloud.html).

[A propos des clouds, des services principaux et des solutions](https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html) dans Experience Cloud

Contactez vos administrateurs Analytics si vous avez des questions ou des préoccupations.

Best,

Votre administrateur Analytics
