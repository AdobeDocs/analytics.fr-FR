---
description: Cette intégration des courriers électroniques de Data Connectors™ d’Adobe® combine des informations comportementales d’Analytics® avec la solution marketing par courrier électronique Delivra afin de créer un outil puissant permettant de redéfinir la mesure de succès et de cibler les audiences avec des messages plus pertinents.
title: Connecteur de données Delivra pour Adobe Analytics
uuid: 9d56d39c-98e6-4e9b-b00d-515df02ea879
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Connecteur de données Delivra pour Adobe Analytics {#delivra-data-connector-for-adobe-analytics}

Cette intégration des courriers électroniques de Data Connectors™ d’Adobe® combine des informations comportementales d’Analytics® avec la solution marketing par courrier électronique Delivra afin de créer un outil puissant permettant de redéfinir la mesure de succès et de cibler les audiences avec des messages plus pertinents.

La diffusion de messages électroniques pertinents à ces segments de marché peut déboucher sur de nouvelles opportunités de chiffre d’affaires, ce qui entraîne une augmentation des conversions et du chiffre d’affaires parmi les campagnes par e-mail existantes et nouvelles. Par exemple, il a été démontré que la diffusion de messages électroniques pertinents basés sur les produits consultés au cours d’une visite ou laissés dans un panier d’achats abandonné a un impact considérable sur le chiffre d’affaires et un impact minimal sur les coûts, puisque ce procédé tire parti des visiteurs déjà présents sur votre site. Cette augmentation de l’efficacité marketing est l’un des avantages clés de l’intégration d’Analytics à Delivra. En outre, cette intégration synchronise automatiquement les mesures de courrier électronique avec les données Analytics de manière fréquente, chaque heure, pour la création de rapports en boucle fermée.

## Avantages clés {#key-benefits}

Cette intégration présente les principaux avantages suivants :

* Consolidation des données d’analyse et de marketing par e-mail dans une interface de création de rapports.
* Optimisation des campagnes par e-mail par le biais de conversions et de contributions au chiffre d’affaires et au succès du site.
* Re-commercialisation auprès des segments de marché et visiteurs clés en fonction des segments de marketing dynamique.
* Synchronisation des mesures de courrier électronique quasi en temps réel disponible, par rapport à une synchronisation standard par jour

## Segments de marketing dynamique {#dynamic-marketing-segments}

Cette intégration des courriers électroniques des Data Connectors prend en charge les segments de marketing dynamique pour vous aider à stimuler votre activité commerciale.

Cette intégration comprend les segments marketing suivants, prêts à l’emploi :

* **Profils d’achat :** augmentez les commandes répétées et la valeur moyenne des commandes grâce à des campagnes ciblées en fonction des habitudes d’achat des visiteurs.
* **Profil comportemental basé sur la consultation de produits/contenu :** atteignez des clients potentiels par le biais de segments marketing basés sur les consultations de produits et la création de profils utilisateur relative à l’accès au contenu.
* **Profil d’abandon de panier :** aidez les visiteurs à devenir des clients grâce à des campagnes ciblées spécialement conçues pour les visiteurs qui hésitent à valider leur panier.
* Les clients peuvent également créer et planifier des segments de remarketing personnalisés spécifiques aux besoins de leurs utilisateurs.

## Procédure d’intégration et conditions préalables {#integration-procedure-and-prerequisites}

À l’aide d’un assistant « plug and play », des processus intuitifs vous guideront pas à pas à travers les points de synchronisation du système et débuteront l’intégration.

Cette intégration des Data Connectors requiert les éléments suivants :

### Conditions préalables pour Adobe {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Adobe Data Warehouse
* Compte Adobe Analytics.
* Variables Analytics disponibles et configurées, y compris les eVars et les événements personnalisés.

### Conditions préalables de Delivra {#section-bcb904574ccf42308bcf7a15e45b4d58}

* Compte Delivra actif de niveau professionnel (ou supérieur) avec l’option « Intégration Adobe » activée.

## Tarifs {#pricing}

Cette intégration des Data Connectors comprend les informations relatives aux tarifs que vous devez connaître.

Les sections suivantes comprennent davantage d’informations :

### Informations sur les tarifs des prestations d’Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Cette intégration peut engendrer des frais récurrents et de mise en œuvre. Pour de plus amples informations concernant les tarifs, contactez votre gestionnaire de compte Adobe.

### Tarifs des prestations Delivra {#section-c6afad08c34b43e3a7a3637eea3328c3}

Cette intégration peut entraîner des frais.

* Contactez votre représentant du compte Delivra pour plus d’informations sur les tarifs.

## Informations à connaître avant d’activer cette intégration {#what-you-should-know-before-activating-this-integration}

Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements d’Adobe Analytics® et de votre logiciel de messagerie électronique.

Cela permettra de s’assurer que les bonnes pratiques ou les conditions préalables appropriées sont déjà en place avant l’activation, ce qui permettra une intégration optimale et réussie.

### Adobe Analytics {#adobe-analytics}

Consultez les informations suivantes sur cette intégration de Data Connectors en ce qui concerne Adobe Analytics :

* **Spécifique à une suite de rapports :** notez que cette intégration est spécifique à une suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports de votre choix avant d’activer l’intégration.
* **Représentant autorisé :** notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, le cas échéant. En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise. À ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans le contrat de service décrit ci-dessus.
* **Data Warehouse™ :** cette intégration requiert l’activation de Data Warehouse pour générer des segments de remarketing. Si vous n’avez pas activé Data Warehouse, contactez Adobe pour plus d’informations.
* **ID de destinataire :** l’intégration requiert que nous capturions et stockions un « identifiant visiteur » dans une variable Analytics (eVar). L’identifiant visiteur (souvent appelé « ID de destinataire ») est une représentation codée ou numérique d’une adresse électronique provenant du système Delivra. Cet « ID de destinataire » est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui provient du système Delivra et peut être utilisé à des fins de remarketing. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l’assistant vous y invite.
* **Suivi externe :** si vous ne respectez pas actuellement la bonne pratique consistant à activer le suivi externe pour chaque campagne par e-mail envoyée, vous devez le faire pour garantir le succès de l’intégration. Consultez la section Delivra ci-dessous pour plus d’informations.
* **Respect de la confidentialité :** vous devez comprendre qu’en activant le suivi des identifiants destinataires ou visiteurs, cette fonctionnalité peut effectuer le suivi des informations d’identification personnelle des visiteurs de votre site. Cela entraîne des répercussions en matière de confidentialité qui nécessitent la mise en œuvre de procédures appropriées par votre organisation, comme la notification et la demande de consentement auprès des visiteurs de votre site.

### Intégration de Delivra pour les Data Connectors Adobe {#delivra-for-adobe-data-connectors-integration}

Consultez les informations suivantes sur cette intégration des Data Connectors en ce qui concerne Delivra :

* **Compte Delivra valide :** pour utiliser l’intégration des courriers électroniques des Data Connectors, un client doit disposer d’un compte Delivra valide.
* **Client actuel de Delivra :** cette intégration requiert que vous soyez client d’Adobe et de Delivra. Si vous n’êtes actuellement pas client de Delivra, vous ne disposerez pas des informations nécessaires pour terminer l’assistant d’intégration. Si vous êtes actuellement client de Delivra, vous aurez besoin de votre ID de compte Delivra, ou du nom de liste, affecté à votre organisation, pour terminer l’assistant d’intégration. Vous devrez fournir à Delivra le nom de la société et l’ID de compte associés à l’intégration, afin de terminer votre configuration.
