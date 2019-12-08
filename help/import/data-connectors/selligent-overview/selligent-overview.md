---
description: valeur nulle
title: Connecteur de données intelligent pour Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Selligent Data Connector for Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

Cette intégration présente les principaux avantages suivants :

* Consolidez les données de marketing et d’analyse par courrier électronique dans une interface de création de rapports unique.
* Optimisez les campagnes par courrier électronique par conversion et contribution aux recettes et aux réussites du site.
* Commercialisez à nouveau les visiteurs clés et les segments de marché en fonction des segments marketing dynamiques.

## Segments de marketing dynamique {#section-a2216f3339304636bd5417249bd635a4}

Cette intégration de courriel prend en charge les segments de marketing dynamique pour vous aider à diriger votre entreprise. Cette intégration comprend les segments marketing suivants, prêts à l’emploi :

| Segment | Description |
|---|---|
| **Profil d'abandon du panier** | Aidez les visiteurs à se convertir en clients grâce à des campagnes affinées spécialement conçues pour ceux qui hésitent à compléter leur panier. |
| **Profil Achats** | Augmentez les commandes répétées et la valeur moyenne des commandes grâce aux campagnes ciblées par les modèles d’achat des visiteurs. |
| **Profil comportemental Affichage du produit/du contenu** | Contactez les clients potentiels par le biais de segments marketing basés sur les consultations de produits et le profilage de l’accès au contenu. |
| **Segments de remarketing personnalisés** | Les clients peuvent également créer et planifier des segments de remarketing personnalisés spécifiques aux besoins de leurs utilisateurs. |

## Avant d’activer cette intégration{#before-you-activate-this-integration}

Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements d’Adobe Analytics et de votre logiciel de messagerie électronique.

Cela permettra de s’assurer que les meilleures pratiques et les conditions préalables appropriées sont en place avant l’activation. Cela se traduira par une intégration optimale et réussie.

## Conditions préalables requises pour Adobe Analytics{#prerequisites-for-adobe-analytics}

Répertorie les actions nécessaires à effectuer dans Adobe Analytics avant de pouvoir déployer l’intégration.

| Condition requise | Remarques |
|---|---|
| Sélectionner une suite de rapports | Notez que cette intégration est spécifique à une suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports de votre choix avant d’activer l’intégration. |
| Configuration des variables Analytics | Cette intégration requiert des événements personnalisés et des eVars personnalisées, ainsi que éventuellement des événements supplémentaires et des eVars supplémentaires. Voir Configuration des variables Analytics pour la sélection. |
| Représentant autorisé | Notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, selon le cas. En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise ; et, à ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans l'accord de service décrit ci-dessus. |
| Activer Adobe Data Warehouse™ | Cette intégration requiert l’activation de l’entrepôt de données pour générer des segments de remarketing. Si vous n’avez pas activé l’entrepôt de données Adobe, contactez Adobe pour plus de détails. |
| Recipient ID | L’intégration requiert que nous capturions et stockions un "identifiant visiteur" dans une variable Analytics (eVar). L’identifiant visiteur (souvent appelé "ID du destinataire") est une représentation codée ou numérique d’une adresse électronique du système sélectif. Cet "ID de destinataire" est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui est récupéré dans le système sélectif et peut être utilisé à des fins de remarketing. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l'Assistant vous y invite. |
| Suivi externe | Si vous ne suivez pas actuellement la bonne pratique consistant à activer le suivi externe pour chaque campagne par courrier électronique envoyée, vous devez le faire pour garantir une intégration réussie. Pour plus d’informations, reportez-vous à la section Sélection ci-dessous. |
| Respect de la confidentialité | Vous devez comprendre qu’en activant le suivi des destinataires ou des identifiants des visiteurs, cette fonctionnalité peut effectuer le suivi des informations d’identification personnelle des visiteurs de votre site. Cela a des implications en matière de confidentialité qui nécessitent la mise en oeuvre de procédures appropriées par votre organisation, comme la notification et le consentement des visiteurs de votre site. |

## Configuration des variables Analytics pour la sélection{#configure-analytics-variables-for-selligent}

Cette intégration requiert 2 eVars à réserver pour chaque implémentation de suite de rapports.

Outre ces eVars, certains événements peuvent être réservés en fonction des données de la fonctionnalité de suivi sélectif, que vous souhaitez voir dans Analytics. Ces eVars et événements sont décrits ci-dessous :

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
   <td colname="col2"> ID du message </td> 
   <td colname="col3"> Pour capturer l’identification de campagne d’un message électronique individuel. </td> 
   <td colname="col4"> <p><b>État</b>: Activé </p> <p><b>Affectation</b>: Le plus récent </p> <p><b>Expire après</b>: "Décision commerciale" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> Pour capturer l’identification anonyme de votre client qui a cliqué sur la campagne par courrier électronique. </td> 
   <td colname="col4"> <p><b>État</b>: Activé </p> <p><b>Affectation</b>: Le plus récent </p> <p><b>Expire après</b>: "Décision commerciale" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Envoyé </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques envoyés par Selligent. </td> 
   <td colname="col4"> <p><b>Type</b>: Numérique </p> <p><b>Participation</b>: Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Livré </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques livrés. </td> 
   <td colname="col4"> <p><b>Type</b>: Numérique </p> <p><b>Participation</b>: Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Vues </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques uniques qui ont été consultés. </td> 
   <td colname="col4"> <p><b>Type</b>: Numérique </p> <p><b>Participation</b>: Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Clics </td> 
   <td colname="col3"> Pour stocker le nombre de clics sur un e-mail. </td> 
   <td colname="col4"> <p><b>Type</b>: Numérique </p> <p><b>Participation</b>: Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Rebond </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques qui ont été reportés. </td> 
   <td colname="col4"> <p><b>Type</b>: Numérique </p> <p><b>Participation</b>: Activé </p> </td> 
  </tr> 
 </tbody> 
</table>

## Conditions préalables pour sélectif{#prerequisites-for-selligent}

Répertorie les informations nécessaires à fournir à partir de votre compte sélectif avant de pouvoir déployer l’intégration.

**Compte sélectif valide**

Pour utiliser cette intégration des Connecteurs de données, vous devez disposer d’un compte sélectif valide.

**Informations du compte**

Vous aurez besoin des informations suivantes sur votre compte sélectif lors de cette configuration de l’intégration :

* **URL** du service Adobe :

   L’URL peut être dérivée de l’URL utilisée pour se connecter à la solution de marketing sélectif. Remplacez la partie "/simweb/login.aspx" de l’URL par "/automation/omniture.asmx".

   E.g: `http://<client-specific install url>/automation/omniture.asmx`

* **** Paramètres de chaîne de requête : Ces informations sont ajoutées à l’URL de la page d’entrée pour l’ID de message et l’ID de destinataire (identifiant visiteur). Il s’agit toujours du MID et du RID pour l’ID de message et l’ID de destinataire respectivement.

* **Jeton** d’intégration Lancez l’outil Manager depuis Simweb et accédez à **[!UICONTROL Configuration]** &gt; Paramètres **** système &gt; onglet **[!UICONTROL Général]** &gt; Système. **** Sous **[!UICONTROL Security]**, vous trouverez le jeton d’intégration.

   ![](assets/selligent-integration_token.png)
