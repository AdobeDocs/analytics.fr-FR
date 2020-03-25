---
description: valeur nulle
title: Connecteur de données Selligent pour Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Connecteur de données Selligent pour Adobe Analytics {#selligent-data-connector-for-adobe-analytics}

Cette intégration présente les principaux avantages suivants :

* Consolidation des données d’analyse et de marketing par e-mail dans une interface de création de rapports.
* Optimisation des campagnes par e-mail par le biais de conversions et de contributions au chiffre d’affaires et au succès du site.
* Re-commercialisation auprès des segments de marché et visiteurs clés en fonction des segments de marketing dynamique.

## Segments de marketing dynamique {#section-a2216f3339304636bd5417249bd635a4}

Cette intégration de messagerie électronique prend en charge les segments de marketing dynamique pour vous aider à stimuler l’activité commerciale de votre entreprise. Cette intégration comprend les segments marketing suivants, prêts à l’emploi :

| Segment | Description |
|---|---|
| **Profil d’abandon de panier** | Aidez les visiteurs à se convertir en clients grâce à des campagnes ciblées spécialement conçues pour les visiteurs qui hésitent à valider leur panier. |
| **Profil Achats** | Augmentez les commandes répétées et la valeur moyenne des commandes grâce à des campagnes ciblées en fonction des habitudes d’achat des visiteurs. |
| **Profil comportemental de vues de produit/contenu** | Atteignez les clients potentiels grâce à des segments marketing basés sur les vues des produits et la création de profils utilisateur basée sur l’accès au contenu. |
| **Segments de remarketing personnalisés** | Les clients peuvent également créer et planifier des segments de remarketing personnalisés spécifiques aux besoins de leurs utilisateurs. |

## Avant l’activation de cette intégration {#before-you-activate-this-integration}

Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements Adobe Analytics et à votre logiciel de messagerie électronique.

Cela permettra de s’assurer que les bonnes pratiques et les conditions préalables appropriées sont déjà en place avant l’activation. Cela se traduira par une intégration optimale et réussie.

## Conditions préalables pour Adobe Analytics {#prerequisites-for-adobe-analytics}

Répertorie les actions nécessaires à effectuer dans Adobe Analytics avant de pouvoir déployer l’intégration.

| Condition requise | Remarques |
|---|---|
| Sélectionner une suite de rapports | Notez que cette intégration est spécifique à une suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports de votre choix avant d’activer l’intégration. |
| Configuration des variables Analytics | Cette intégration requiert des événements et des eVars personnalisés et, éventuellement, des événements et des eVars supplémentaires. Voir Configuration des variables Analytics pour Selligent. |
| Représentant autorisé | Notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, selon le cas. En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise. À ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans le contrat de service décrit ci-dessus. |
| Activer Adobe Data Warehouse™ | Cette intégration requiert l’activation de Data Warehouse pour générer des segments de remarketing. Si vous n’avez pas activé Adobe Data Warehouse, contactez Adobe pour plus de détails. |
| Recipient ID | L’intégration requiert que nous capturions et stockions un « identifiant visiteur » dans une variable Analytics (eVar). L’identifiant visiteur (souvent appelé « ID de destinataire ») est une représentation codée ou numérique d’une adresse électronique du système Selligent. Cet « ID de destinataire » est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui est récupéré dans le système Selligent et peut être utilisé à des fins de remarketing. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l’assistant vous y invite. |
| Suivi externe | Si vous ne respectez pas actuellement la bonne pratique consistant à activer le suivi externe pour chaque campagne par e-mail envoyée, vous devez le faire pour garantir le succès de l’intégration. Pour plus d’informations, reportez-vous à la section Selligent ci-dessous. |
| Respect de la confidentialité | Vous devez comprendre qu’en activant le suivi des identifiants destinataires ou visiteurs, cette fonctionnalité peut effectuer le suivi des informations d’identification personnelle des visiteurs de votre site. Cela entraîne des répercussions en matière de confidentialité qui nécessitent la mise en œuvre de procédures appropriées par votre organisation, comme la notification et la demande de consentement auprès des visiteurs de votre site. |

## Configuration des variables Analytics pour Selligent {#configure-analytics-variables-for-selligent}

Cette intégration nécessite que 2 eVars soient réservés pour chaque mise en œuvre de suite de rapports.

Outre ces eVars, certains événements peuvent être réservés en fonction des données Selligent que vous souhaitez voir dans Analytics. Ces eVars et événements sont décrits ci-dessous :

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de variable </th> 
   <th colname="col2" class="entry"> Nom de variable </th> 
   <th colname="col3" class="entry"> Utilisation </th> 
   <th colname="col4" class="entry"> Paramètres </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de message </td> 
   <td colname="col3"> Pour capturer l’identification du message électronique individuel de la campagne. </td> 
   <td colname="col4"> <p><b>État</b> : activé </p> <p><b>Attribution</b> : le plus récent </p> <p><b>Expire après</b> : « décision commerciale » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> Pour capturer l’identification anonyme de votre client qui a cliqué sur la campagne par e-mail. </td> 
   <td colname="col4"> <p><b>État</b> : activé </p> <p><b>Attribution</b> : le plus récent </p> <p><b>Expire après</b> : « décision commerciale » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Envoyé </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques envoyés par Selligent. </td> 
   <td colname="col4"> <p><b>Type</b> : numérique </p> <p><b>Participation</b> : activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Distribué </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques distribués. </td> 
   <td colname="col4"> <p><b>Type</b> : numérique </p> <p><b>Participation</b> : activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Vues </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques uniques qui ont été consultés. </td> 
   <td colname="col4"> <p><b>Type</b> : numérique </p> <p><b>Participation</b> : activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Clics </td> 
   <td colname="col3"> Pour stocker le nombre de clics sur un courrier électronique. </td> 
   <td colname="col4"> <p><b>Type</b> : numérique </p> <p><b>Participation</b> : activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Ont rebondi </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques qui ont rebondi. </td> 
   <td colname="col4"> <p><b>Type</b> : numérique </p> <p><b>Participation</b> : activé </p> </td> 
  </tr> 
 </tbody> 
</table>

## Conditions préalables pour Selligent {#prerequisites-for-selligent}

Répertorie les informations nécessaires à fournir à partir de votre compte Selligent avant de pouvoir déployer l’intégration.

**Compte Selligent valide**

Pour utiliser cette intégration des Data Connectors, vous devez disposer d’un compte Selligent valide.

**Informations du compte**

Vous aurez besoin des informations suivantes sur votre compte Selligent lors de cette configuration de l’intégration :

* **URL du service Adobe** :

   L’URL peut être dérivée de l’URL utilisée pour se connecter à la solution de marketing Selligent. Remplacez la partie « /simweb/login.aspx » de l’URL par « /automation/omniture.asmx ».

   Par exemple : `http://<client-specific install url>/automation/omniture.asmx`

* **Paramètres de chaîne de requête** : ces informations sont ajoutées à l’URL de la page d’entrée pour l’ID de message et l’ID destinataire (identifiant visiteur). On parle toujours de MID et de RID respectivement pour l’ID de message et l’ID de destinataire.

* **Jeton d’intégration** Lancez l’outil Manager depuis Simweb et accédez à **[!UICONTROL Configuration]** > **[!UICONTROL Paramètres système]** > onglet **[!UICONTROL Général]** > **[!UICONTROL Système]**. Vous trouverez le jeton d’intégration sous **[!UICONTROL Sécurité]**.

   ![](assets/selligent-integration_token.png)
