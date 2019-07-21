---
description: valeur nulle
keywords: groupes ; autorisations
seo-description: valeur nulle
seo-title: Modifications des autorisations d'utilisateur et de groupe
solution: Analytics
subtopic: Utilisateurs et groupes
title: Modifications des autorisations d'utilisateur et de groupe
topic: Outils d’administration
uuid: 94 f 2727 b -17 e 4-4003-a 222-35 c 821 d 6959 e
translation-type: tm+mt
source-git-commit: 0837416ae67936fbf81af2b7051a7ed9f522f5b5

---


# Modifications des autorisations d'utilisateur et de groupe

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe vous avertira lorsqu’il sera temps de migrer les utilisateurs. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

## Qu’est-ce qui a changé ?{#section_2C205DE94155441B9E9D3E4C46CCF2EE}

**[!UICONTROL Admin]** &gt; **[!UICONTROL Gestion utilisateur]** &gt; **[!UICONTROL Groupes]**

>[!NOTE]
>
>En raison du nombre élevé de combinaisons d'autorisations possibles disponibles, nous ne pouvons pas fournir de documentation décrivant toutes les méthodes API pouvant être utilisées dans chaque combinaison d'autorisations. En général, les non-administrateurs qui se voient accorder un accès aux services web ne disposent que d’un accès en lecture seule aux méthodes d’API. Ils ne disposeront pas d’un accès en écriture aux méthodes.

Comme l’API et l’interface utilisent le même système d’autorisation, quelles que soit les autorisations qu’un administrateur de l’interface (Adobe Admin Console) a accordées à un particulier non-administrateur, il s’agira des mêmes autorisations que celles dont l’utilisateur dispose dans l’API.

