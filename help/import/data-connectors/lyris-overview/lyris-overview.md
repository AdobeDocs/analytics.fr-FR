---
description: Décrit les gains d’efficacité marketing réalisés grâce à l’intégration.
title: Connecteur de données Lyris pour Adobe Analytics
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Connecteur de données Lyris pour Adobe Analytics {#lyris-data-connector-for-adobe-analytics}

Décrit les gains d’efficacité marketing réalisés grâce à l’intégration.

L’intégration des courriers électroniques Adobe® Data Connectors™ combine les informations comportementales d’Adobe Analytics avec le marketing par courrier électronique Lyris pour redéfinir la mesure de succès et cibler les audiences avec des messages plus pertinents.

La diffusion de messages électroniques pertinents à ces segments de marché peut déboucher sur de nouvelles opportunités de chiffre d’affaires, ce qui entraîne une augmentation des conversions et du chiffre d’affaires parmi les campagnes par e-mail existantes et nouvelles. Par exemple, il a été démontré que la diffusion de messages électroniques pertinents basés sur les produits consultés au cours d’une visite ou laissés dans un panier d’achats abandonné a un impact considérable sur le chiffre d’affaires et un impact minimal sur les coûts, puisque ce procédé tire parti des visiteurs déjà présents sur votre site.

Cette augmentation de l’efficacité marketing est l’un des principaux avantages de l’intégration d’Adobe Analytics à Lyris. En outre, cette intégration synchronise automatiquement les mesures de courrier électronique avec les données Adobe Analytics de manière fréquente, chaque heure, pour la création de rapports en boucle fermée.

## Principaux avantages et fonctionnalités {#key-benefits-and-features}

Décrit les principaux avantages de l’intégration de Lyris avec Adobe Marketing Reports and Analytics.

L’intégration de Lyris et d’Adobe Analytics présente les avantages clés suivants :

* Consolidation des données d’analyse et de marketing par e-mail dans une interface de création de rapports.
* Optimisation des campagnes par e-mail par le biais de conversions et de contributions au chiffre d’affaires et au succès du site.
* Re-commercialisation auprès des segments de marché et visiteurs clés en fonction des segments de marketing dynamique.

### Segments de marketing dynamique

Cette intégration des courriers électroniques prend en charge les segments de marketing dynamique pour vous aider à stimuler votre activité commerciale. Cette intégration comprend les segments marketing suivants, prêts à l’emploi :

* **Profil d’abandon de panier** : aidez les visiteurs à devenir des clients grâce à des campagnes ciblées spécialement conçues pour les visiteurs qui hésitent à valider leur panier.
* **Profils d’achat** : augmentez les commandes répétées et la valeur moyenne des commandes grâce aux campagnes ciblées par les modèles d’achat des visiteurs.
* **Profil comportemental basé sur la consultation de produits/contenu** : atteignez des clients potentiels par le biais de segments marketing basés sur les consultations de produits et la création de profils utilisateur relative à l’accès au contenu.
* Les clients peuvent également créer et planifier des **segments de remarketing personnalisés** spécifiques aux besoins de leurs utilisateurs.

## Conditions préalables à l’intégration {#integration-prerequisites}

Décrit les conditions préalables à une intégration réussie.

Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements Adobe Analytics et à votre logiciel de messagerie électronique.

Cela permettra de s’assurer que les bonnes pratiques ou que les conditions préalables appropriées sont en place avant l’activation, ce qui permettra une intégration optimale et réussie.

### Conditions préalables pour Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Spécifique à une suite de rapports** : notez que cette intégration est spécifique à une suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports de votre choix avant d’activer l’intégration.
* **Variables Analytics disponibles et configurées** : cette intégration requiert des événements personnalisés et des eVars personnalisées, ainsi qu’éventuellement des événements supplémentaires et des eVars supplémentaires.

* **Représentant autorisé** : notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, le cas échéant. En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise. À ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans le contrat de service décrit ci-dessus.
* **Adobe Analytics Data Warehouse** : cette intégration requiert l’activation de Data Warehouse d’Adobe Analytics pour générer des segments de marketing. Si vous n’avez pas activé Data Warehouse, contactez Adobe pour plus d’informations.
* **ID de destinataire** : l’intégration requiert que nous capturions et stockions un « identifiant visiteur » dans une variable Analytics (eVar). L’identifiant visiteur (souvent appelé « ID de destinataire ») est une représentation codée ou numérique d’une adresse électronique provenant du système Lyris. Cet « ID de destinataire » est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui provient du système Lyris et peut être utilisé à des fins de remarketing. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l’assistant vous y invite.
* **Suivi externe** : si vous ne suivez pas actuellement la bonne pratique consistant à activer le suivi externe pour chaque campagne par e-mail envoyée, vous devez le faire pour garantir le succès de l’intégration. Consultez la section Lyris ci-dessous pour plus de détails.
* **Respect de la confidentialité** : vous devez comprendre qu’en activant le suivi des identifiants destinataires ou visiteurs, cette fonctionnalité peut effectuer le suivi des informations d’identification personnelle des visiteurs de votre site. Cela entraîne des implications en matière de confidentialité qui nécessitent la mise en œuvre de procédures appropriées par votre organisation, comme la notification et le consentement des visiteurs de votre site.

### Conditions préalables pour Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Compte Lyris valide** : pour utiliser l’intégration des connecteurs de données, un client doit disposer d’un compte Lyris valide.
* **Informations du compte** : vous aurez besoin des informations suivantes sur votre compte Lyris lors de la configuration de l’intégration :

   * *Clé API Lyris* : utilisé pour la population de données
   * *Paramètres de chaîne de requête* : ces informations sont ajoutées à l’URL de la page d’entrée pour l’ID de message et l’ID de destinataire (identifiant visiteur).
   * *Serveur/URL Lyris* : valeur de serveur utilisée dans le système Lyris
   * *ID de site Lyris* : aussi appelé « ID de client », il s’agit de la valeur unique de votre instance de Lyris HQ. Vous pouvez le trouver sous « Informations client » dans la section « Page d’accueil du compte » de EmailLabs.

## Configuration des variables Adobe Analytics pour Lyris {#configure-adobe-analytics-variables-for-lyris}

Décrit les eVars et les événements à réserver pour chaque implémentation de suite de rapports.

Cette intégration requiert au moins 2 eVars à réserver pour chaque implémentation de suite de rapports. Outre ces eVars, certains événements peuvent être réservés selon les données Lyris que vous souhaitez voir dans Analytics. Ces eVars et événements sont décrits dans le tableau ci-dessous :

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de variable </th> 
   <th colname="col2" class="entry"> Nom de variable </th> 
   <th colname="col3" class="entry"> Utilisation de la variable </th> 
   <th colname="col4" class="entry"> Paramètres </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de message </td> 
   <td colname="col3"> Pour capturer l’identification de campagne de messagerie électronique individuelle </td> 
   <td colname="col4"> <p>État : activé </p> <p>Attribution : le plus récent </p> <p>Expire après : « Décision commerciale » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> Pour capturer l’identification anonyme du client qui a cliqué sur la campagne par e-mail </td> 
   <td colname="col4"> <p>État : activé </p> <p>Attribution : le plus récent </p> <p>Expire après : « Décision commerciale » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Courriers électroniques envoyés </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques envoyés par Lyris </td> 
   <td colname="col4">Type : numérique <p>Participation : activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Courriers électroniques ouverts </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques ouverts </td> 
   <td colname="col4">Type : numérique <p>Participation : activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Courriers électroniques uniques ouverts </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques uniques ouverts </td> 
   <td colname="col4">Type : numérique <p>Participation : activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Clics publicitaires par courriel </td> 
   <td colname="col3"> Pour stocker le nombre de fois où un message électronique a subi des clics </td> 
   <td colname="col4">Type : numérique <p>Participation : activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Rebonds de courriers électroniques </td> 
   <td colname="col3"> Pour stocker le nombre de courriers électroniques qui ont rebondi </td> 
   <td colname="col4">Type : numérique <p>Participation : activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Désabonnement au courrier électronique </td> 
   <td colname="col3"> Pour stocker le nombre d’abonnements aux courriers électroniques désactivés </td> 
   <td colname="col4">Type : numérique <p>Participation : activé </p> </td> 
  </tr> 
 </tbody> 
</table>
