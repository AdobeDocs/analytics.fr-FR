---
description: Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements d’Adobe Analytics® et de votre logiciel de messagerie électronique.
seo-description: Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements d’Adobe Analytics® et de votre logiciel de messagerie électronique.
seo-title: Avant D’Activer Cette Intégration
title: Avant D’Activer Cette Intégration
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Avant D’Activer Cette Intégration {#before-you-activate-this-integration}

Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements d’Adobe Analytics® et de votre logiciel de messagerie électronique.

Cela permettra de s’assurer que les meilleures pratiques ou les conditions préalables appropriées sont en place avant l’activation, ce qui permettra une intégration optimale et réussie.

## Adobe Analytics Requirements{#adobe-analytics-requirements}

Consultez les informations suivantes sur l’intégration de ces connecteurs de données en ce qui concerne Adobe Analytics :

* **** Spécifique à une Report Suite :Notez que cette intégration est spécifique à une suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports souhaitée avant d’activer l’intégration et que la suite de rapports contient des données.
* **** Variables Analytics disponibles et configurées : Cette intégration requiert 10 événements personnalisés et 1 eVar personnalisée. Voir Variables [d’intégration](appfigures-before-activation.md#analytics-integration-variables)Analytics.

* **** Suite de rapports initialisée avec les données en direct : Si vous créez une toute nouvelle suite de rapports pour cette intégration, elle doit avoir reçu certaines données (au moins un accès) via les exigences d’appFigures de suivi en direct. Si les données en direct n’ont pas été enregistrées, la suite de rapports ne sera pas prête à recevoir les données de l’App Store intégrées.

* **** Intégration existante à l’App Store : Cette intégration remplit les données pendant 13 mois. Afin d’éviter tout chevauchement avec un fournisseur de données App Store précédent, contactez votre représentant appFigures. Indiquez-leur la dernière date de réception des données. appFigures ajuste la période de remplissage en conséquence.

## appFigures Requirements{#appfigures-requirements}

Consultez les informations suivantes sur l’intégration des connecteurs de données en ce qui concerne appFigures :

* **** Client actuel d’appFigures : Cette intégration requiert que vous soyez un utilisateur d’Adobe et d’appFigures. Si vous n’êtes pas actuellement utilisateur du plan d’entreprise appFigures, vous ne disposez pas des informations nécessaires pour terminer l’assistant d’intégration. Pour plus d’informations, rendez-vous sur appFigures sur le Web.
* **** Clé de compte appFigures : Une clé de compte appFigures est requise pour activer le connecteur de données appFigures. Cette clé de compte peut être générée dans la section "Modules complémentaires". Pour plus d’informations, voir [Configuration de l’intégration](../appfigures-overview/t-appfigures-integration.md) .

* **Finalisation** des données : Les informations de téléchargement, de vente et de classement sont synchronisées chaque jour pendant les 7 derniers jours. Après 7 jours, les données sont considérées comme définitives et ne sont plus mises à jour.

## Tarifs{#pricing}

Cette intégration des connecteurs de données inclut des considérations de tarification que vous devez connaître.

Les sections suivantes comprennent davantage d’informations :

### Points à prendre en compte concernant les tarifs Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Il n’y a actuellement aucun frais pour activer cette intégration. Cependant, vous pouvez constater une légère augmentation des appels serveur en raison de l’importation des sources de données.

### Points à prendre en compte concernant les prix d’appFigures {#section-c6afad08c34b43e3a7a3637eea3328c3}

Cette intégration n’entraîne actuellement aucun frais. Actuellement, cette intégration est uniquement disponible pour les clients d’entreprise. Veuillez [contacter appFigures](https://appfigures.com/support/contact) pour plus d’informations.

## Analytics Integration Variables{#analytics-integration-variables}

L’intégration des connecteurs de données pour appFigures utilise des variables Analytics pour effectuer le suivi de diverses mesures appFigures.

Le tableau suivant décrit les variables Analytics automatiquement activées pour l’intégration appFigures.

### Variables requises {#section-3ca8dc46bab0436cba0c9ef827c8356a}

> [!NOTE] Cette intégration utilise des variables dédiées pour les données de la boutique d’applications. Vous n’avez donc pas besoin d’affecter des variables et des événements de commerce personnalisés.

| Type de variable | Nom | Méthode de remplissage | Description |
|---|---|---|---|
| eVar | ID d’objet de la boutique d’applications | Importé à partir d’appFigures. | Configurez cette eVar avec l’expiration de la visite, l’attribution la plus récente et les sous-relations de base. |
| event (numeric) | Téléchargements de la boutique d’applications | Importé à partir d’appFigures. | Nombre de téléchargements d’applications mobiles. |
| event (numeric) | Achats de la boutique d’applications (dans l’application) | Importé à partir d’appFigures. | Nombre d’achats et d’abonnements in-app. |
| event (numeric) | Classement de la boutique d’applications | Importé à partir d’appFigures. | Utilisé pour définir la mesure calculée "Moyenne des appFigures". Non utilisé directement. |
| event (numeric) | Diviseur de classement de la boutique d’applications | Importé à partir d’appFigures. | Utilisé pour définir la mesure calculée "Moyenne des appFigures". Non utilisé directement. |
| event (numeric) | Evaluation de la boutique d’applications | Importé à partir d’appFigures. | Utilisé pour définir la mesure calculée "Moyenne des appFigures". Non utilisé directement. |
| event (numeric) | Diviseur d’évaluations de la boutique d’applications | Importé à partir d’appFigures. | Utilisé pour définir la mesure calculée "Moyenne des appFigures". Non utilisé directement. |
| event (devise) | Recettes de la boutique d’applications (dans l’application) | Importé à partir d’appFigures. | Montant des recettes in-app moins les frais de stockage. |
| event (devise) | Recettes de la boutique d’applications (une seule option) | Importé à partir d’appFigures. | Recettes totales provenant des achats d’applications moins les frais de stockage. |
| event (devise) | Redevances de la boutique d’applications (dans l’application) | Importé à partir d’appFigures. | Inutilisée |
| event (devise) | Redevances de la boutique d’applications (une seule fois) | Importé à partir d’appFigures. | Inutilisée |
