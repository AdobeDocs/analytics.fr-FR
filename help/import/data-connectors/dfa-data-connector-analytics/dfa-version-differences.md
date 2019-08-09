---
description: 'Il existe actuellement trois versions de l’intégration DFA : versions 1.0, 1.5 et 2.0.'
keywords: DFA
seo-description: 'Il existe actuellement trois versions de l’intégration DFA : versions 1.0, 1.5 et 2.0.'
seo-title: Différences de versions
solution: Analytics
title: Différences de versions
topic: Connecteurs de données
uuid: e 0 ae 70 f 0-369 d -451 a -9752-02660 d 270660
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Différences de versions{#version-differences}

Il existe actuellement trois versions de l’intégration DFA : versions 1.0, 1.5 et 2.0.

Le tableau suivant résume les fonctions de chaque version de l’intégration.

| Fonctionnalité | Version 1.0 | Version 1.5 | Version 2.0 |
|---|---|---|---|
| Mesures de nuit de clics et d’impressions DFA | Oui | Oui | Oui |
| Suivi des clics publicitaires et des affichages publicitaires | Oui | Oui | Oui |
| L’intégration reçoit les données à un niveau Advertiser | Non | Oui | Oui |
| L’intégration reçoit les données à un niveau de configuration Floodlight | Non | Non | Oui |
| Mesures de coûts | Non | Non | Oui |
| Mesures de créatifs | Non | Non | Oui |
| Chaînes de requête supérieures à 2 000 octets | Non | Oui | Oui |
| Utilise le module Integrate pour une collecte optimale des données tierces | Non | Oui | Oui |
| Suivi des dépassements de délai et des erreurs | Non | Oui | Oui |
| Identifiant côté client négocié non nécessaire | Non | Non | Oui |

## Version 1.5 {#section-b5a3e967cfa141ea8f740612336181be}

La version 1.5 de l’intégration introduit le module Integrate au code JavaScript de la page d’entrée. Le module Integrate permet d’envoyer des demandes à taille fixe au serveur de publicités DFA (ad.doubleclick.net) qui pallie les limites de demandes à 2 000 octets de l’intégration précédente. Elle comprend également une variable de dépassement de délai configurable, *`s.maxDelay`*, pour continuer à collecter les données des visiteurs Adobe lors de la panne du réseau. Les erreurs et dépassements de délai peuvent également être capturés dans les variables Analytics.

L’illustration suivante présente les interactions réseau sur la page d’entrée de la version 1.5.

![](assets/DFA_About_1_5.png)

Dans la version 1.5, le module Integrate (2) demande les données au serveur Floodlight (3). Le serveur Floodlight redirige la demande vers le serveur de publicités DFA, qui renvoie les données sur le visiteur de la même façon que la version 1.0. Il envoie une instruction de redirection 302 (4) à un service de traduction spécial à l’adresse integrate.112.2o7.net, qui convertit la structure de la réponse en objet JSON. Le module Integrate consomme cet objet JSON et transmet les informations au suivi Adobe (5).

La migration de la version 1.0 de l’intégration à la version 1.5 implique un changement JavaScript. Pour obtenir ce code JavaScript, connectez-vous à votre compte Adobe Online Marketing Suite, choisissez le produit Genesis, cliquez sur Edit (Modifier) dans votre intégration DFA, puis exécutez l’assistant. Si un identifiant de site client a déjà été affecté, vous recevrez immédiatement le nouveau code JavaScript par courrier électronique une fois l’intégration enregistrée. Une fois que vous avez ce code, une nouvelle version du s_code principal est également nécessaire pour le module Integrate. Vous pouvez demander ce code auprès de votre gestionnaire de compte ou de votre conseiller en mise en œuvre.

L’une des fonctions importantes du nouveau code JavaScript réside dans le fait qu’aucun changement de mise en œuvre n’est nécessaire entre la version 1.5 et la version 2.0.

## Version 2.0 {#section-afd56de0c56c4489bb5ddc5798d6709a}

La dernière version de l’intégration DFA procure des données pour une configuration Floodlight entière dans l’intégration. Avant la version 2.0, des intégrations individuelles étaient liées à une seule instance DFA Advertiser. Grâce à ce changement, les mesures de clics, d’impressions et de coûts pour toute la configuration Floodlight seront incluses dans la suite de rapports intégrée. Il est également possible d’effectuer le suivi intersite des affichages publicitaires, quand ces deux sites se trouvent dans la même configuration Floodlight.

Les mesures de coûts de médias sont également disponibles à compter de la version 2.0 de l’intégration. Pour activer les mesures de coûts de médias pour une intégration, vous devez choisir un événement Rapports et analyses pour le coût de médias dans l’assistant Genesis, puis spécifier la devise des chiffres de mesures dans l’interface DFA.

Les dépassements de délai devraient diminuer avec l’intégration 2.0, puisque les redirections 302 ont été éliminées, tandis que la quantité de données pouvant être intégrées devrait augmenter.

Si une configuration Floodlight est une configuration partagée dans DFA, la mise à niveau de la version 1. 5 à la version 2.0 génère des données de conversion pour tous les publicitaires partagés dans la configuration Floodlight à inclure dans la suite de rapports.

## Mise à niveau vers la version 2.0 {#section-f0bf90b9a7a1434ab1540b6c0999f4c7}

Le tableau suivant décrit les propriétaires pour la migration vers les versions plus récentes de l’intégration :

| Migration | Propriétaire | Tâches |
|---|---|---|
| Version 1.0 à 1.5 | Client | Mettre en œuvre le code JavaScript de la version 1.5 avec le module Integrate |
| Version 1.5 à 2.0 | Client | Le client commence la discussion avec Google au sujet des délais de mise à niveau. Après approbation, Google active la fonction AdServing avancée. |

