---
description: Décrit les gains d’efficacité marketing réalisés grâce à l’intégration.
title: Connecteur de données Lyris pour Adobe Analytics
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Lyris Data Connector for Adobe Analytics{#lyris-data-connector-for-adobe-analytics}

Décrit les gains d’efficacité marketing réalisés grâce à l’intégration.

L’intégration des courriers électroniques Adobe® Data Connectors™ combine les informations comportementales d’Adobe Analytics avec le marketing par courrier électronique Lyris pour redéfinir la mesure de succès et cibler les audiences avec des messages plus pertinents.

La remise de messages électroniques pertinents à ces segments de marché peut générer de nouvelles opportunités de recettes, ce qui entraîne une augmentation des conversions et des recettes au sein des campagnes de messagerie nouvelles et existantes. Par exemple, la diffusion de messages électroniques pertinents basés sur des produits qui ont été consultés au cours d’une visite ou des produits qui ont été laissés dans un panier d’achat abandonné a démontré un impact considérable sur les recettes, avec un impact minimal sur les coûts, car cela ne fait qu’augmenter les visiteurs de votre site.

Cette augmentation de l’efficacité marketing est l’un des principaux avantages de l’intégration d’Adobe Analytics à Lyris. En outre, cette intégration synchronise automatiquement les mesures de courrier électronique avec les données Adobe Analytics aussi fréquemment que par heure pour la création de rapports en boucle fermée.

## Principaux avantages et fonctionnalités{#key-benefits-and-features}

Décrit les principaux avantages de l’intégration des rapports et analyses Lyris et Adobe Marketing.

L’intégration de Lyris et d’Adobe Analytics présente les principaux avantages suivants :

* Consolidation des données de marketing et d’analyse par courrier électronique dans une interface de création de rapports
* Optimiser les campagnes par courrier électronique par conversion et contribution aux recettes et au succès du site
* Commercialiser à nouveau les visiteurs clés et les segments de marché en fonction des segments marketing dynamiques

### Segments de marketing dynamique

L’intégration du courrier électronique prend en charge les segments de marketing dynamique pour vous aider à diriger votre entreprise. Cette intégration comprend les segments marketing suivants, prêts à l’emploi :

* **Profil** d'abandon du panier : Aidez les visiteurs à se convertir en clients grâce à des campagnes affinées spécialement conçues pour ceux qui hésitent à compléter leur panier
* **Profils** d’achat : Augmenter les commandes répétées et la valeur moyenne des commandes par le biais de campagnes ciblées sur les modèles d'achat des visiteurs
* **Profil** comportemental de la vue de produit/contenu : Atteindre les clients potentiels par le biais de segments marketing basés sur les consultations de produits et le profilage de l’accès au contenu
* Les clients peuvent également créer et planifier des segments **de remarketing** personnalisés spécifiques aux besoins de leurs utilisateurs.

## Conditions préalables à l’intégration{#integration-prerequisites}

Décrit les conditions préalables à une intégration réussie.

Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements d’Adobe Analytics et de votre logiciel de messagerie électronique.

Cela permet de s’assurer que les bonnes pratiques et les conditions préalables appropriées sont en place avant l’activation, ce qui se traduit par une intégration optimale et réussie.

### Conditions préalables requises pour Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Spécifique**&#x200B;à une Report Suite :Notez que cette intégration est spécifique à une suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports de votre choix avant d’activer l’intégration.
* **Variables** Analytics disponibles et configurées :Cette intégration requiert des événements personnalisés et des eVars personnalisées, ainsi que éventuellement des événements supplémentaires et des eVars supplémentaires.

* **Représentant** autorisé :Notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, selon le cas. En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise ; et, à ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans l'accord de service décrit ci-dessus.
* **Entrepôt** de données Adobe Analytics : Cette intégration requiert l’activation de l’entrepôt de données Adobe Analytics pour générer des segments de remarketing. Si vous n’avez pas activé l’entrepôt de données, contactez Adobe pour plus d’informations.
* **ID** du destinataire : L’intégration requiert que nous capturions et stockions un "identifiant visiteur" dans une variable Analytics (eVar). L’identifiant visiteur (souvent appelé "ID du destinataire") est une représentation codée ou numérique d’une adresse électronique du système Lyris. Cet "ID de destinataire" est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui est récupéré dans le système Lyris et peut être utilisé à des fins de re-marketing. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l'Assistant vous y invite.
* **Suivi** externe : Si vous ne suivez pas actuellement la bonne pratique consistant à activer le suivi externe pour chaque campagne par courrier électronique envoyée, vous devez le faire pour garantir une intégration réussie. Voir la section Lyris ci-dessous pour plus de détails
* **Respect** de la vie privée :Vous devez comprendre qu’en activant le suivi des destinataires ou des identifiants des visiteurs, cette fonctionnalité peut effectuer le suivi des informations d’identification personnelle des visiteurs de votre site. Cela a des implications en matière de confidentialité, ce qui nécessite la mise en oeuvre de procédures appropriées par votre organisation, comme la notification et le consentement des visiteurs de votre site.

### Conditions préalables requises pour Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Compte** Lyris valide : Pour utiliser cette intégration de Connector de données, vous devez disposer d’un compte Lyris valide.
* **Informations** du compte : Vous aurez besoin des informations suivantes sur votre compte Lyris lors de cette configuration de l’intégration :

   * *Clé* API Lyris : Utilisé pour la population de données
   * *Paramètres* de chaîne de requête : Ces informations sont ajoutées à l’URL de la page d’entrée pour l’ID de message et l’ID de destinataire (identifiant visiteur).
   * *Serveur/URL* Lyris : Valeur de serveur utilisée dans le système Lyris
   * *Identifiant* du site Lyris : Aussi appelé "ID client", il s’agit de la valeur unique de votre instance de Lyris HQ. Vous pouvez le trouver sous "Informations client" dans la section "Page d’accueil du compte" de EmailLabs.

## Configuration des variables Adobe Analytics pour Lyris{#configure-adobe-analytics-variables-for-lyris}

Décrit les eVars et les événements à réserver pour chaque implémentation de suite de rapports.

Cette intégration requiert au moins 2 eVars à réserver pour chaque implémentation de suite de rapports. Outre ces eVars, certains événements peuvent être réservés selon les données Lyris que vous souhaitez voir dans Analytics. Ces eVars et événements sont décrits dans le tableau ci-dessous :

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
   <td colname="col2"> ID du message </td> 
   <td colname="col3"> Pour capturer l’identification de campagne de messagerie électronique individuelle </td> 
   <td colname="col4"> <p>État : Activé </p> <p>Affectation : Le plus récent </p> <p>Expire après : "Décision commerciale" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> Pour capturer l’identification anonyme du client qui a cliqué sur la campagne par courrier électronique </td> 
   <td colname="col4"> <p>État : Activé </p> <p>Affectation : Le plus récent </p> <p>Expire après : "Décision commerciale" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Courriers électroniques envoyés </td> 
   <td colname="col3"> Pour stocker non. des courriels envoyés par Lyris </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Courriers électroniques ouverts </td> 
   <td colname="col3"> Pour stocker non. des courriers électroniques ouverts </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Courriers électroniques uniques ouverts </td> 
   <td colname="col3"> Pour stocker non. des courriers électroniques uniques ouverts </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Clics publicitaires par courriel </td> 
   <td colname="col3"> Pour stocker non. de fois où un message électronique a été cliqué </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Retours par courriel </td> 
   <td colname="col3"> Pour stocker le no. des courriers électroniques rebondissés </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement </td> 
   <td colname="col2"> Lyris - Abonnement au courrier électronique </td> 
   <td colname="col3"> Pour stocker le no. des abonnements aux courriers électroniques désactivés </td> 
   <td colname="col4">Type : Numérique <p>Participation : Activé </p> </td> 
  </tr> 
 </tbody> 
</table>
