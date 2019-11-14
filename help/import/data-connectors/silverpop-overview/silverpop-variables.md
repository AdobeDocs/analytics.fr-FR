---
description: L’intégration des connecteurs de données pour Silverpop utilise des variables Analytics pour effectuer le suivi de diverses mesures Silverpop.
title: Variables d’intégration Analytics
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics Integration Variables{#analytics-integration-variables}

L’intégration des connecteurs de données pour Silverpop utilise des variables Analytics pour effectuer le suivi de diverses mesures Silverpop.

Après avoir identifié l’événement et les eVars à utiliser avec l’intégration Silverpop, utilisez la console d’administration Adobe Analytics pour les activer (voir Suites [de](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)rapports).

Le tableau suivant décrit les variables Analytics nécessaires pour l’intégration de Silverpop.

## Variables requises {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Type de variable | Nom | Méthode de remplissage | Description |
|---|---|---|---|
| event (numeric) | Retours | Importation automatique à partir de Silverpop. | L’événement Rebonds vous permet de voir le nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de remise. |
| event (numeric) | Clics | Importation automatique à partir de Silverpop. | L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. |
| event (numeric) | Ouvre | Importation automatique à partir de Silverpop. | L’événement Ouvert vous permet de voir le nombre de visiteurs qui ont ouvert le message électronique. |
| event (numeric) | Envois | Importation automatique à partir de Silverpop. | L’événement Envoi vous permet de voir le nombre de messages électroniques envoyés. |
| event (numeric) | Désabonnements | Importation automatique à partir de Silverpop. | L’événement Désabonné vous permet de voir le nombre de visiteurs qui ont ouvert le message électronique, puis cliqué sur le lien Désabonner pour exclure les futurs messages électroniques de votre organisation. |
| eVar | Identifiant Silverpop/Identifiant visiteur | Collecté à partir des paramètres de requête dans les liens de courrier électronique par le biais de la méthode de collecte automatisée ou d’un module externe JavaScript. | Identifiant visiteur unique |
| eVar ou s.campaign | ID de courrier | Collecté à partir des paramètres de requête dans les liens de courrier électronique par le biais de la méthode de collecte automatisée ou d’un module externe JavaScript. | Ceci est souvent stocké dans la variable de campagne. |

## Variables facultatives {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Type de variable | Nom | Méthode de remplissage | Description |
|---|---|---|---|
| event (compteur) | Fichier téléchargé | Collecte manuelle par le biais des balises Analytics. | Cet événement permet d’identifier les utilisateurs qui ont téléchargé un fichier sur le site. |
| event (compteur) | Formulaire commencé | Collecte manuelle par le biais des balises Analytics. | Le formulaire démarré permet d’identifier les utilisateurs qui commencent un formulaire, mais ne le remplissent pas. |
| event (compteur) | Formulaire complété | Collecte manuelle par le biais des balises Analytics. | Le formulaire renseigné sert à identifier les visiteurs qui commencent un formulaire et ne le remplissent pas. |
| eVar | Email Address | Collecte manuelle par le biais des balises Analytics. | L’adresse électronique permet de collecter manuellement l’adresse électronique lors de l’inscription, de la connexion ou d’autres pages sur lesquelles l’adresse électronique est collectée. Cette variable est utilisée pour effectuer un nouveau marketing pour les utilisateurs qui ont choisi de recevoir un courrier électronique, mais qui n’ont peut-être pas déjà cliqué par le passé. |
| eVar | Fichier téléchargé | Collecte manuelle par le biais des balises Analytics. | Le fichier téléchargé identifie le fichier téléchargé par un visiteur. |
| eVar | Nom du formulaire | Collecte manuelle par le biais des balises Analytics. | Nom du formulaire identifie le formulaire abandonné par un visiteur. |

