---
description: Découvrez les étapes de l’intégration des connecteurs de données DFA.
seo-description: Découvrez les étapes de l’intégration des connecteurs de données DFA.
seo-title: Configuration de l’intégration DFA
title: Configuration de l’intégration DFA
uuid: 4 c 2 ac 58 a -87 c 6-46 f 3-9033-9404 beb 18 c 39
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configuration de l’intégration DFA{#configure-the-dfa-integration}

Découvrez les étapes de l’intégration des connecteurs de données DFA.

Les pages de configuration présentent un aperçu de l’intégration, ainsi que des liens utiles conduisant vers davantage d’informations. Cette intégration engendre des frais Adobe et DoubleClick. Contactez votre représentant commercial au sujet des deux organisations et veillez à comprendre la structure des frais.

1. Log in to the [!DNL Adobe Analytics].
1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. Locate **[!UICONTROL DoubleClick DFA]**, then click **[!UICONTROL Add New]**.

   ![Résultat de l’étape](assets/wizard-01.png)

   On each page of the Integration Wizard, provide the required information, then click **[!UICONTROL Next]**. Le tableau suivant explique quelles sont les informations nécessaires pour exécuter l’intégration à l’aide de l’assistant.

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> N° de page de l’Assistant </th> 
   <th colname="col2" class="entry"> Champ </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Nom d’intégration </td> 
   <td colname="col3"> Nom d’intégration affiché par Genesis dans la liste d’intégration active de la suite de rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Adresse de courriel d’intégration </td> 
   <td colname="col3"> Adresse électronique qui reçoit toutes les notifications liées à cette intégration. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Nom d’utilisateur </td> 
   <td colname="col3"> Nom d’utilisateur de l’API DFA à utiliser avec cette intégration. Afin qu’un utilisateur puisse se connecter à l’API, vérifiez l’attribut de cette dernière dans l’interface DFA. Ensuite, un champ de mot de passe s’affiche où vous pouvez spécifier un mot de passe pour l’utilisateur. Ce mot de passe est saisi avec le nom d’utilisateur dans l’assistant pour authentification. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Mot de passe </td> 
   <td colname="col3"> Mot de passe de l’API DFA. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Identifiant publicitaire </td> 
   <td colname="col3"> <p>Identifiant de publicitaire DFA ou identifiant de configuration Floodlight parent. La fonctionnalité Connecteurs de données utilise cet identifiant afin d’identifier le publicitaire DFA à suivre (version 1.5 de l’intégration). Cet identifiant publicitaire n'est pas utilisé dans la version 2.0 de l'intégration : l'identifiant de configuration Floodlight parent est recherché et utilisé. Suivez les instructions à l’écran. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> Variable publicitaire DFA </td> 
   <td colname="col3"> eVar Analytics qui reçoit l’attribut de campagne DFA et les données sur les impressions et les clics. Généralement, il s’agit de l’eVar du code de suivi ( <span class="varname"> s. campaign </span>), mais vous pouvez choisir n'importe quelle evar disponible. Connecteurs de données ajoute également les classifications DFA suivantes à l’eVar sélectionnée : <p><b>Campagnes</b> : collection des publicités diffusées sur plusieurs sites qui convoient un message commun. </p> <p><b>Nom du site</b> : site où était diffusée la publicité. </p> <p><b>Nom de la publicité</b> : nom de la publicité, comme défini dans votre compte DFA. </p> <p><b>Site Placement Name</b> (Nom de référencement du site) : site web et page où était diffusée la publicité. </p> <p><b>Delivery Tool</b> (Outil de remise) : DoubleClick for Advertisers. </p> <p><b>Canal</b> : bannière publicitaire. </p> <p><b>Cost Structure</b> (Structure de coûts) : coût par million, coût par clic ou coût fixe, selon la structure de coûts de la publicité. </p> <p><b>Creative Name</b> (Nom du créatif) : nom du créatif associé à une publicité, un référencement et un identifiant de créatif. </p> <p><b>DFA &gt; Déduplication SearchCenter</b> : spécifie que DFA référence les valeurs dans les variables SearchCenter en cas de clics ou affichages publicitaires DFA. Pour en savoir plus, voir <a href="../../dfa-data-connector-analytics/dfa-integration-features.md#concept-ff93289d1662410e98f62c200394b3e3" format="dita" scope="local">Déduplication SearchCenter</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Impressions </td> 
   <td colname="col3"> Événement personnalisé qui reçoit les données des mesures d’impressions DFA. Les impressions indiquent le nombre de fois où la publicité a été diffusée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Clics </td> 
   <td colname="col3"> Sélectionnez l’événement personnalisé qui reçoit les données des mesures de clics DFA. Les clics indiquent le nombre de fois où les visiteurs ont cliqué sur la publicité, comme mesuré par la redirection de DFA. La mesure Clics établit la corrélation avec la mesure de clics publicitaires Analytics. <p>Remarque : Les clics DFA et les clics publicitaires Analytics peuvent ne pas correspondre exactement car les données sont collectées différemment. For more information, see <a href="../../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-metric-definitions.md#concept-2d5cd5ddd2594bb386a16a2764f30982" format="dita" scope="local"> Metric Definitions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> View-Through Variable (Variable d’affichage publicitaire) </td> 
   <td colname="col3"> <p>eVar Analytics qui reçoit les données d’affichage publicitaire DFA. La variable d’affichage publicitaire permet de savoir de quelle façon les affichages publicitaires affectent les taux de conversion sur votre site. </p> <p>La fonctionnalité Connecteurs de données ajoute les mêmes classifications liées à DFA pour cette eVar que pour la variable publicitaire DFA (voir ci-dessus). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Time Since Last View (Durée depuis le dernier affichage) (variable d’intervalle de temps de l’affichage publicitaire) </td> 
   <td colname="col3"> eVar Analytics qui reçoit les données de durée depuis le dernier affichage DFA. La durée depuis le dernier affichage correspond à la durée écoulée depuis le dernier affichage publicitaire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Affichages publicitaires </td> 
   <td colname="col3"> Événement personnalisé qui reçoit les données des mesures d’affichages publicitaires DFA. Utilisez l’événement d’affichages publicitaires avec la variable d’affichage publicitaire pour savoir quelles campagnes n’ont pas influencé un affichage publicitaire direct, mais peuvent avoir joué un rôle pour orienter le trafic vers le site à un moment consécutif. <p>La fonctionnalité Connecteurs de données renomme l’événement personnalisé sélectionné en « affichages publicitaires ». </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Échec de la requête DFA </td> 
   <td colname="col3"> (Facultatif) eVar Analytics qui reçoit les codes de message d’erreur de requête DFA signalés. Codes de message DFA possibles : 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b> : aucun cookie DoubleClick. </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b> : l’utilisateur s’est désabonné. </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b> : aucun historique de campagne. </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b> : erreur de requête (délai dépassé, serveur en panne, etc.). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Événement de dépassement de délai </td> 
   <td colname="col3"> <p>Événement de compteur Analytics qui s’incrémente chaque fois que le délai <span class="varname"> s. maxdelay </span> expire et aucune réponse n'a été reçue des serveurs DFA. Use this event to configure the <span class="varname"> s.maxDelay </span> variable (see <a href="../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d" format="dita" scope="local"> Tuning s.maxDelay </a>.) </p> </td> 
  </tr> 
 </tbody> 
</table>

