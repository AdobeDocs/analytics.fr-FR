---
description: Cette intégration associe la puissance du système intégré de commentaires du logiciel de marketing par courrier électronique et la création de rapports comportementaux d’Adobe Analytics afin de créer de puissantes opportunités d’analyse et d’optimisation pour votre entreprise.
seo-description: Cette intégration associe la puissance du système intégré de commentaires du logiciel de marketing par courrier électronique et la création de rapports comportementaux d’Adobe Analytics afin de créer de puissantes opportunités d’analyse et d’optimisation pour votre entreprise.
seo-title: optivo® Broadmail Data Connector for Adobe Analytics
title: optivo® Broadmail Data Connector for Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# optivo® Broadmail Data Connector for Adobe Analytics{#optivo-broadmail-data-connector-for-adobe-analytics}

Cette intégration associe la puissance du système intégré de commentaires du logiciel de marketing par courrier électronique et la création de rapports comportementaux d’Adobe Analytics afin de créer de puissantes opportunités d’analyse et d’optimisation pour votre entreprise.

[!DNL ~Partner~] est un logiciel professionnel de marketing par courrier électronique. Sa fonction principale est de créer, d'envoyer et d'évaluer des campagnes par newsletter et par email. `[~Partner~]` est disponible en tant que service cloud (logiciel en tant que service).

L’ `[~Partner~]` intégration offre le remarketing automatisé et la synchronisation des données, ce qui entraîne une augmentation des conversions et des recettes. L’intégration permet aux spécialistes du marketing de synchroniser automatiquement les segments pour leurs clients, en fonction de leur interaction par courrier électronique et de leur comportement sur le site. L’échange automatisé de données de segments personnalisables vous permet de créer des campagnes par courrier électronique très ciblées pour stimuler les ventes, telles que l’abandon du panier d’achat et le remarketing après achat pour les produits de vente croisée, consécutive à un achat ou à une vente.

Cette intégration échange également les mesures des campagnes par courrier électronique réussies depuis `[~Partner~]` Adobe Analytics. Les données essentielles sont affichées de manière centralisée dans l’aperçu de votre campagne par courrier électronique.

## Programme de laboratoire des connecteurs de données {#section-51f9864851b64d96873127b9ac9c9a2b}

Ce programme est une méthode rapide permettant aux partenaires tiers d’Adobe de créer des intégrations et de les diffuser sur notre marché commun. Les intégrations sont entièrement développées par nos partenaires et mises à disposition sur Adobe Experience Cloud selon les méthodologies de la communauté. Elles sont mises à la disposition des clients Adobe d’Adobe Analytics et d’autres solutions sans frais supplémentaires et sont fournies en l’état, sans aucune garantie implicite de la part d’Adobe en raison de la nature tierce des intégrations.

Si vous avez des questions concernant votre service actuel, votre garantie ou votre licence, contactez votre gestionnaire de compte Adobe.

## Principaux avantages et fonctionnalités{#key-benefits-and-features}

Cette intégration présente les principaux avantages suivants :

* Récupérez les acheteurs qui parcourent et abandonnent
* Augmenter les ventes grâce à un marketing de relance ciblé de ventes croisées et de ventes consécutives
* Campagnes automatiques par segment
* Campagnes optimisées en cours
* Segments du [!DNL ~partenaire~] pour le remarketing ciblé
* Mises à jour constantes des mesures de campagne
* Déclencheurs de conversation automatisés

## Segments de marketing dynamique{#dynamic-marketing-segments}

Cette intégration comprend les segments de marketing dynamique suivants :

* **** Profils d’achat : Augmentez les commandes répétées et la valeur moyenne des commandes grâce aux campagnes ciblées par les modèles d’achat des visiteurs.
* **** Profil comportemental de la vue de produit/contenu : Contactez les clients potentiels par le biais de segments marketing basés sur les consultations de produits et le profilage de l’accès au contenu.
* **** Profil d'abandon du panier : Aidez les visiteurs à se convertir en clients grâce à des campagnes affinées spécialement conçues pour ceux qui hésitent à compléter leur panier.
* **** Remarketing effectif :Les clients peuvent également créer et programmer des segments de remarketing personnalisés spécifiques aux besoins de leurs utilisateurs.

