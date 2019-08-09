---
description: L'intégration des Connecteurs de données pour Silverpop utilise les variables Analytics pour effectuer le suivi de diverses mesures Silverpop.
seo-description: L'intégration des Connecteurs de données pour Silverpop utilise les variables Analytics pour effectuer le suivi de diverses mesures Silverpop.
seo-title: Variables d'intégration Analytics
title: Variables d'intégration Analytics
uuid: 3 aef 3 caf-e 24 e -4 fe 7-b 4 d 7-50 ca 0 f 6703 b 5
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics Integration Variables{#analytics-integration-variables}

L'intégration des Connecteurs de données pour Silverpop utilise les variables Analytics pour effectuer le suivi de diverses mesures Silverpop.

Après avoir identifié l'événement et les evars à utiliser avec l'intégration Silverpop, utilisez la console d'administration Adobe Analytics pour les activer (voir [Report Suites](http://microsite.omniture.com/t2/help/en_US/reference/index.html?f=report_suites_admin)).

Le tableau suivant décrit les variables Analytics nécessaires pour l'intégration de Silverpop.

## Variables obligatoires {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Type de variable | Nom | Méthode de remplissage | Description |
|---|---|---|---|
| événement (numérique) | Rebonds | Importé automatiquement à partir de Silverpop. | L'événement Rebonds vous permet de voir le nombre de courriers électroniques qui n'ont pas été remis aux destinataires en raison d'un problème de remise. |
| événement (numérique) | Clics | Importé automatiquement à partir de Silverpop. | L'événement Clicked vous permet de voir le nombre de visiteurs qui ont cliqué sur le courriel. |
| événement (numérique) | Ouvertures | Importé automatiquement à partir de Silverpop. | L'événement Ouvert vous permet de voir le nombre de visiteurs qui ont ouvert le courriel. |
| événement (numérique) | Envoie | Importé automatiquement à partir de Silverpop. | L'événement Envoyer vous permet de voir le nombre de courriers électroniques envoyés. |
| événement (numérique) | Désabonne | Importé automatiquement à partir de Silverpop. | L'événement Non abonné vous permet de voir le nombre de visiteurs qui ont ouvert le courriel mais, d'autre part, cliquent sur le lien Désabonner pour exclure les futurs courriers électroniques de votre organisation. |
| eVar | ID de Silverpop/Identifiant visiteur | Collecte à partir des paramètres de requête dans les liens de courrier électronique via la méthode de collecte automatisée ou un module JavaScript. | Identifiant visiteur unique |
| Evar ou s. campaign | ID de publipostage | Collecte à partir des paramètres de requête dans les liens de courrier électronique via la méthode de collecte automatisée ou un module JavaScript. | Elle est souvent stockée dans la variable campaign. |

## Variables facultatives {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Type de variable | Nom | Méthode de remplissage | Description |
|---|---|---|---|
| event (compteur) | Fichier téléchargé | Collecte manuelle par le biais des balises Analytics. | Cet événement est utilisé pour identifier les utilisateurs qui ont téléchargé un fichier sur le site. |
| event (compteur) | Formulaire commencé | Collecte manuelle par le biais des balises Analytics. | Le début du formulaire permet d'identifier les utilisateurs qui commencent un formulaire, mais ne le terminent pas. |
| event (compteur) | Formulaire complété | Collecte manuelle par le biais des balises Analytics. | Le formulaire Terminé est utilisé pour identifier les visiteurs qui commencent un formulaire et ne le terminent pas. |
| eVar | Email Address | Collecte manuelle par le biais des balises Analytics. | L'adresse électronique permet de collecter manuellement l'adresse électronique à l'inscription, à la connexion ou à d'autres pages sur lesquelles l'adresse électronique est collectée. Cette variable est utilisée pour le marketing pour les utilisateurs qui ont choisi de recevoir un courrier électronique, mais qui n'ont peut-être pas déjà cliqué par courriel dessus. |
| eVar | Fichier téléchargé | Collecte manuelle par le biais des balises Analytics. | Le fichier téléchargé identifie le fichier téléchargé par un visiteur. |
| eVar | Nom du formulaire | Collecte manuelle par le biais des balises Analytics. | Le nom du formulaire identifie le formulaire abandonné par un visiteur. |

