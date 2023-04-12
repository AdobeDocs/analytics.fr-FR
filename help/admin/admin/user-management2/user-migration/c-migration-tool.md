---
description: Ce que vous devez savoir sur la migration des ID utilisateur d’Analytics vers l’Admin Console dans un environnement Adobe Experience Cloud.
title: Migration des utilisateurs d’Analytics vers l’Admin Console
feature: Admin Tools
exl-id: f4bc0e92-af53-40db-8138-44d29e4b25fe
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '3162'
ht-degree: 99%

---

# Migration des utilisateurs d’Analytics vers Adobe Admin Console{#analytics-user-migration-to-the-admin-console}

Ce que vous devez savoir sur la migration des ID utilisateur d’Analytics vers Adobe Admin Console dans un environnement Adobe Experience Cloud.

Pour une aide générale sur les rubriques d’Adobe Admin Console (sans rapport avec la migration d’Analytics), consultez le [Guide d’utilisateur de l’Admin Console](https://helpx.adobe.com/fr/enterprise/administering/user-guide.html).

Après avoir migré, vous pouvez [gérer les utilisateurs et les produits Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr) dans Adobe Admin Console.

## Qu’est-ce que la migration des ID utilisateur d’Analytics ? {#section-adbe49aba10c4e62afa836a97894107c}

La migration des ID utilisateur Analytics permet aux administrateurs de migrer facilement les comptes utilisateurs du système de gestion des utilisateurs Analytics vers Adobe Admin Console. Une fois la migration de vos utilisateurs terminée, ils auront accès aux solutions et aux services principaux disponibles dans Experience Cloud. La migration est en cours de déploiement.

Les avantages de l’utilisation d’Adobe Admin Console sont les suivants :

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
   <td colname="col2"> <p>Les utilisateurs d’Analytics peuvent se connecter à l’environnement Experience Cloud et à toutes les solutions à l’aide de leur Adobe ID ou Enterprise ID. Cette connexion permet l’accès à des solutions intégrées et des services principaux de l’environnement Experience Cloud. </p> <p>Après la migration, les utilisateurs qui tentent de se connecter via les comptes hérités (<span class="filepath"> my.omniture.com</span> et <span class="filepath"> sc.omniture.com</span>) sont redirigés vers <span class="filepath"> experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestion de l’identité des utilisateurs et des autorisations </p> </td> 
   <td colname="col2"> <p>Les administrateurs d’Analytics peuvent gérer les utilisateurs et les autorisations exclusivement dans l’<a href="https://adminconsole.adobe.com/enterprise/">Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestion des produits et des services principaux </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Invitez de nouveaux utilisateurs </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Créez des profils produit </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Accordez des autorisations aux utilisateurs pour des produits et services spécifiques </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Accédez aux <a href="https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=fr">services principaux inter-solutions</a> disponibles dans l’environnement Adobe Experience Cloud. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Que savoir et que faire avant de migrer des ID utilisateur (FAQ) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

Réponses à certaines questions que vous pourriez vous poser avant la migration.

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question/Tâche </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Je suis un administrateur Analytics et j’ai reçu un courrier électronique m’informant de la migration à venir. Par où dois-je commencer ? </p> </td> 
   <td colname="col2"> <p>Vérifiez que vous disposez d’un Adobe ID et que vous pouvez accéder à l’<a href="https://adminconsole.adobe.com/enterprise/">Admin Console de l’environnement Experience Cloud</a>. </p> <p>Si ce n’est pas le cas, contactez l’<a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html">assistance clientèle d’Adobe</a>. (Vous devez tout d’abord contacter votre administrateur système ou produit qui peut vous inviter au sein de l’organisation appropriée.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intégration d’AEM à Analytics </p> </td> 
   <td colname="col2"> <p> Les utilisateurs d’AEM avec une intégration vers Analytics doivent modifier leur configuration pour pouvoir utiliser le secret partagé d’Analytics plutôt que le mot de passe. </p> <p> Cela doit être fait avant l’activation de la migration. Une fois la migration désactivée, le mot de passe qui avait été configuré n’est plus valide. </p> <p><b>Obtention du secret partagé dans Analytics</b> </p> <p> Vous pouvez obtenir le secret partagé dans Analytics (<span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> Gestion des utilisateurs</span>).Celui-ci est différent pour chaque utilisateur. </p> <p><b>Mise à jour de votre configuration AEM avec le secret partagé</b> </p> <p>Voir <a href="https://helpx.adobe.com/fr/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html"> Connecting to Adobe Analytics and Creating Frameworks</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mise à jour de Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Important : mettez à jour <a href="https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html?lang=fr"> Report Builder</a> vers la dernière version. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quand commence la migration ? </p> </td> 
   <td colname="col2"> <p>Adobe avertit les administrateurs d’Analytics par courrier électronique contenant des instructions sur le moment où la migration commence. </p> <p>Les migrations vers Adobe Admin Console se produisent par vagues. Le jour de la migration, Adobe avertit les administrateurs d’Analytics et leur accorde l’accès à l’outil de migration. Une fois qu’une société de connexion respecte les critères définis pour chaque vague de migration, Adobe : </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">définit les dates de début et de fin de la migration de la société ; </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">envoie une notification électronique aux administrateurs actuels d’Analytics de la société, environ 30 jours avant la migration ; </li> 
     <li id="li_476265B24CE2404B995201170C75D674">affiche une notification intégrée au produit informant les administrateurs de la date de début de la migration. </li> 
    </ul> <p> Le jour de la migration, vos anciens groupes d’autorisations sont automatiquement copiés vers Adobe Admin Console. Vous ne pourrez plus inviter de nouveaux utilisateurs ou créer des groupes dans les Outils d’administration Analytics. </p> <p>Après la migration : </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Les administrateurs utiliseront Adobe Admin Console pour gérer leurs utilisateurs et autorisations Analytics. (Vous n’utiliserez plus l’interface Gestion utilisateur d’Analytics &gt; Admin &gt; Gestion utilisateur.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Les utilisateurs accéderont à Analytics à l’aide de leur Adobe ID ou Enterprise ID par l’intermédiaire de l’environnement Experience Cloud, au lieu de <span class="filepath"> my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Que se passera-t-il à la date de début de la migration ? </p> </td> 
   <td colname="col2"> <p>À 10h00 UTC à la date de début de la migration : </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Les groupes d’autorisations existants d’Analytics sont répliqués automatiquement dans Adobe Admin Console sous la forme de profils de produit, y compris leur description et les autorisations granulaires relatives aux suites de rapports, aux mesures, aux dimensions et aux outils Analytics et de suite de rapports. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Si certains de vos utilisateurs Analytics actuels ont été créés dans Adobe Admin Console (signifiant qu’ils disposent d’un Adobe/Enterprise ID lié), ils sont ajoutés aux profils de produit appropriés dans Adobe Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">La section Gestion utilisateur de l’onglet Admin d’Analytics est définie sur  <span class="term"> lecture seule</span>. Vous ne pourrez plus créer d’utilisateurs ou de groupes d’autorisations dans cette section et devrez effectuer ces deux actions via Adobe Admin Console. Pour plus d’informations, consultez <a href="/help/admin/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Fonctionnalités d’Analytics non prises en charge par Adobe Admin Console</a>. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">En tant qu’administrateur, il vous sera accordé un accès à l’outil <a href="https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/t-migrate-users.html?lang=fr">Migration de l’ID utilisateur</a>. En outre, une notification intégrée au produit s’affiche, incluant la date de fin de la migration (généralement 60 jours dans le futur) en plus de liens vers le contenu de l’aide et les FAQ. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Vous aurez accès à l’onglet Autorisations dans Adobe Admin Console qui permet de créer des profils de produit avec toutes les options granulaires que vous connaissez dans Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Comment dois-je migrer les ID utilisateur ? </p> </td> 
   <td colname="col2"> <p> Cliquez sur <a href="/help/admin/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrer les ID utilisateur</a> dans la page Admin de la section Gestion utilisateur. Utilisez l’outil pour ajouter des utilisateurs à des profils de produit dans Adobe Admin Console (copiés depuis les groupes d’autorisations dans Analytics). Vous pouvez migrer les ID utilisateur à votre propre rythme. </p> <p>Des privilèges d’administration sont requis. Une fois que la migration est terminée, elle ne peut plus être annulée. </p> <p>À la date de fin de la migration, l’accès à <span class="filepath"> my.omniture.com</span> est désactivé pour les utilisateurs dans leur société de connexion. Les utilisateurs (y compris ceux qui doivent encore être migrés) sont redirigés vers une interface de connexion via l’URL d’Experience Cloud (<span class="filepath"> experiencecloud.adobe.com</span>) </p> <p>Remarque : Adobe recommande d’en profiter pour effectuer un audit des utilisateurs et des groupes avant la migration. Supprimez les comptes anciens et non utilisés ou bien les comptes qui ne doivent plus avoir accès au produit (par exemple les employés n’appartenant plus à l’organisation). </p> <p>Sujet connexe : <a href="/help/admin/admin/user-management2/user-migration/migrate-enterprise.md"> Migration de comptes utilisateurs Analytics sous la forme d’Enterprise ID et de Federated ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La migration va-t-elle affecter mon implémentation d’Analytics ou la manière dont les données sont collectées ? </p> </td> 
   <td colname="col2"> <p>Non. </p> <p>La finalité de l’outil de migration est de vous aider à transférer les ID utilisateur et les autorisations de la Gestion utilisateur d’Analytics vers l’<a href="https://adminconsole.adobe.com/enterprise/">Admin Console de l’environnement Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Combien de temps prend le processus de migration ? </p> </td> 
   <td colname="col2"> <p>Tous les administrateurs actuels d’Analytics reçoivent une notification électronique quatre semaines avant la migration. (La date de début réelle apparaît dans l’interface d’Analytics.) </p> <p>Une fois que la migration commence, les administrateurs ont 60 jours pour terminer le processus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je accélérer ma migration ? </p> </td> 
   <td colname="col2"> <p>Oui. Néanmoins, Adobe recommande que vous utilisiez la période pré-migration pour : </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">vérifier que vous êtes un administrateur produit Analytics dans Adobe Admin Console ; </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">informer votre base d’utilisateurs du changement de leur mode de connexion dès lors que la migration aura commencé ; </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">auditer les utilisateurs et autorisations actuels et réaliser des activités de nettoyage. </li> 
    </ul> <p>Pour accélérer votre migration, contactez votre équipe de compte d’Adobe à l’adresse <a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html"> Assistance clientèle Adobe</a> et envoyer une demande de date de début antérieure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Je suis administrateur Analytics et je n’ai pas accès à Adobe Admin Console. Qui peut m’aider à avoir accès à Adobe Admin Console ? </p> </td> 
   <td colname="col2"> <p>Tout administrateur système ou produit disposant d’un accès à Adobe Admin Console de votre organisation peut vous accorder cet accès. Si vous ne savez pas qui dans votre organisation dispose des privilèges administrateur de la console, contactez l’<a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html">assistance clientèle d’Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je retarder la date de début de la migration ? </p> </td> 
   <td colname="col2"> <p>Oui. Pour ce faire, contactez l’<a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html">assistance clientèle d’Adobe</a>. </p><p>Voir ci-dessous la description des modifications apportées à votre gestion actuelle des utilisateurs et des autorisations d’Analytics à la date de début. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maintenant que ma société migre vers Adobe Admin Console, où puis-je créer les nouveaux utilisateurs et groupes d’autorisations avant la date de début de la migration ? </p> </td> 
   <td colname="col2"> <p>Avant la date de début de la migration, vous pouvez créer des utilisateurs dans Adobe Admin Console ou sous Analytics &gt; Gestion utilisateur. </p> <p>Une fois que la migration aura commencé, vous ne pourrez créer les utilisateurs et les groupes d’autorisations que dans Adobe Admin Console. </p><p>consultez la section Migration ci-dessous pour plus d’informations sur ce qui se passe à la date de début de la migration. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Où puis-je implémenter une authentification unique à l’aide des Federated ID ? </p> </td> 
   <td colname="col2"> <p> Un outil qui permettra de transformer les Adobe ID en Federated ID sera bientôt disponible dans Adobe Admin Console. Au cours de la migration, vous ne pouvez pas migrer les utilisateurs sous la forme de Federated ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Que savoir au cours de la migration (FAQ) {#section-d394524aa6d046d79025bbd7499792bc}

Informations importantes sur le processus de migration et son impact sur la gestion des utilisateurs actuels.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Comment les groupes d’autorisations sont-ils répliqués sur Adobe Admin Console ? Qu’en est-il de mes utilisateurs ? </p> </td> 
   <td colname="col2"> <p>Un groupe Analytics migré est nommé <i>Profil de produit</i> dans Adobe Admin Console. Les paramètres d’autorisation du groupe d’origine sont conservés lors de la migration. Néanmoins, les utilisateurs affectés au groupe ne sont pas migrés. Lorsqu’un utilisateur appartenant à un groupe est migré à l’aide de l’outil de migration, cet utilisateur est affecté au profil produit correspondant. </p> <p>Par exemple, un groupe d’autorisations Opérations côte ouest qui autorisait à ses membres l’accès à Report Builder et Analysis Workspace (avec certaines suites de rapports, mesures et dimensions) devient un profil produit Opérations côte ouest. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je déléguer la migration à un autre administrateur ? </p> </td> 
   <td colname="col2"> <p>Une fois la migration commencée, tout administrateur qui accède à votre instance Analytics via l’environnement Experience Cloud peut utiliser l’outil de migration pour commencer (ou poursuivre) la migration des utilisateurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je mettre à jour l’abonnement à des groupes d’autorisations pour les utilisateurs non migrés ? </p> </td> 
   <td colname="col2"> <p>Oui. Vous pouvez modifier l’appartenance à un groupe des utilisateurs non migrés depuis la section Gestion utilisateur d’Analytics. </p><p>En attente d’éclaircissements d’Ashok sur ce qui a été fait. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je créer des utilisateurs et des groupes d’autorisations dans Analytics une fois la migration commencée, puis utiliser l’outil de migration pour les déplacer vers Adobe Admin Console ? </p> </td> 
   <td colname="col2"> <p> Non. Une fois la migration commencée, tous les nouveaux utilisateurs et groupes d’autorisations (appelés Profils de produit dans Adobe Admin Console) doivent être créés dans Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les utilisateurs que je migre à l’aide de l’outil de migration auront-ils les mêmes autorisations que dans Analytics ? </p> </td> 
   <td colname="col2"> <p>Oui. Les utilisateurs migrés à l’aide de l’outil gardent les mêmes autorisations que dans Analytics. En outre, ils conservent l’accès à leurs ressources Analytics (tels que les segments, les projets, les mesures calculées, etc.) lorsqu’ils accèdent à Analytics par l’environnement Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les utilisateurs que je migre vers Adobe Admin Console ont-ils toujours accès à Analytics par l’intermédiaire de <span class="filepath">my.omniture.com</span> ? </p> </td> 
   <td colname="col2"> <p>Oui. Les utilisateurs migrés continuent d’avoir accès à Analytics à l’aide de leurs nom d’utilisateur et mot de passe actuels par l’intermédiaire de <span class="filepath"> my.omniture.com</span> jusqu’à la date de fin de la migration, sauf si vous désactivez leur accès au compte hérité via l’outil de migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plusieurs de mes utilisateurs ont le même ID de message électronique dans leur enregistrement Analytics. Que se passe-t-il si je les migre ? </p> </td> 
   <td colname="col2"> <p>Comme les comptes utilisateur d’Adobe Admin Console requièrent des ID de message électronique uniques, vous rencontrerez l’erreur « ID de message électronique en double » lorsque vous tenterez de migrer plusieurs de ces utilisateurs. Vous pouvez mettre à jour les ID de message électronique des utilisateurs non migrés dans la section (existante) Gestion utilisateur avant de tenter à nouveau la migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Que dois-je faire après la migration des utilisateurs ? </p> </td> 
   <td colname="col2"> <p>Désactivez l’accès de leur compte hérité à <span class="filepath"> my.omniture.com</span>. Vous ne pourrez pas désactiver le compte hérité tant qu’ils n’ont pas été migrés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je effectuer le suivi du processus de migration ? </p> </td> 
   <td colname="col2"> <p>L’outil de migration inclut un tableau de bord qui affiche le nombre d’utilisateurs déjà migrés et, parmi eux, le nombre de ceux dont le compte hérité a été désactivé. </p> <p> Idéalement, vous aurez réussi la migration de votre société de connexion vers Adobe Admin Console lorsque 100 % des utilisateurs auront terminé la migration et que leurs comptes hérités auront été désactivés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Je dois effectuer la gestion des utilisateurs et des autorisations au cours de la migration. Quel outil puis-je utiliser pour effectuer cette tâche ? </p> </td> 
   <td colname="col2"> <p>Une fois la migration commencée, vous utiliserez Adobe Admin Console pour créer et gérer de nouveaux utilisateurs et profils de produit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Que se passe-t-il au niveau des utilisateurs lorsque je les migre à l’aide de cet outil ? </p> </td> 
   <td colname="col2"> <p>Ils reçoivent un courrier électronique de bienvenue adressé à l’ID de message électronique inscrit dans leur registre utilisateur Analytics les informant de la nouvelle manière d’accéder à Analytics par l’intermédiaire de l’environnement Experience Cloud. S’ils n’ont pas d’Adobe ID existant, ils sont invités à en créer un. Ils pourront ensuite accéder à la solution à l’aide de leur Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je utiliser des API pour migrer les utilisateurs au lieu de l’outil de migration ? </p> </td> 
   <td colname="col2"> <p>Non. Vous devez utiliser l’outil de migration pour vous assurer que tous les utilisateurs existants sont migrés vers Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quelles fonctionnalités de gestion des utilisateurs d’Analytics ne sont pas disponibles dans Adobe Admin Console ? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Transfert de ressources </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Expiration des utilisateurs </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Journaux des utilisateurs </li> 
    </ul> <p>Ces fonctionnalités resteront disponibles dans la gestion des utilisateurs d’Analytics. </p> <p>Pour plus d’informations, consultez <a href="/help/admin/admin/user-management2/user-migration/c-migration-tool.md">Fonctionnalités d’Analytics non prises en charge par Adobe Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nous avons créé plusieurs configurations dans Adobe Admin Console et nous les avons fait correspondre aux groupes d’autorisations Analytics. Que va-t-il arriver à ces configurations lorsque la migration aura commencé ? </p> </td> 
   <td colname="col2"> <p>Les groupes d’autorisations Analytics sont à nouveau créés dans Adobe Admin Console sous la forme de profils de produit, comme tous les autres groupes. Cela signifie que vous verrez deux profils de produit dans la console qui disposent d’autorisations en double. Vous pouvez supprimer les profils de produit en double depuis Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quelle est l’étape qui succède à la migration de l’utilisateur ? </p> </td> 
   <td colname="col2"> <p>Une fois que vous avez migré l’utilisateur ou un ensemble d’utilisateurs, l’étape suivante est de désactiver leur compte hérité par l’intermédiaire de <span class="filepath"> my.omniture.com</span>. Pour ce faire, sélectionnez les utilisateurs en question dans l’outil de migration et cliquez sur l’option contextuelle « Désactiver le compte hérité » qui s’affiche dans la partie supérieure de l’écran. Notez que cette option n’est visible que lorsque vous sélectionnez un utilisateur ou un ensemble d’utilisateurs qui a été migré avec succès vers Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Que se passe-t-il à la date de fin de la migration ? </p> </td> 
   <td colname="col2"> <p>Après la date de fin de la migration (60 jours après le début de la migration), tous les utilisateurs de votre société de connexion sont connectés via la page de connexion de l’environnement Experience Cloud en utilisant leur Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Je n’ai pas été en mesure de migrer tous mes utilisateurs avant la date de fin de la migration. Les utilisateurs non migrés vont-ils perdre leur accès à Analytics ? </p> </td> 
   <td colname="col2"> <p>Les utilisateurs qui n’ont pas été migrés à la date de fin sont redirigés vers la page de connexion de l’environnement Experience Cloud (experiencecloud.adobe.com) et ne pourront pas accéder à Analytics. Néanmoins, vous continuerez à avoir accès à l’outil de migration afin de pouvoir trouver et migrer ces utilisateurs dans le but de restaurer leur accès. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Que savoir après la migration (FAQ) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question/Problème </th> 
   <th colname="col2" class="entry"> Réponses </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Suppression des utilisateurs d’Adobe Admin Console </p> </td> 
   <td colname="col2"> <p> Dans Analytics, un utilisateur qui a été supprimé est marqué comme étant  <span class="term"> expiré</span>, mais le compte correspondant existe toujours. La préservation du compte permet le transfert de ressources comme les segments, les mesures calculées, les projets, les rapports planifiés, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration d’un compte </p> </td> 
   <td colname="col2"> <p> Vous pouvez programmer la date d’expiration d’un compte dans les Outils d’administration d’Analytics. Une fois la date d’expiration atteinte, l’utilisateur n’aura plus accès à Analytics, mais son compte utilisateur Experience Cloud (Adobe ID, Enterprise ID, Federated ID, etc.) sera toujours valide. La connexion à Experience Cloud sera toujours possible, mais il deviendra impossible de cliquer pour se connecter à Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Fonctionnalités d’Analytics non prises en charge par Adobe Admin Console {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>Étudiez les problèmes suivants qui peuvent se produire lors de la migration.

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question/Problème </th> 
   <th colname="col2" class="entry"> Réponses </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Connexion en tant que </p> </td> 
   <td colname="col2"> <p> Les administrateurs migrant vers Adobe Admin Console ne pourront plus utiliser la fonction « Connexion en tant que » pour accéder aux comptes utilisateur non administrateur qui ont été migrés vers Adobe Admin Console. Cette fonction devient obsolète dans Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration des utilisateurs et transfert des ressources </p> </td> 
   <td colname="col2"> <p> Adobe Admin Console ne prend pas en charge l’expiration des utilisateurs et le transfert des ressources. Les administrateurs utiliseront la section Utilisateurs et ressources Analytics dans les outils d’administration d’Analytics pour les deux fonctions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dernier accès (Dernière connexion) </p> </td> 
   <td colname="col2"> <p> Les détails relatifs à la date et l’heure de la dernière connexion des utilisateurs sont disponibles via le lien Utilisateurs et ressources Analytics et non dans Adobe Admin Console. La date de dernière connexion à Analytics correspond à la date à laquelle les utilisateurs ont réellement accédé à Analytics depuis Experience Cloud et ne correspond pas à la date/heure à laquelle ils se sont connectés à l’environnement Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>API de gestion des utilisateurs <a href="https://helpx.adobe.com/fr/enterprise/using/identity.html"> Types d’identité pris en charge par Adobe</a> </p> </td> 
   <td colname="col2"> <p> Les administrateurs migrant vers Adobe Admin Console doivent configurer les interfaces<a href="https://developer.adobe.com/UMAPI/"> API de gestion des utilisateurs</a> fournies dans Adobe Developer pour un accès programmatique aux comptes utilisateur dans Adobe Admin Console. </p> <p>Les API d’autorisation d’Analytics sont désactivées lorsque vous êtes activé pour la migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Informations de connexion aux services Web </p> </td> 
   <td colname="col2"> <p> Les informations de connexion aux services Web des utilisateurs (et leur secret partagé) ne sont pas disponibles dans Adobe Admin Console. Vous pouvez y accéder en cliquant sur l’utilisateur spécifique depuis la section Utilisateurs et ressources Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Authentification unique </p> </td> 
   <td colname="col2"> <p> Les configurations de connexion unique d’Analytics sont supprimées lorsque vous avez terminé la migration. Elles restent actives au cours de la migration. Les clients qui utilisent la connexion unique Analytics doivent effectuer une mise à niveau vers <a href="https://helpx.adobe.com/fr/enterprise/using/identity.html"> Adobe Federated ID</a>. </p> <p>Analytics recommande que vous migriez vos utilisateurs sous la forme d’Adobe ID dans un premier temps afin de créer facilement les comptes Experience Cloud, puis de convertir ces comptes en utilisateurs à connexion unique Federated. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Téléchargement de groupes d’autorisations </p> </td> 
   <td colname="col2"> <p> Le téléchargement des informations de groupes d’autorisations ne sera plus pris en charge, que ce soit dans les Outils d’administration Analytics ou dans Adobe Admin Console. Les clients doivent utiliser les API de gestion des utilisateurs adobe.io pour obtenir les informations de groupes d’autorisations en masse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date de création du compte </p> </td> 
   <td colname="col2"> <p>Les informations de date de création du compte ne sont plus prises en charge, que ce soit dans les Outils d’administration Analytics ou dans Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Courriers électroniques en masse </p> </td> 
   <td colname="col2"> <p>Les courriers électroniques en masse destinés aux utilisateurs ne seront plus pris en charge, que ce soit dans les outils d’administration Analytics ou dans Adobe Admin Console. Les clients peuvent exporter en masse les adresses électroniques de leurs utilisateurs depuis Adobe Admin Console et envoyer un courrier électronique en utilisant le client de messagerie qu’ils souhaitent. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comment avertir vos utilisateurs de la migration {#section-f3b25f672a3a4d03b0559656fd99d20a}

Vous souhaiterez peut-être communiquer ce plan de migration de manière proactive aux utilisateurs actuels. Vous trouverez ci-dessous un modèle de courrier électronique que vous pouvez personnaliser avant de l’envoyer à tous vos utilisateurs Analytics actuels :

Pour envoyer un e-mail à tous les utilisateurs, accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Gestion des utilisateurs]** > [Envoyer un e-mail aux utilisateurs](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/t-email-users.html?lang=fr).

**Objet :** Très bientôt - Nouveau mode de connexion à Adobe Analytics et Adobe Experience Cloud.

**Corps :** Chers utilisateurs Adobe Analytics,

Notre société va commencer à migrer tous les comptes Adobe Analytics depuis [!DNL https://my.omniture.com/login/] vers l’environnement Adobe Experience Cloud ([experiencecloud.adobe.com](https://experiencecloud.adobe.com/)). Avec cette migration, votre compte Adobe Analytics sera mis à niveau pour permettre l’accès à Analytics via l’environnement Adobe Experience Cloud. Bien que la méthode pour accéder à Analytics change, toutes vos autorisations existantes pour les suites de rapports et les outils seront quant à elles conservées.

**Étapes suivantes :** nous commencerons à migrer les utilisateurs le  **INSÉRER LA DATE**. Surveillez votre messagerie : un message de bienvenue comportant vos nouveaux identifiants de connexion vous sera adressé à l’ID de message électronique répertorié dans votre compte Analytics. Si vous n’avez pas configuré un [Adobe ID](https://helpx.adobe.com/fr/x-productkb/global/adobe-id-account-change.html) lié à votre adresse e-mail, vous serez invité à configurer un compte. 

**Ressources utiles :**

[Connectez-vous et gérez les paramètres du profil](https://helpx.adobe.com/fr/enterprise/admin-guide.html/fr/enterprise/using/manage-products.ug.html).

Contactez vos administrateurs Analytics en cas de questions ou problèmes.

Cordialement,

Administrateur Analytics
