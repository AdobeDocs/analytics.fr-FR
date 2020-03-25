---
description: Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements d’Adobe Analytics® et de votre logiciel de messagerie électronique.
title: Avant l’activation de cette intégration
uuid: b911edc6-2265-48ed-9e3c-c79cc20dd9b2
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Avant l’activation de cette intégration {#before-you-activate-this-integration}

Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements d’Adobe Analytics® et de votre logiciel de messagerie électronique.

Cela permettra de s’assurer que les bonnes pratiques ou les conditions préalables appropriées sont déjà en place avant l’activation, ce qui permettra une intégration optimale et réussie.

## Adobe Analytics {#adobe-analytics}

Consultez les informations suivantes sur cette intégration de Data Connectors en ce qui concerne Adobe Analytics :

* **Spécifique à une suite de rapports :** notez que cette intégration est spécifique à une suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports de votre choix avant d’activer l’intégration.
* **Variables Analytics disponibles et configurées** : cette intégration requiert 5 événements personnalisés et 2 eVars personnalisées, et éventuellement 3 événements et 3 eVars supplémentaires. Voir [Variables d’intégration Analytics](/help/import/data-connectors/silverpop-overview/silverpop-variables.md).

* **Représentant autorisé :** notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, le cas échéant. En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise. À ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans le contrat de service décrit ci-dessus.
* **Data Warehouse™ :** cette intégration requiert l’activation de Data Warehouse pour générer des segments de remarketing. Si vous n’avez pas activé Data Warehouse, contactez Adobe pour plus d’informations.
* **ID de destinataire :** l’intégration requiert que nous capturions et stockions un « identifiant visiteur » dans une variable Analytics (eVar). L’identifiant visiteur (souvent appelé « ID de destinataire ») est une représentation codée ou numérique d’une adresse électronique du système Silverpop. Cet « ID de destinataire » est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui est transmis dans le système Silverpop et peut être utilisé à des fins de remarketing. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l’assistant vous y invite.
* **Suivi externe :** si vous ne respectez pas actuellement la bonne pratique consistant à activer le suivi externe pour chaque campagne par e-mail envoyée, vous devez le faire pour garantir le succès de l’intégration. Pour plus d’informations, reportez-vous à la section Silverpop ci-dessous.
* **Respect de la confidentialité :** vous devez comprendre qu’en activant le suivi des identifiants destinataires ou visiteurs, cette fonctionnalité peut effectuer le suivi des informations d’identification personnelle des visiteurs de votre site. Cela entraîne des répercussions en matière de confidentialité qui nécessitent la mise en œuvre de procédures appropriées par votre organisation, comme la notification et la demande de consentement auprès des visiteurs de votre site.

## Intégration des connecteurs de données à Silverpop {#silverpop-data-connector-integration}

Consultez les informations suivantes sur cette intégration des connecteurs de données à Silverpop :

* **Compte Silverpop valide :** afin de pouvoir utiliser l’intégration intégration de messagerie électronique des Data Connectors, un client doit disposer d’un compte Silverpop actif avec la fonction e-mail activée et d’informations d’identification d’utilisateur actives.
* **Contacter votre représentant Silverpop**. Cette intégration n’est pas activée automatiquement par Silverpop. Vous devez contacter votre représentant Silverpop pour lancer la configuration Silverpop avant que les données ne soient importées ou exportées depuis Analytics.

> [!NOTE] Cette intégration fonctionne uniquement avec les organisations Engage (pas avec les Transact).

## Tarifs {#pricing}

Cette intégration des Data Connectors comprend des aspects tarifaires que vous devez prendre en compte avant de procéder à l’activation.

### Informations sur les tarifs des prestations d’Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Cette intégration peut engendrer des frais récurrents et de mise en œuvre. Pour de plus amples informations concernant les tarifs, contactez votre gestionnaire de compte Adobe.

### Informations sur les tarifs des prestations Partner {#section-c6afad08c34b43e3a7a3637eea3328c3}

Cette intégration peut entraîner des frais. Veuillez contacter votre chargé de relations pour obtenir des informations sur les tarifs.