<table id="table_D1DB0DE37752450BBCCA44DB760BB505"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Amélioration </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p id="reportaccess">Changements apportés à l’<span class="uicontrol">accès aux rapports</span> (personnalisation des groupes) </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Ajouter un nouveau groupe</span> &gt; <span class="uicontrol">Accès aux rapports</span> </p> <p>La section <span class="wintitle">Accès aux rapports</span> de la page <span class="wintitle">Définir un groupe d’utilisateurs</span> a été réduite à quatre catégories, qui vous permettent de personnaliser les droits d’accès à un niveau détaillé. </p> <p><img  src="assets/report-access.png" id="image_CB83E5C7DB4343619421A1FAA61478D0"> </img> </p> <p>Les options qui figuraient auparavant dans : </p> 
    <ul id="ul_16D5EF18D57D4608AEEDEC40D90D8828"> 
     <li id="li_F29E84C6228A464C8807F09205AEAAC6"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-analytics-tools.md#concept_C4383A6C0F5E4130875FDD3756F2E2FC" format="dita" scope="local"> Outils Analytics</a> : activez les autorisations d’utilisateurs pour les éléments généraux (facturation, journaux, etc.), la gestion des entreprises, l’accès aux services web, le Report Builder et l’intégration des Data Connectors. </p> <p> <b>Remarque</b> : Les paramètres d’entreprise de la catégorie de personnalisation d’Admin Console ont été déplacés dans les outils Analytics. </p> </li> 
     <li id="li_A6EB788162A2455E94CE54B9279A854D"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-report-suite-tools.md#concept_C94E9864349B428AB9CCE0CA4B0A40FF" format="dita" scope="local"> Outils de génération de rapports</a> : autorisations d’accès des utilisateurs aux services web, à la gestion des suites de rapports, aux outils et aux rapports et aux éléments de tableau de bord. </p> </li> 
     <li id="li_EDB0255E009B4F1CAFAF53966B41363C"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-metrics.md#concept_05D54436430E4320A48C7C685D337FBE" format="dita" scope="local"> Mesures</a> : activez les autorisations pour les événements de trafic, de conversion, personnalisés, de solution, la reconnaissance de contenu, etc. </p> </li> 
     <li id="li_8DAE87D1DEF54803A9C6FE31C01F0FB0"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-dimensions.md#concept_68B36161345341369B6D01DC7DD42A22" format="dita" scope="local"> Dimensions</a> : personnalisez l’accès des utilisateurs à un niveau plus détaillé, y compris les eVars, les rapports de trafic, les rapports de solution et les rapports de cheminement. </p> </li> 
    </ul> <p>Vous pouvez par exemple créer un groupe ayant accès à plusieurs outils Analytics (<span class="wintitle">Analysis Workspace</span>, <span class="wintitle">Reports &amp; Analytics</span> et <span class="wintitle">Report Builder</span>), avec autorisation d’accès à des mesures et dimensions spécifiques (y compris les eVars) et des fonctionnalités telles que la création de segments ou de mesures calculées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Changements apportés aux groupes prédéfinis </p> </td> 
   <td colname="col2"> <p> <b>Accès des administrateurs :</b> les groupes prédéfinis ne sont plus requis pour les administrateurs. Ces derniers ont maintenant accès à tous les éléments (outils, dimensions et mesures), ainsi qu’aux services web, au Report Builder, à Activity Map et aux Ad Hoc Analysis. </p> <p>Dorénavant, ces groupes permettent d’octroyer ou de restreindre l’accès des utilisateurs non-administrateurs. </p> <p> <b>Groupes personnalisés :</b> les groupes personnalisés remplacent les groupes prédéfinis. Les groupes prédéfinis existants seront migrés dans des groupes personnalisés du même nom. Tous les groupes personnalisés que vous avez créés seront préservés avec leurs paramètres. Toutefois, les paramètres ont été déplacés. Par exemple, les paramètres de la société (sous Personnaliser l’Admin Console) se trouvent maintenant sous <a href="../../../admin/user-management2/c-customize-report-access/groups-analytics-tools.md#concept_C4383A6C0F5E4130875FDD3756F2E2FC" format="dita" scope="local"> Personnaliser les outils Analytics</a>. </p> <p> Users belonging to <span class="term"> All Report Access</span> have been migrated to a custom group with access to: </p> 
    <ul id="ul_696A9243F5FD4AF187352C2F4B1CFDC2"> 
     <li id="li_683A0A3BB7214CFFBC61D5A4CD237F48">Toutes les dimensions </li> 
     <li id="li_D8FDBF6A32224731AB706315DEA0A03E">Toutes les mesures </li> 
     <li id="li_65ABE5C95D43444D88E63EE95C9AED05">Toutes les suites de rapports </li> 
     <li id="li_7ED1505590144B38B3B9851BAA6BBB49">Rapport Canal </li> 
     <li id="li_F718FE1FCF9A4B05AB933CA3F105F3EC">Rapport Détection des anomalies </li> 
     <li id="li_527BD52007E846FE8B5F71AB3C12F695">Rapport Temps réel </li> 
     <li id="li_AFFB58C7FB644AC8A85E2D76BA7D51F5">Accès à Analysis Workspace </li> 
    </ul> <p>Les administrateurs peuvent supprimer des groupes personnalisés et créer leurs propres groupes, puisque tous les paramètres qui étaient auparavant disponibles dans les groupes prédéfinis peuvent maintenant être personnalisés dans les paramètres <span class="wintitle">Accès aux rapports</span> sur la page <a href="../c-user-groups/groups.md" format="dita" scope="local">Définition des groupes d’utilisateurs</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorisations au niveau des dimensions </p> </td> 
   <td colname="col2"> <p>Vous pouvez personnaliser les autorisations afin d’inclure ou d’exclure l’accès aux dimensions (outre les mesures). </p> 
    <ul id="ul_DA5A54223673474E9151AF979DA50659"> 
     <li id="li_C3E82F7BC07A4F2F83A85D3D511292CC"> <p>Toutes les dimensions et les mesures actuelles des groupes personnalisés ont été automatiquement transférées dans les nouvelles catégories. Si un groupe comprend des mesures actives, il obtiendra par défaut toutes les dimensions (eVars et reconnaissance du contenu) et mesures nouvellement autorisables. </p> </li> 
     <li id="li_CC56F9181CC14AB59318628E72F2E8C9"> Droits d’accès de l’importateur de classifications (anciennement SAINT) : l’accès aux classifications est déterminé par l’accès à la <a href="https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html" format="html" scope="external">variable</a> sur laquelle repose la classification. </li> 
    </ul> <p>See <a href="../../../admin/user-management2/c-customize-report-access/groups-dimensions.md#concept_68B36161345341369B6D01DC7DD42A22" format="dita" scope="local"> Customize Dimension Permissions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Admin Console </p> </td> 
   <td colname="col2"> <p>Recommandé uniquement pour les nouveaux clients ou les clients dont les entreprises sont <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html" format="html" scope="external">configurées dans Experience Cloud</a>. Pour les clients <span class="keyword">Analytics</span> actuels, une migration est prévue vers le système de gestion des identités d’<span class="keyword">Experience Cloud</span>. </p> <p>More information is available in <a href="https://helpx.adobe.com/enterprise/using/manage-permissions-and-roles.html" format="html" scope="external"> Manage product permissions in the Admin Console</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Questions fréquentes à propos des changements des autorisations {#section_02809EFC95054B40A089E6C6E4FACA13}

