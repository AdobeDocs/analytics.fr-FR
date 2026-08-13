---
description: Ce que vous devez savoir sur la migration des ID utilisateur Analytics vers Admin Console dans Adobe CX Enterprise.
title: Migration des utilisateurs d’Analytics vers l’Admin Console
feature: Admin Tools
exl-id: f4bc0e92-af53-40db-8138-44d29e4b25fe
role: Admin
TQID: https://experienceleague.adobe.com/bCf6DWIpIVALcGPAi3tL8zlZ5V8lzPR-9XNCm4HuFnY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8id: d124af73-4061-4b84-9063-ae2b60f2c1f3id: e499b847-6dc4-408a-9f0b-70d35ce9b711id: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 2960
ht-degree: 51%

---

# Migration des utilisateurs d’Analytics vers Adobe Admin Console{#analytics-user-migration-to-the-admin-console}

Ce que vous devez savoir sur la migration des ID utilisateur Analytics vers Adobe Admin Console dans Adobe CX Enterprise.

Pour une aide générale sur les rubriques d’Adobe Admin Console (sans rapport avec la migration d’Analytics), consultez le [Guide d’utilisateur de l’Admin Console](https://helpx.adobe.com/fr/enterprise/administering/user-guide.html).

Après la migration, vous pouvez [gérer les utilisateurs et les produits CX Enterprise](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr) dans Adobe Admin Console.

## Qu’est-ce que la migration des ID utilisateur d’Analytics ? {#section-adbe49aba10c4e62afa836a97894107c}

La migration des ID d’utilisateur ou d’utilisatrice d’Analytics permet aux administrateurs et aux administratrices de migrer facilement les comptes d’utilisateur ou d’utilisatrice du système de gestion des utilisateurs et des utilisatrices d’Analytics vers l’Adobe Admin Console. Une fois la migration de vos utilisateurs terminée, ils auront accès aux solutions et services principaux disponibles dans CX Enterprise. La migration est déployée par phases auprès des clients.

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
   <td colname="col2"> <p>Les utilisateurs d’Analytics peuvent se connecter à CX Enterprise et à toutes les solutions à l’aide de leur Adobe ID ou Enterprise ID. Cette connexion permet d’accéder à des solutions intégrées et à des services principaux dans CX Enterprise. </p> <p>Après la migration, les utilisateurs qui tentent de se connecter via les comptes hérités (<span class="filepath"> my.omniture.com</span> et <span class="filepath"> sc.omniture.com</span>) sont redirigés vers <span class="filepath"> experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestion de l’identité des utilisateurs et des autorisations </p> </td> 
   <td colname="col2"> <p>Les administrateurs d’Analytics peuvent gérer les utilisateurs et les autorisations exclusivement dans l’<a href="https://adminconsole.adobe.com/enterprise/">Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestion des produits et des services principaux </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Inviter de nouveaux utilisateurs </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Créer des profils produit </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Octroyer aux utilisateurs l’autorisation d’accéder à des produits et services spécifiques </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Accédez à <a href="https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=fr"> services principaux inter-solutions</a> disponibles dans Adobe CX Enterprise </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Que savoir et que faire avant de migrer des ID utilisateur (FAQ) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

Réponses aux questions que vous pourriez avoir avant la migration.

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question/Tâche </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Je suis administrateur Analytics et j’ai reçu un e-mail de pré-migration. Que dois-je faire en premier ? </p> </td> 
   <td colname="col2"> <p>Vérifiez que vous disposez d’une Adobe ID et que vous pouvez accéder à l’<a href="https://adminconsole.adobe.com/enterprise/"> CX Enterprise Admin Console</a>. </p> <p>Si ce n’est pas le cas, contactez l’<a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html">assistance clientèle d’Adobe</a>. (Vous devez tout d’abord contacter votre administrateur système ou produit qui peut vous inviter au sein de l’organisation appropriée.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intégrations d’AEM à Analytics </p> </td> 
   <td colname="col2"> <p> Les utilisateurs d’AEM avec une intégration à Analytics devront modifier leur configuration pour utiliser le secret partagé Analytics au lieu du mot de passe. </p> <p> Vous devez effectuer cette opération avant l’activation de la migration. Une fois la migration désactivée, le mot de passe configuré à l’origine n’est plus valide. </p> <p><b>Pour obtenir le secret partagé dans Analytics</b> </p> <p> Vous pouvez obtenir le secret partagé dans Analytics (<span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> Gestion des utilisateurs</span>).Celui-ci est différent pour chaque utilisateur. </p> <p><b>Mise à jour de votre configuration AEM avec le secret partagé</b> </p> <p>Voir <a href="https://helpx.adobe.com/fr/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html"> Connecting to Adobe Analytics and Creating Frameworks</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mise à jour de Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Important : mettez à jour <a href="/help/analyze/report-builder/report-builder-setup.md"> Report Builder</a> vers la dernière version. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quand commence la migration ? </p> </td> 
   <td colname="col2"> <p>Adobe avertira les administrateurs et administratrices Analytics par e-mail en leur indiquant le moment où la migration commencera. </p> <p>Les migrations vers Adobe Admin Console se produisent par vagues. Le jour de la migration, Adobe en informe les administrateurs Analytics et leur accorde l’accès à l’outil de migration. Une fois qu’une société de connexion répond aux critères définis pour chaque vague de migration, Adobe : </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Définissez les dates de début et de fin de la migration de l’entreprise. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Envoyez une notification par e-mail aux administrateurs Analytics actuels de l’entreprise, environ 30 jours avant leur migration. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Affichez une notification intégrée au produit informant les administrateurs de la date de début de la migration. </li> 
    </ul> <p> Le jour de la migration, vos anciens groupes d’autorisations sont automatiquement copiés vers Adobe Admin Console. Vous ne pourrez plus inviter de nouveaux utilisateurs ou créer des groupes dans les Outils d’administration Analytics. </p> <p>Après la migration : </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Les administrateurs utiliseront Adobe Admin Console pour gérer leurs utilisateurs et autorisations Analytics. (Vous n’utiliserez plus l’interface Gestion utilisateur d’Analytics &gt; Admin &gt; Gestion utilisateur.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Les utilisateurs accéderont à Analytics à l’aide de leur Adobe ou Enterprise ID via CX Enterprise au lieu de <span class="filepath"> my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Que se passera-t-il à la date de début de la migration ? </p> </td> 
   <td colname="col2"> <p>À 10 h 00 UTC, la date de début de la migration : </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Les groupes d’autorisations existants d’Analytics sont répliqués automatiquement dans Adobe Admin Console sous la forme de profils de produit, y compris leur description et les autorisations granulaires relatives aux suites de rapports, aux mesures, aux dimensions et aux outils Analytics et de suite de rapports. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Si certains de vos utilisateurs Analytics actuels ont été créés dans Adobe Admin Console (signifiant qu’ils disposent d’un Adobe/Enterprise ID lié), ils sont ajoutés aux profils de produit appropriés dans Adobe Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">La section Gestion des utilisateurs de l’onglet Admin d’Analytics est définie <span class="term"> lecture seule</span>. Vous ne pourrez plus créer d’utilisateurs ou de groupes d’autorisations dans cette section et devrez effectuer ces deux actions via Adobe Admin Console. Pour plus d’informations, consultez <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Fonctionnalités d’Analytics non prises en charge par Adobe Admin Console</a>. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">En tant qu’administrateur, il vous sera accordé un accès à l’outil <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md">Migration de l’ID utilisateur</a>. En outre, une notification intégrée au produit s’affiche, incluant la date de fin de la migration (généralement 60 jours dans le futur) en plus de liens vers le contenu de l’aide et les FAQ. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Vous aurez accès à l’onglet Autorisations dans Adobe Admin Console qui permet de créer des profils de produit avec toutes les options granulaires que vous connaissez dans Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Comment migrer les ID utilisateur ? </p> </td> 
   <td colname="col2"> <p> Cliquez <a href="/help/admin/tools/user-management/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrer les ID utilisateur</a> sur la page Admin de la section Gestion utilisateur. Utilisez l’outil pour ajouter des utilisateurs à des profils de produit dans Adobe Admin Console (copiés depuis les groupes d’autorisations dans Analytics). Vous pouvez migrer les ID utilisateur à votre propre rythme. </p> <p>Des privilèges d’administration sont requis. Une fois la migration terminée, elle ne peut pas être inversée. </p> <p>À la date de fin de la migration, l’accès à <span class="filepath"> my.omniture.com</span> est désactivé pour les utilisateurs dans leur société de connexion. Les utilisateurs (y compris ceux qui ne sont pas encore migrés) seront redirigés vers la connexion via la nouvelle URL d’entreprise CX (<span class="filepath"> experiencecloud.adobe.com</span>) </p> <p>Remarque : Adobe recommande d’en profiter pour effectuer un audit des utilisateurs et des groupes avant la migration. Supprimez les comptes anciens et non utilisés ou bien les comptes qui ne doivent plus avoir accès au produit (par exemple les employés n’appartenant plus à l’organisation). </p> <p>Rubrique connexe : <a href="/help/admin/tools/user-management/user-migration/migrate-enterprise.md">Migration de comptes d’utilisateurs Analytics sous la forme d’Enterprise ID et de Federated ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La migration aura-t-elle une incidence sur mon implémentation Analytics ou sur la manière dont les données sont collectées ? </p> </td> 
   <td colname="col2"> <p>Non. </p> <p>L’outil de migration existe pour vous aider à effectuer la transition des ID utilisateur et des autorisations d’Analytics User Management vers <a href="https://adminconsole.adobe.com/enterprise/"> CX Enterprise Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Combien de temps dure le processus de migration ? </p> </td> 
   <td colname="col2"> <p>Tous les administrateurs Analytics actuels recevront un e-mail de notification quatre semaines avant la migration. (La date de début réelle apparaîtra dans l’interface d’Analytics.) </p> <p>Lorsque la migration commencera, les administrateurs disposeront de 60 jours pour terminer le processus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je accélérer ma migration ? </p> </td> 
   <td colname="col2"> <p>Oui. Toutefois, Adobe vous recommande d’utiliser la durée avant le début de la migration pour : </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">vérifier que vous êtes un administrateur produit Analytics dans Adobe Admin Console ; </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Informez votre base d’utilisateurs que leur expérience de connexion changera lorsque la migration commencera. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Contrôlez vos utilisateurs et autorisations actuels et effectuez des activités de nettoyage. </li> 
    </ul> <p>Pour accélérer votre migration, contactez l’équipe chargée de votre compte Adobe à <a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html">’assistance clientèle d’Adobe</a> et demandez une date de début plus proche. </p> </td> 
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
   <td colname="col2"> <p> Un outil qui permettra de transformer les Adobe ID en Federated ID sera bientôt disponible dans Adobe Admin Console. Pendant la migration, vous ne pouvez pas migrer les utilisateurs sous la forme de Federated ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Que savoir au cours de la migration (FAQ) {#section-d394524aa6d046d79025bbd7499792bc}

Informations importantes sur le processus de migration et son impact sur la gestion actuelle des utilisateurs et utilisatrices.

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
   <td colname="col2"> <p>Un groupe Analytics migré est nommé <i>Profil de produit</i> dans Adobe Admin Console. Les paramètres d’autorisation pour le groupe d’origine sont conservés dans la migration. Toutefois, les utilisateurs affectés au groupe ne sont pas migrés. Lorsqu’un utilisateur appartenant à ce groupe fait l’objet d’une migration à l’aide de l’outil de migration, il est affecté à ce profil de produit. </p> <p>Par exemple, un groupe d’autorisations Opérations de la côte Ouest qui autorisait ses membres à accéder à Report Builder et Analysis Workspace (avec certaines suites de rapports, mesures, dimensions) deviendra un profil de produit Opérations de la côte Ouest. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je déléguer l’effort de migration à un autre administrateur ? </p> </td> 
   <td colname="col2"> <p>Une fois la migration commencée, tout administrateur qui accède à votre instance Analytics par l’intermédiaire de CX Enterprise peut utiliser l’outil de migration pour commencer (ou continuer) la migration des utilisateurs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je mettre à jour l’appartenance à un groupe d’autorisations pour les utilisateurs non migrés ? </p> </td> 
   <td colname="col2"> <p>Oui. Vous pouvez modifier l’appartenance à un groupe des utilisateurs non migrés à partir de la section Gestion des utilisateurs d’Analytics . </p><p>En attente d’éclaircissements d’Ashok sur ce qui a été fait. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je créer des utilisateurs et des groupes d’autorisations dans Analytics une fois la migration commencée, puis utiliser l’outil de migration pour les déplacer vers Adobe Admin Console ? </p> </td> 
   <td colname="col2"> <p> Non. Une fois la migration commencée, tous les nouveaux utilisateurs et groupes d’autorisations (appelés Profils de produit dans Adobe Admin Console) doivent être créés dans Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les utilisateurs que je migre à l’aide de l’outil de migration se verraient-ils attribuer les mêmes autorisations que celles d’Analytics ? </p> </td> 
   <td colname="col2"> <p>Oui. Les utilisateurs migrés à l’aide de l’outil se verront accorder les autorisations dont ils disposent actuellement dans Analytics. En outre, ils conservent l’accès à leurs ressources Analytics (telles que les segments, les projets, les mesures calculées, etc.) lorsqu’ils accèdent à Analytics par le biais de l’expérience client Entreprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les utilisateurs que je migre vers Adobe Admin Console ont-ils toujours accès à Analytics par l’intermédiaire de <span class="filepath">my.omniture.com</span> ? </p> </td> 
   <td colname="col2"> <p>Oui. Les utilisateurs migrés continuent d’avoir accès à Analytics à l’aide de leurs nom d’utilisateur et mot de passe actuels par l’intermédiaire de <span class="filepath"> my.omniture.com</span> jusqu’à la date de fin de la migration, sauf si vous désactivez leur accès au compte hérité via l’outil de migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plusieurs de mes utilisateurs possèdent le même ID d’e-mail dans leur enregistrement Analytics. Que se passe-t-il si je les migre ? </p> </td> 
   <td colname="col2"> <p>Comme les comptes d’utilisateurs d’Adobe Admin Console requièrent des ID d’e-mail uniques, vous rencontrerez l’erreur « ID d’e-mail en double » lorsque vous tenterez de migrer plusieurs de ces utilisateurs ou utilisatrices. Vous pouvez mettre à jour les ID d’e-mail des utilisateurs non migrés sous la section Gestion des utilisateurs (héritée) avant de relancer la migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Que faire après la migration de mes utilisateurs ? </p> </td> 
   <td colname="col2"> <p>Désactivez l’accès de leur compte hérité à <span class="filepath"> my.omniture.com</span>. Vous ne pourrez pas désactiver les comptes hérités à moins qu'ils n'aient été migrés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je suivre le processus de migration ? </p> </td> 
   <td colname="col2"> <p>L’outil de migration comprend un tableau de bord qui indique combien d’utilisateurs ont été migrés avec succès et combien d’entre eux ont leur ancienne connexion désactivée. </p> <p> Idéalement, vous aurez réussi la migration de votre société de connexion vers Adobe Admin Console lorsque 100 % des utilisateurs auront terminé la migration et que leurs comptes hérités auront été désactivés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Je dois gérer les utilisateurs et les autorisations pendant la migration. Quel outil puis-je utiliser pour effectuer cette tâche ? </p> </td> 
   <td colname="col2"> <p>Une fois la migration commencée, vous utiliserez Adobe Admin Console pour créer et gérer de nouveaux utilisateurs et profils de produit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Que vivent mes utilisateurs et utilisatrices lorsque je les migre à l’aide de l’outil ? </p> </td> 
   <td colname="col2"> <p>Ils recevront un e-mail de bienvenue adressé à l’ID d’e-mail dans leur enregistrement d’utilisateur Analytics, les informant de leur nouvelle façon d’accéder à Analytics via l’expérience client Enterprise. S’ils ne disposent pas d’une Adobe ID existante, ils sont invités à en créer une, après quoi ils peuvent accéder à la solution à l’aide de leur Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puis-je utiliser des API pour migrer mes utilisateurs au lieu d’utiliser l’outil de migration ? </p> </td> 
   <td colname="col2"> <p>Non. Vous devez utiliser l’outil de migration pour vous assurer que tous les utilisateurs existants sont migrés vers Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quelles fonctionnalités de gestion des utilisateurs d’Analytics ne sont pas disponibles dans Adobe Admin Console ? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Transfert de ressources </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Expiration utilisateur </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Journaux des utilisateurs </li> 
    </ul> <p>Ils resteront à votre disposition dans la gestion des utilisateurs Analytics. </p> <p>Pour plus d’informations, consultez <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md">Fonctionnalités d’Analytics non prises en charge par Adobe Admin Console</a>. </p> </td> 
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
   <td colname="col2"> <p>Après la date de fin de la migration (60 jours à compter du début de la migration), tous les utilisateurs de votre société de connexion sont redirigés vers la page de connexion d’entreprise CX à l’aide de leurs Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Je n'ai pas pu migrer tous mes utilisateurs à la date de fin de la migration. Les utilisateurs non migrés perdraient-ils leur accès à Analytics ? </p> </td> 
   <td colname="col2"> <p>Les utilisateurs qui n’ont pas été migrés à la date de fin seront redirigés vers la page de connexion d’entreprise CX (experiencecloud.adobe.com) et ne pourront pas accéder à Analytics. Néanmoins, vous continuerez à avoir accès à l’outil de migration afin de pouvoir trouver et migrer ces utilisateurs dans le but de restaurer leur accès. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Que savoir après la migration (FAQ) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question/événement </th> 
   <th colname="col2" class="entry"> Réponses </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Suppression des utilisateurs d’Adobe Admin Console </p> </td> 
   <td colname="col2"> <p> Dans Analytics, un utilisateur supprimé est défini comme <span class="term"> ayant expiré</span> mais le compte existe toujours. La conservation du compte permet le transfert des ressources, telles que les segments, les mesures calculées, les rapports planifiés, les projets, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expirations de compte </p> </td> 
   <td colname="col2"> <p> Vous pouvez définir manuellement une date d’expiration de compte dans Analytics dans les outils d’administration. Une fois la date d’expiration atteinte, l’utilisateur ne peut plus accéder à Analytics, mais à son compte d’utilisateur d’entreprise CX (par exemple, Adobe ID, Enterprise ID, Federated ID, etc.). n'expire pas. Il peut toujours se connecter à CX Enterprise, mais il ne peut pas cliquer sur Analytics. </p> </td> 
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
   <th colname="col1" class="entry"> Question/événement </th> 
   <th colname="col2" class="entry"> Réponses </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Connexion en tant que </p> </td> 
   <td colname="col2"> <p> Les membres de l’administration migrant vers Adobe Admin Console ne pourront plus utiliser la fonction « Connexion en tant que » pour accéder aux comptes d’utilisateurs non admin qui ont été migrés vers Adobe Admin Console. Cette fonctionnalité a été retirée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration des utilisateurs et transfert de ressources </p> </td> 
   <td colname="col2"> <p> Adobe Admin Console ne prend pas en charge l’expiration des utilisateurs et le transfert des ressources. Les administrateurs utiliseront la section Utilisateurs d’Analytics et Assets sous Outils d’administration dans Analytics pour les deux fonctions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dernier accès (dernière connexion) </p> </td> 
   <td colname="col2"> <p> Les détails relatifs à la date et l’heure de la dernière connexion des utilisateurs sont disponibles via le lien Utilisateurs et ressources Analytics et non dans Adobe Admin Console. La date de dernière connexion dans Analytics est spécifique à la date à laquelle les utilisateurs ont réellement accédé à Analytics depuis CX Enterprise et ne reflète pas la date/l’heure à laquelle ils se sont connectés à CX Enterprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>API de gestion des utilisateurs <a href="https://helpx.adobe.com/fr/enterprise/using/identity.html"> Types d’identité pris en charge par Adobe</a> </p> </td> 
   <td colname="col2"> <p> Les administrateurs migrant vers Adobe Admin Console doivent configurer les API de gestion des utilisateurs fournies dans Adobe Developer pour un accès programmatique aux comptes utilisateur dans Adobe Admin Console. </p> <p>Les API d’autorisation Analytics sont désactivées lorsque vous activez la migration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Informations de connexion aux services Web </p> </td> 
   <td colname="col2"> <p> Les informations de connexion aux services Web des utilisateurs (et leur secret partagé) ne sont pas disponibles dans Adobe Admin Console. Vous pouvez y accéder en cliquant sur l’utilisateur spécifique depuis la section Utilisateurs et ressources Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Authentification unique </p> </td> 
   <td colname="col2"> <p> Les configurations d’authentification unique d’Analytics seront supprimées une fois la migration terminée. Ils resteront actifs pendant la migration. Les clients qui utilisent la connexion unique Analytics doivent effectuer une mise à niveau vers <a href="https://helpx.adobe.com/fr/enterprise/using/identity.html"> Adobe Federated ID</a>. </p> <p>Analytics recommande d’abord de migrer vos utilisateurs sous la forme d’Adobe ID pour créer facilement des comptes d’entreprise CX, puis de convertir ces comptes en utilisateurs Federated Single Sign. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Téléchargement des groupes d’autorisations </p> </td> 
   <td colname="col2"> <p> Le téléchargement des informations relatives aux groupes d’autorisations ne sera plus pris en charge, que ce soit dans les outils d’administration Analytics ou dans Adobe Admin Console. Les clients doivent utiliser les API User Management d’adobe.io pour obtenir en bloc des informations sur les groupes d’autorisations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date de création du compte </p> </td> 
   <td colname="col2"> <p>Les informations de date de création de compte ne sont plus prises en charge dans les outils d’administration Analytics ou dans Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Courriers électroniques en masse </p> </td> 
   <td colname="col2"> <p>Les courriers électroniques en masse destinés aux utilisateurs ne seront plus pris en charge, que ce soit dans les outils d’administration Analytics ou dans Adobe Admin Console. Les clients peuvent exporter en masse les adresses électroniques de leurs utilisateurs depuis Adobe Admin Console et envoyer un courrier électronique en utilisant le client de messagerie qu’ils souhaitent. </p> </td> 
  </tr> 
 </tbody> 
</table>
