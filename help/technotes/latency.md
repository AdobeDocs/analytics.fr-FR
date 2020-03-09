---
description: Les informations suivantes peuvent vous aider à résoudre les problèmes de latence des suites de rapports dans les données Analytics.
keywords: missing data;slow
subtopic: Current data
title: Disponibilité des données et latence
topic: Reports
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
translation-type: tm+mt
source-git-commit: a4a4d9e6e2d3e3ed88b4ef66e9da3b05865a9b79

---


# Disponibilité des données et latence dans Adobe Analytics

En règle générale, vous pouvez vous attendre à voir des données complètes dans les rapports 2 heures après la collecte des données. Les informations suivantes peuvent vous aider à résoudre les problèmes de latence des suites de rapports dans les données Analytics.

## Présentation du traitement par lots des données

Chaque serveur de collecte de données capture et traite des données d’analyse brutes, puis charge les données mises en lots toutes les heures en vue de la création de rapports. Le processus de transfert prend généralement 30 minutes. Dès lors, une latence normale pour le trafic qui se produit directement après la fin du processus de chargement est d’environ 90 minutes (60 minutes jusqu’au chargement par lots suivant, puis 30 minutes pour le transfert et l’affichage du fichier). Pour le trafic qui survient directement avant un transfert, la latence des données peut être de 30 minutes (0 minute jusqu’au prochain transfert par lot, puis 30 minutes pour le transfert et l’affichage des fichiers).

Si nécessaire, le service à la clientèle d’Adobe peut activer des téléchargements de données par lots de 30 minutes (au lieu d’une heure) pour les suites de rapports les plus utilisées.

## Contributeurs à la latence

La latence est un délai plus long que les deux heures habituelles nécessaires aux serveurs de collecte de données pour traiter complètement les données. Elle n&#39;affecte pas la collecte de données ; les données sont toujours collectées pour une implémentation opérationnelle, quelle que soit la latence d’une suite de rapports. Sa gravité (à quel point les données sont à jour) et sa durée (le temps nécessaire pour les résoudre) peuvent varier considérablement. Il est généralement limité à une seule suite de rapports.

On distingue plusieurs catégories de latence :

* **Pic de trafic inattendu :** Ce type de latence survient lorsque plus de données sont envoyées à une suite de rapports que ce qui était prévu ou validé par contrat. Il s’agit de la cause de latence la plus courante.
* **Problèmes matériels normaux :** Adobe applique les meilleures stratégies de gestion et de surveillance des centres de données, de redondance des données et de fiabilité du matériel. Le matériel est mis à jour régulièrement et conjointement avec les fenêtres de maintenance publiées. La maintenance d&#39;urgence d&#39;un matériel défectueux peut nécessiter un arrêt temporaire et nécessaire du traitement des données (et non de la collecte des données), car le matériel de remplacement est mis en ligne. Cela peut se traduire par une latence importante.
* **Données anormales :** Les modèles de données non naturels, tels que les visites exceptionnellement longues causées par un robot ou un analyseur, peuvent temporairement augmenter certaines charges de traitement qui provoquent une latence.

## Fonctions qui dépendent de la latence

Certaines fonctionnalités d’Adobe Experience Cloud s’accompagnent d’une latence innée en plus du temps de traitement standard.

* Analytics pour les  de (A4T) nécessite 5 à 10 minutes de latence supplémentaires pour permettre le stockage des données collectées des deux plateformes dans le même accès.
* Les données horodatées nécessitent un temps supplémentaire en raison des différents serveurs sur lesquels ces données sont traitées. Les accès horodatés reçus en temps réel ou presque peuvent prendre jusqu’à 15 minutes. Les accès reçus avec un horodatage d’hier peuvent prendre jusqu’à 2 heures. Les accès plus anciens peuvent prendre plus de temps, augmentant chaque jour jusqu’à un plafond d’environ 24 heures.

## Moyens d’atténuer ou d’éviter la latence

Il existe plusieurs stratégies visant à prévenir la latence ou à réduire le temps de récupération à la suite d’une latence :

* **Avertissez Adobe des pics de trafic prévus :** Bien qu’il soit impossible d’anticiper chaque pic de trafic sur votre site, il peut arriver que vous attendiez une augmentation significative du trafic. Par exemple, une période de vacances particulièrement réussie ou peu après une campagne de grande envergure. Dans ce cas, nous offrons à votre entreprise le moyen de nous avertir d’une hausse prévue du trafic, de sorte que nous puissions allouer davantage de ressources de traitement à votre suite de rapports. Voir [Planifier un pic](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) de trafic dans le guide de l’utilisateur Admin pour savoir comment avertir Adobe d’un accroissement du trafic.
* **Tenez compte de la charge de traitement lors de l’activation de nouvelles fonctionnalités :** Certaines fonctionnalités nécessitent davantage de traitement que d’autres. Plus il y a de fonctionnalités activées dans une suite de rapports, plus il est difficile de récupérer à la suite d’une latence. Lors de l’activation de fonctionnalités sur une suite de rapports, veuillez tenir compte du fait que les fonctionnalités suivantes augmentent la quantité de données à traiter :

   * Implémentation de plus de 20  sur la même page
   * Règles VISTA complexes
   * Plus de 20 valeurs dans la variable « products »
   * Sérialisation d’événements

* Enable IAB Bot filtering: [Bot filtering](/help/admin/admin/bot-removal/bot-removal.md) can greatly reduce latency if your report suite is frequented by bots or crawlers. Il est conseillé d’utiliser la liste de robots IAB, dans la mesure où elle est mise à jour et gérée par l’[Interactive Advertising Bureau](https://www.iab.net/about_the_iab) (IAB). Un utilisateur peut personnaliser ses propres règles de robots pour compléter celles de l’IAB.

## Que faire en cas de latence ?

Dans les cas de latence, assurez-vous qu’Adobe surveille de manière proactive le pipeline de traitement et fait tout ce qui est possible pour ramener le temps de traitement à la normale le plus rapidement possible. De nombreux problèmes de latence sont résolus en quelques heures. Si une suite de rapports spécifique vous préoccupe, l’un des utilisateurs de votre société ayant souscrit un plan d’assistance peut contacter le service d’assistance pour communiquer l’identifiant de la suite qui présente un problème de latence. L’agent Adobe peut confirmer la latence et vous tenir informé de l’évolution du dossier de résolution.
