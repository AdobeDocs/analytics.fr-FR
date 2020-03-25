---
description: Cette intégration associe la puissance du système de retour intégré du logiciel de marketing par courrier électronique et le reporting comportemental d’Adobe Analytics afin de créer de puissantes opportunités d’analyse et d’optimisation pour votre entreprise.
title: Connecteur de données optivo® broadmail pour Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Connecteur de données optivo® broadmail pour Adobe Analytics {#optivo-broadmail-data-connector-for-adobe-analytics}

Cette intégration associe la puissance du système de retour intégré du logiciel de marketing par courrier électronique et le reporting comportemental d’Adobe Analytics afin de créer de puissantes opportunités d’analyse et d’optimisation pour votre entreprise.

[!DNL ~Partner~] est un logiciel professionnel de marketing par courrier électronique. Sa fonction principale est de créer, d’envoyer et d’évaluer des campagnes par newsletter et par e-mail. `[~Partner~]` est disponible en tant que service cloud (logiciel en tant que service).

L’intégration `[~Partner~]` offre le remarketing automatisé et la synchronisation des données, ce qui entraîne une augmentation des conversions et des recettes. L’intégration permet aux spécialistes du marketing de synchroniser automatiquement les segments pour leurs clients, en fonction de leur interaction par e-mail et de leur comportement sur le site. L’échange automatisé de données de segments personnalisables vous permet de créer des campagnes par e-mail très ciblées pour stimuler les ventes, lors de l’abandon du panier d’achats ou pour le remarketing après achat pour les produits de ventes croisées et de ventes consécutives.

Cette intégration échange également les mesures des campagnes par e-mail réussies de `[~Partner~]` vers Adobe Analytics. Les données essentielles sont affichées de manière centralisée dans l’aperçu de votre campagne par e-mail.

## Programme de laboratoire des Data Connectors {#section-51f9864851b64d96873127b9ac9c9a2b}

Ce programme est une méthode rapide permettant aux partenaires tiers d’Adobe de créer des intégrations et de les diffuser sur notre marché commun. Les intégrations sont entièrement développées par nos partenaires et mises à disposition sur Adobe Experience Cloud selon les procédés de la communauté. Elles sont mises à la disposition des clients Adobe d’Adobe Analytics et d’autres solutions sans frais supplémentaires et sont fournies en l’état, sans aucune garantie implicite de la part d’Adobe en raison de la nature tierce des intégrations.

Si vous avez des questions concernant votre service actuel, votre garantie ou votre licence, contactez votre gestionnaire de compte Adobe.

## Principaux avantages et fonctionnalités {#key-benefits-and-features}

Cette intégration présente les principaux avantages suivants :

* Récupération des acheteurs qui parcourent le site et abandonnent
* Augmentation des ventes grâce à un marketing de relance ciblé de ventes croisées et de ventes consécutives
* Campagnes automatiques basées sur les segments
* Campagnes optimisées en cours
* Segments pour le remarketing ciblé dans [!DNL ~Partner~]
* Mises à jour constantes des mesures de campagne
* Déclencheurs de conversations automatiques

## Segments de marketing dynamique {#dynamic-marketing-segments}

Cette intégration comprend les segments de marketing dynamique suivants :

* **Profils d’achat :** augmentez les commandes répétées et la valeur moyenne des commandes grâce à des campagnes ciblées en fonction des habitudes d’achat des visiteurs.
* **Profil comportemental basé sur la consultation de produits/contenu :** atteignez des clients potentiels par le biais de segments marketing basés sur les consultations de produits et la création de profils utilisateur relative à l’accès au contenu.
* **Profil d’abandon de panier :** aidez les visiteurs à devenir des clients grâce à des campagnes ciblées spécialement conçues pour les visiteurs qui hésitent à valider leur panier.
* **Remarketing efficace :** les clients peuvent également créer et planifier des segments de remarketing personnalisés spécifiques aux besoins de leurs utilisateurs.

## Avant l’activation {#before-you-activate}

Avant de démarrer l’intégration des Data Connectors pour , remplissez les exigences suivantes :

## Exigences d’Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Spécifique à une suite de rapports :** notez que cette intégration est spécifique à une suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports de votre choix avant d’activer l’intégration.
* **Variables Adobe Analytics disponibles et configurées :** cette intégration requiert des événements personnalisés et des eVars personnalisées.

* **Représentant autorisé :** notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, le cas échéant. En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise. À ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans le contrat de service décrit ci-dessus.
* **ID de message :** l’intégration requiert que nous capturions et stockions un « ID de message » dans une variable Adobe Analytics (eVar). Ces identifiants sont nécessaires pour identifier les messages que vous avez envoyés. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l’assistant vous y invite.
* **Partner :** l’intégration requiert que nous capturions et stockions un [!UICONTROL ~Partner~] dans une variable Adobe Analytics (eVar). Cet ID est une représentation codée ou numérique d’une adresse électronique du système [!UICONTROL ~Partner~]. Ce [!UICONTROL ~Partner~] est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui est transmis au système [!UICONTROL ~Partner~] et peut être utilisé à des fins de remarketing. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l’assistant vous y invite.
* **Heure post click** : dans le cadre du processus de configuration, cette intégration requiert une affectation à une eVar correspondant à l’heure d’une action post click. Cela est nécessaire pour transmettre des informations sur une action de destinataire à [!UICONTROL ~Partner~] une fois que le destinataire a cliqué sur un lien dans un mail.

* **Produit post click :** dans le cadre du processus de configuration, cette intégration requiert une affectation à une eVar qui correspond au produit proposé associé à une action post-click. Cela est nécessaire pour transmettre des informations sur une action de destinataire à [!UICONTROL ~Partner~] une fois que le destinataire a cliqué sur un lien dans un mail.

* **Type d’actions post click** : dans le cadre du processus de configuration, cette intégration requiert une affectation à une eVar correspondant à l’heure d’une action post click. Cela est nécessaire pour transmettre des informations sur une action de destinataire à [!UICONTROL ~Partner~] une fois que le destinataire a cliqué sur un lien dans un mail.

* **Respect de la confidentialité :** vous devez comprendre qu’en activant le suivi des identifiants destinataires ou visiteurs, cette fonctionnalité peut effectuer le suivi des informations d’identification personnelle des visiteurs de votre site. Cela entraîne des répercussions en matière de confidentialité qui nécessitent la mise en œuvre de procédures appropriées par votre organisation, comme la notification et la demande de consentement auprès des visiteurs de votre site.

## Tarifs {#pricing}

Notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, selon le cas.

En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise. À ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans le contrat de service décrit ci-dessus.

### Informations sur les tarifs des prestations d’Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Les clients actuels de la solution Adobe Analytics n’ont aucun coût supplémentaire associé à l’utilisation de cette intégration des Data Connectors. Les clients qui n’utilisent pas encore le nouveau produit Adobe Analytics doivent contacter leur gestionnaire de compte Adobe pour plus d’informations.

### Informations sur les tarifs des prestations Partner {#section-f8ca71df32224412a5101efb6e356529}

Cette intégration est disponible pour les clients [!DNL ~Partner~], mais des frais d’intégration supplémentaires s’appliqueront. Veuillez contacter sales@optivo.com pour plus d’informations sur les tarifs. Veuillez contacter [!DNL ~Partner~] pour plus d’informations sur les tarifs.

## Variables Adobe Analytics {#adobe-analytics-variables}

Cette intégration nécessite que les variables Adobe Analytics effectuent le suivi des mesures.

Après avoir identifié l’événement et les eVars à utiliser avec cette intégration, ils doivent être activés dans Analytics Admin Console (voir [Suites de rapports](https://docs.adobe.com/content/help/fr-FR/analytics/admin/manage-report-suites/report-suites-admin.html) pour obtenir des instructions).