## Avant d’activer{#before-you-activate}

Avant de démarrer l’intégration des Connecteurs de données pour , remplissez les conditions suivantes :

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **** Spécifique à la suite de rapports : Notez que cette intégration est spécifique à une suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports de votre choix avant d’activer l’intégration.
* **** Variables Adobe Analytics disponibles et configurées : Cette intégration requiert des événements personnalisés et des eVars personnalisées.

* **** Représentant autorisé : Notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, selon le cas. En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise ; et, à ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans l'accord de service décrit ci-dessus.
* **** ID du message : L’intégration requiert que nous capturions et stockions un "ID de message" dans une variable Adobe Analytics (eVar). Ces identifiants sont nécessaires pour identifier les messages que vous avez envoyés. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l'Assistant vous y invite.
* **** Partenaire : L’intégration requiert que nous capturions et stockions un [!UICONTROL ~partenaire~] dans une variable Adobe Analytics (eVar). Cet identifiant est une représentation codée ou numérique d'une adresse électronique du système [!UICONTROL ~partenaire~] . Ce [!UICONTROL ~partenaire~] est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui est extrait dans le système [!UICONTROL ~Partner~] et peut être utilisé à des fins de remarketing. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l'Assistant vous y invite.
* **** Heure du clic sur la publication : Dans le cadre du processus de configuration, cette intégration requiert une affectation à une eVar correspondant à l’heure d’une action post-clic. Cela est nécessaire pour transmettre des informations sur une action de destinataire au [!UICONTROL ~partenaire~] après que le destinataire a cliqué sur un lien dans un courrier.

* **** Produit après clic : Dans le cadre du processus de configuration, cette intégration requiert une affectation à une eVar qui correspond au produit proposé associé à une action post-clic. Cela est nécessaire pour transmettre des informations sur une action de destinataire au [!UICONTROL ~partenaire~] après que le destinataire a cliqué sur un lien dans un courrier.

* **** Type d’action après clic : Dans le cadre du processus de configuration, cette intégration requiert une affectation à une eVar correspondant au type d’action post-clic. Cela est nécessaire pour transmettre des informations sur une action de destinataire au [!UICONTROL ~partenaire~] après que le destinataire a cliqué sur un lien dans un courrier.

* **** Respect de la vie privée : Vous devez comprendre qu’en activant le suivi des destinataires ou des identifiants des visiteurs, cette fonctionnalité peut effectuer le suivi des informations d’identification personnelle des visiteurs de votre site. Cela a des implications en matière de confidentialité qui nécessitent la mise en oeuvre de procédures appropriées par votre organisation, comme la notification et le consentement des visiteurs de votre site.

## Tarifs{#pricing}

 Notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, selon le cas.

En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise ; et, à ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans l'accord de service décrit ci-dessus.

### Points à prendre en compte concernant les tarifs Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Les clients actuels de la solution Adobe Analytics n’ont aucun coût supplémentaire associé à l’utilisation de cette intégration des connecteurs de données. Les clients qui n’ont pas encore accédé au nouveau produit Adobe Analytics doivent contacter leur gestionnaire de compte Adobe pour plus de détails.

### Points à prendre en compte concernant les prix des partenaires {#section-f8ca71df32224412a5101efb6e356529}

Cette intégration est disponible pour les clients [!DNL ~partenaires~] , mais des frais d'intégration supplémentaires s'appliqueront. Veuillez contacter sales@optivo.com pour plus de détails sur les tarifs. Veuillez contacter [!DNL ~le partenaire~] pour obtenir des informations sur les tarifs.

## Variables Adobe Analytics{#adobe-analytics-variables}

Cette intégration nécessite que les variables Adobe Analytics effectuent le suivi des mesures.

Après avoir identifié l’événement et les eVars à utiliser avec cette intégration, ils doivent être activés dans la console d’administration Analytics (voir Suites [de](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) rapports pour obtenir des instructions).