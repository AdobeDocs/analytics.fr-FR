---
description: L’intégration des Data Connectors pour Silverpop effectue le suivi de plusieurs mesures Silverpop à l’aide des variables Analytics.
title: Variables d’intégration Analytics
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variables d’intégration Analytics {#analytics-integration-variables}

L’intégration des Data Connectors pour Silverpop effectue le suivi de plusieurs mesures Silverpop à l’aide des variables Analytics.

Après avoir identifié l’événement et les eVars à utiliser avec l’intégration Silverpop, activez-les depuis l’Admin Console d’Adobe Analytics (voir [Suites de rapports](https://docs.adobe.com/content/help/fr-FR/analytics/admin/manage-report-suites/report-suites-admin.html)).

Le tableau suivant décrit les variables Analytics nécessaires pour l’intégration Silverpop.

## Variables obligatoires {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Type de variable | Nom | Méthode de remplissage | Description |
|---|---|---|---|
| Événement (numérique) | Retours | Importé automatiquement depuis Silverpop. | L’événement Rebonds vous permet d’afficher le nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de livraison. |
| Événement (numérique) | Clics | Importé automatiquement depuis Silverpop. | L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. |
| Événement (numérique) | Ouvertures | Importé automatiquement depuis Silverpop. | L’événement Ouvert vous permet d’afficher le nombre de visiteurs qui ont ouvert le message électronique. |
| Événement (numérique) | Envois | Importé automatiquement depuis Silverpop. | L’événement Envoyé vous permet d’afficher le nombre de messages électroniques envoyés. |
| Événement (numérique) | Désabonnements | Importé automatiquement depuis Silverpop. | L’événement Désabonné vous permet d’afficher le nombre de visiteurs qui ont ouvert le message électronique, mais qui ont cliqué sur le lien Se désabonner pour ne plus recevoir à l’avenir de messages électroniques de votre organisation. |
| eVar | ID Silverpop/Identifiant visiteur | Collecté à partir des paramètres de requête dans les liens de courrier électronique par le biais de la méthode de collecte automatisée ou d’un plug-in JavaScript. | Identifiant visiteur unique |
| eVar ou s.campaign | ID de publipostage | Collecté à partir des paramètres de requête dans les liens de courrier électronique par le biais de la méthode de collecte automatisée ou d’un plug-in JavaScript. | Il est souvent stocké dans la variable de campagne. |

## Variables facultatives {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Type de variable | Nom | Méthode de remplissage | Description |
|---|---|---|---|
| Événement (compteur) | Fichier téléchargé | Collecté manuellement par le biais des balises Analytics. | Cet événement permet d’identifier les utilisateurs qui ont téléchargé un fichier sur le site. |
| Événement (compteur) | Formulaire commencé | Collecté manuellement par le biais des balises Analytics. | Formulaire commencé permet d’identifier les utilisateurs qui commencent un formulaire, mais ne le remplissent pas entièrement. |
| Événement (compteur) | Formulaire complété | Collecté manuellement par le biais des balises Analytics. | Formulaire complété permet d’identifier les visiteurs qui commencent un formulaire, mais ne le remplissent pas entièrement. |
| eVar | Adresse électronique | Collecté manuellement par le biais des balises Analytics. | Adresse électronique sert à collecter manuellement l’adresse électronique lors de l’inscription ou de la connexion, ou encore depuis d’autres pages qui la collectent. Cette variable est utilisée pour effectuer un remarketing auprès des utilisateurs qui ont choisi de recevoir des courriers électroniques, mais qui n’ont peut-être pas encore cliqué sur l’un d’eux. |
| eVar | Fichier téléchargé | Collecté manuellement par le biais des balises Analytics. | Fichier téléchargé identifie le fichier téléchargé par un visiteur. |
| eVar | Nom du formulaire | Collecté manuellement par le biais des balises Analytics. | Nom du formulaire identifie le formulaire abandonné par un visiteur. |

