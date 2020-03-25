---
description: Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements d’Adobe Analytics® et de votre logiciel de messagerie électronique.
title: Avant l’activation de cette intégration
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Avant l’activation de cette intégration {#before-you-activate-this-integration}

Avant d’activer cette intégration, comparez les éléments suivants à vos déploiements d’Adobe Analytics® et de votre logiciel de messagerie électronique.

Cela permettra de s’assurer que les bonnes pratiques ou les conditions préalables appropriées sont déjà en place avant l’activation, ce qui permettra une intégration optimale et réussie.

## Exigences d’Adobe Analytics {#adobe-analytics-requirements}

Consultez les informations suivantes sur cette intégration de connecteurs de données en ce qui concerne Adobe Analytics :

* **Spécifique à une suite de rapports :** notez que cette intégration est spécifique à une suite de rapports. Assurez-vous d’avoir sélectionné la suite de rapports souhaitée avant d’activer l’intégration et que la suite de rapports contient des données.
* **Variables Analytics disponibles et configurées :** cette intégration nécessite dix événements personnalisés et une eVar personnalisée. Voir [Variables d’intégration Analytics](appfigures-before-activation.md#analytics-integration-variables).

* **Suite de rapports initialisée avec les données en direct :** si vous créez une toute nouvelle suite de rapports pour cette intégration, elle doit avoir reçu certaines données (au moins un accès) conformément aux exigences d’appFigures en matière de suivi en direct. Si les données en direct n’ont pas été enregistrées, la suite de rapports ne sera pas en mesure de recevoir les données intégrées de la boutique d’applications.

* **Intégration existante avec la boutique d’applications :** cette intégration permet de renseigner les données pendant 13 mois. Afin d’éviter tout chevauchement avec un ancien fournisseur de données de la boutique d’applications, contactez votre représentant appFigures. Indiquez-lui la dernière date à laquelle vous avez reçu des données. appFigures ajuste la période de remplissage en conséquence.

## Exigences d’appFigures {#appfigures-requirements}

Passez en revue les informations suivantes sur l’intégration de ces connecteurs de données en rapport avec appFigures :

* **Client actuel d’appFigures :** pour cette intégration, vous devez être un utilisateur d’Adobe et d’appFigures. Si vous ne faites pas encore partie des utilisateurs du forfait Enterprise d’appFigures, alors vous ne disposez pas des informations nécessaires pour terminer l’assistant d’intégration. Pour plus d’informations, veuillez consulter le site d’appFigures sur le web.
* **Clé de compte appFigures :** une clé de compte appFigures est requise pour activer le connecteur de données appFigures. Vous pouvez générer cette clé de compte dans la section « Modules complémentaires ». Pour plus d’informations, reportez-vous à la section [Configuration de l’intégration](../appfigures-overview/t-appfigures-integration.md).

* **Finalisation des données** : les informations relatives au téléchargement, aux ventes et au classement sont synchronisées chaque jour pendant les sept derniers jours. Après sept jours, les données sont considérées comme définitives et ne sont plus mises à jour.

## Tarifs {#pricing}

Cette intégration des connecteurs de données comprend les informations relatives aux tarifs que vous devez connaître.

Les sections suivantes comprennent davantage d’informations :

### Informations sur les tarifs des prestations d’Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Cette intégration est actuellement gratuite. Cependant, il se peut que vous constatiez une légère augmentation des appels au serveur en raison de l’importation des sources de données.

### Informations sur les tarifs des prestations d’appFigures {#section-c6afad08c34b43e3a7a3637eea3328c3}

Cette intégration n’entraîne actuellement aucuns frais. Pour le moment, cette intégration n’est disponible que pour les clients Enterprise. Veuillez [contacter appFigures](https://appfigures.com/support/contact) pour plus d’informations.

## Variables d’intégration Analytics {#analytics-integration-variables}

L’intégration des connecteurs de données pour appFigures effectue le suivi de plusieurs mesures appFigures à l’aide des variables Analytics.

Le tableau suivant décrit les variables Analytics automatiquement activées pour l’intégration appFigures.

### Variables obligatoires {#section-3ca8dc46bab0436cba0c9ef827c8356a}

> [!NOTE] Cette intégration utilise des variables dédiées pour les données de la boutique d’applications. Vous n’avez donc pas besoin d’attribuer des variables et des événements de commerce personnalisés.

| Type de variable | Nom | Méthode de remplissage | Description |
|---|---|---|---|
| eVar | ID d’objet de la boutique d’applications | Importation à partir d’appFigures. | Configurez cette eVar en indiquant l’expiration de la visite, l’attribution la plus récente et les sous-relations de base. |
| Événement (numérique) | Téléchargements de la boutique d’applications | Importation à partir d’appFigures. | Nombre de téléchargements d’applications mobiles. |
| Événement (numérique) | Achats de la boutique d’applications (in-app) | Importation à partir d’appFigures. | Nombre d’achats et d’abonnements in-app. |
| Événement (numérique) | Classement de la boutique d’applications | Importation à partir d’appFigures. | Utilisée pour définir la moyenne des mesures calculées d’appFigures. Elle n’est pas utilisée directement. |
| Événement (numérique) | Diviseur de classement de la boutique d’applications | Importation à partir d’appFigures. | Utilisée pour définir la moyenne des mesures calculées d’appFigures. Elle n’est pas utilisée directement. |
| Événement (numérique) | Evaluation de la boutique d’applications | Importation à partir d’appFigures. | Utilisée pour définir la moyenne des mesures calculées d’appFigures. Elle n’est pas utilisée directement. |
| Événement (numérique) | Diviseur d’évaluations de la boutique d’applications | Importation à partir d’appFigures. | Utilisée pour définir la moyenne des mesures calculées d’appFigures. Elle n’est pas utilisée directement. |
| event (monétaire) | Recettes de la boutique d’applications (in-app) | Importation à partir d’appFigures. | Montant des recettes in-app moins les frais de la boutique. |
| event (monétaire) | Recettes ponctuelles de la boutique d’applications | Importation à partir d’appFigures. | Total des recettes provenant des achats effectués avec l’application moins les frais de la boutique. |
| event (monétaire) | Redevances de la boutique d’applications (in-app) | Importation à partir d’appFigures. | Inutilisé. |
| event (monétaire) | Redevances ponctuelles de la boutique d’applications | Importation à partir d’appFigures. | Inutilisé. |