Vous trouverez ci-dessous d’importantes nouvelles informations relatives aux mises à jour nouvelles et planifiées et à leurs répercussions sur l’environnement d’administration.

<table id="table_1E93F45C66E841E6882FB602509F30A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1">Quelles modifications ont été apportées aux autorisations dans la version de <b>juillet 2016</b> ? </td> 
   <td colname="col2"> <p> <b>Accès à toutes les suites de rapports</b> </p> <p>Lors de l’ajout de suites de rapports dans un groupe, vous pouvez activer l’option <span class="uicontrol">Accès à toutes les suites de rapports</span>. Ce paramètre applique les autorisations du groupe à toutes les suites de rapports actuelles et futures. </p> <p>Pour activer cette fonction, sélectionnez <span class="uicontrol">Gestion utilisateur</span> &gt; <span class="uicontrol">Groupes</span> &gt; <span class="uicontrol">Ajouter un nouveau groupe d’utilisateurs</span>, puis <span class="uicontrol">Accès à toutes les suites de rapports</span>. </p> <p><img placement="break"  src="assets/all-report-suites.png" width="300px" id="image_9E814D412E87484C940F1100D6DE2B0F" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dois-je utiliser la Console d'administration pour gérer les utilisateurs ou la gestion des utilisateurs Analytics existante ? </p> </td> 
   <td colname="col2"> <p>Les modifications apportées à Analytics &gt; Admin &gt; Gestion des utilisateurs ne sont pas répercutées dans la console d'administration. Par conséquent, seuls les nouveaux clients qui utilisent déjà la Console d'administration pour la gestion des utilisateurs et des groupes doivent continuer à le faire. Une migration pour la gestion des groupes Analytics existante vers la console d'administration est prévue. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quelles modifications ont été apportées aux autorisations dans la version d’<b>octobre 2016</b> ? </p> </td> 
   <td colname="col2"> <p>Les améliorations suivantes apportées à l’interface <span class="wintitle">Outils d’administration</span> actuelle sont disponibles : </p> <p> 
     <ul id="ul_2A31E8DC17A94B7FABDBA9C87C3947EF"> 
      <li id="li_AE2ECCA01CC64D30B109BE74379EE474">Permission changes as described in <a href="../../../admin/user-management2/c-user-management/permissions-changes.md#concept_86581595B86B47D5B8F90282FC3E31EF" format="dita" scope="local"> Administrative Changes - Fall 2016</a>. </li> 
      <li id="li_33CB2B6A2E5F45BE97CC5E0983AF280E">Retrait des rapports sur le trafic obsolètes qui ne figuraient plus dans le menu. </li> 
      <li id="li_57234CF27E1D405987DE89312CD62C52">Autorisations des classifications : L'accès aux classifications sera déterminé par l'accès à la variable pour laquelle la classification est utilisée. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Que dois-je faire pour migrer les utilisateurs ? </p> </td> 
   <td colname="col2"> <p>Vous n’avez rien à faire. Toutes les migrations d’autorisations se dérouleront de manière transparente. </p> <p> 
     <ul id="ul_654F85286EC04416B3E0BA725EBE10AD"> 
      <li id="li_8050B8941F794103B82A0ADF0930D216">Tous les rapports actuels sur le trafic dans un groupe personnalisé seront automatiquement migrés dans la nouvelle catégorie Dimension. </li> 
      <li id="li_B97079DB29A346B98D066F11AB7F94AF">Si des mesures sont activées pour un groupe personnalisé, celui-ci se voit automatiquement attribuer toutes les dimensions qui peuvent nouvellement faire l’objet d’autorisations (eVars et variables de solution). </li> 
      <li id="li_F1219EF490DA473BA15F2B215F2995AE"> Un groupe personnalisé accompagné d’une mesure au moins se verra automatiquement octroyer l’accès à toutes les eVars et autres dimensions reconnaissant le contenu, <b>à l’exception</b> des nouvelles dimensions de trafic disponibles (anciennement les rapports sur le trafic). </li> 
      <li id="li_F494CE6144A04A6199CFBBA1D7BEA32B">Chaque groupe prédéfini sera modifié dans une autorisation. Ces nouvelles autorisations seront ajoutées à une nouvelle catégorie intitulée <span class="uicontrol">Outils Analytics</span>. </li> 
      <li id="li_2FCD9254FC3C4FD7871EEF9453E5CE1E">Pour chaque groupe personnalisé qui comprend des mesures, tous les événements de solution Analytics sont ajoutés comme de nouvelles mesures. </li> 
      <li id="li_34C4560769B64F28A4E83BAE71065DCC">Chaque utilisateur qui était membre du groupe Accès à tous les rapports sera ajouté au nouveau groupe personnalisé. Le groupe Accès à tous les rapports n’existera plus. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qu’est-ce qui ne change pas ? </p> </td> 
   <td colname="col2"> <p>Les Attributs des visiteurs ne peuvent toujours pas être autorisés. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Référence rapide à propos des autorisations {#section_A3FDD8259F524B21A5489833533D1B28}

Le tableau suivant répertorie les tâches et où elles peuvent avoir lieu (selon l’état de l’entreprise).

>[!NOTE]
>
>A *`migrated user`* and *`Experience Cloud user`* refer to users who have accepted an email invitation to join the Experience Cloud. Si l'invitation par courrier électronique n'est pas acceptée, les utilisateurs restent des utilisateurs Analytics et ne peuvent pas être gérés dans la console d'administration. (sauf si la migration utilise des [Entreprise ID ou Federated ID](https://helpx.adobe.com/enterprise/using/set-up-identity.html), auquel cas l’utilisateur est migré quand l’administrateur migre les utilisateurs au cas par cas).

<table id="table_B68FD00FC5D24823A86BB69558C0327C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tâche </th> 
   <th colname="col2" class="entry"> Société utilisée pour la connexion qui ne migre pas </th> 
   <th colname="col3" class="entry"> Société en cours de migration </th> 
   <th colname="col4" class="entry"> Société utilisée pour la connexion pour laquelle la migration est finie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Créer un utilisateur </td> 
   <td colname="col2"> <p>Admin Console (creating a user and adding him or her to an Analytics <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> product configuration</a> also creates the user account in Analytics). </p> <p> <a href="../../../admin/user-management2/c-user-management/t-add-user-account.md#task_60F86F36CB86446699EA7C7E5FB03EA7" format="dita" scope="local"> Outils d’administration</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Console d’administration</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Console d’administration</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modifier un utilisateur </td> 
   <td colname="col2"> <p> <a href="../../../admin/user-management2/c-user-management/t-add-user-account.md#task_60F86F36CB86446699EA7C7E5FB03EA7" format="dita" scope="local"> Outils d’administration</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Console d’administration</a> </p> <p> Outils d’administration – La modification dans les outils d’administration des utilisateurs migrés se limite à la gestion des clés API, ainsi qu’à la suppression et au transfert des ressources. </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Console d’administration</a> </p> <p> Outils d’administration – La modification se limite à la gestion des clés API, ainsi qu’à la suppression et au transfert des ressources. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Supprimer un utilisateur </td> 
   <td colname="col2"> <p>Console d'administration - Pour les utilisateurs d'Experience Cloud </p> <p>Outils d’administration – Pour tous les utilisateurs ; pour les utilisateurs d’Experience Cloud, supprime seulement l’utilisateur Analytics mappé et non le compte Experience Cloud. </p> </td> 
   <td colname="col3"> <p>Console d'administration - Pour les utilisateurs migrés. </p> <p>Outils d’administration – Seulement pour les utilisateurs d’Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> <p> Outils d'administration : après avoir supprimé un utilisateur Experience Cloud ou dissocié son compte dans la console d'administration, vous pouvez supprimer la connexion Analytics à partir des outils d'administration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Connexion à Analytics </td> 
   <td colname="col2"> <p> <b>Experience Cloud : </b> <span class="filepath"> marketing.adobe.com</span>. Pour les utilisateurs d’Experience Cloud seulement. </p> <p> <b>Analytics (hérité) :</b> <span class="filepath">sc.omniture.com</span>. Pour les utilisateurs d’Analytics seulement, ainsi que pour les utilisateurs d’Experience Cloud avec leurs informations d’identification Analytics. </p> </td> 
   <td colname="col3"> <p> <span class="filepath">marketing.adobe.com</span> – Seulement pour les utilisateurs d’Experience Cloud. </p> <p> <span class="filepath"> sc.omniture.com</span> – Pour les utilisateurs d’Analytics seulement, ainsi que pour les utilisateurs d’Experience Cloud avec leurs informations d’identification Analytics. </p> <p>Durant la migration, les administrateurs peuvent désactiver la capacité de connexion <span class="filepath">omniture.com</span> pour certains utilisateurs. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Créer un groupe </td> 
   <td colname="col2"> <p>Console d'administration : lorsqu'un groupe est créé dans la console d'administration, un groupe mappé dans Analytics s'affiche dans les outils d'administration, mais ce groupe mappé ne peut pas avoir changé son nom ni ses outils d'administration ni être supprimé des outils d'administration. </p> <p>Outils d’administration. </p> </td> 
   <td colname="col3"> <p>Admin Console (<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> create product configuration</a>) </p> </td> 
   <td colname="col4"> <p>Admin Console (<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> create product configuration</a>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modifier les utilisateurs d’un groupe </td> 
   <td colname="col2"> <p>Console d'administration - Uniquement pour les utilisateurs d'Experience Cloud </p> <p>Outils d’administration – Pour les utilisateurs d’Analytics seulement et pour les utilisateurs d’Experience Cloud membres de groupes qui peuvent être modifiés dans les outils d’administration. Toutefois, si un utilisateur Experience Cloud fait partie d'un groupe dans la console d'administration, il ne peut pas être supprimé du groupe dans les outils d'administration. </p> </td> 
   <td colname="col3"> <p>Console d'administration - Utilisateurs Experience Cloud uniquement </p> <p> Outils d’administration – Il est toujours possible d’ajouter ou de supprimer les identifiants de connexion Analytics seulement des groupes dans les outils d’administration. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modifier les autorisations d’un groupe </td> 
   <td colname="col2"> <p>Console d'administration : vous pouvez modifier les groupes créés dans la console d'administration. </p> <p>Outils d’administration – Vous pouvez modifier les autorisations de n’importe quel groupe. </p> </td> 
   <td colname="col3"> <p>Console d’administration </p> </td> 
   <td colname="col4"> <p>Console d’administration </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Supprimer le groupe </td> 
   <td colname="col2"> <p>Console d'administration : vous pouvez supprimer uniquement les groupes créés dans la console d'administration. </p> <p>Outils d’administration – Vous pouvez supprimer uniquement les groupes créés dans les outils d’administration. </p> </td> 
   <td colname="col3"> <p>Console d’administration </p> </td> 
   <td colname="col4"> <p>Console d’administration </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modifier le statut d’administrateur d’un utilisateur </td> 
   <td colname="col2"> <p>Console d'administration - Uniquement pour les utilisateurs d'Experience Cloud. </p> <p>Outils d’administration </p> </td> 
   <td colname="col3"> <p>Console d'administration - Uniquement pour les utilisateurs d'Experience Cloud. </p> <p>Outils d’administration – Seulement pour les utilisateurs d’Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
 </tbody> 
</table>
