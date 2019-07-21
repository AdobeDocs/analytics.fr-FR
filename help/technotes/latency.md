---
description: Les informations suivantes peuvent vous aider à résoudre les problèmes de latence des suites de rapports dans les données Analytics.
keywords: données manquantes ; lent
seo-description: Les informations suivantes peuvent vous aider à résoudre les problèmes de latence des suites de rapports dans les données Analytics.
seo-title: Disponibilité et latence des données
solution: Analytics
subtopic: Données actives
title: Disponibilité et latence des données
topic: Présentation
uuid: 1 f 0 e 67 e 3-6 cea -4 af 8-8 b 18-7 ae 9223 df 7 c 8
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Disponibilité et latence des données dans Adobe Analytics

En règle générale, vous pouvez voir des données complètes dans les rapports 2 heures après la collecte des données. Les informations suivantes peuvent vous aider à résoudre les problèmes de latence des suites de rapports dans les données Analytics.

## Présentation du traitement des données par lots

Chaque serveur de collecte de données capture et traite des données d’analyse brutes, puis charge les données mises en lots toutes les heures en vue de la création de rapports. Le processus de transfert prend généralement 30 minutes. Dès lors, une latence normale pour le trafic qui se produit directement après la fin du processus de chargement est d’environ 90 minutes (60 minutes jusqu’au chargement par lots suivant, puis 30 minutes pour le transfert et l’affichage du fichier). Pour le trafic qui se produit directement avant un transfert, la latence des données peut être aussi courte que 30 minutes (0 minute jusqu'au chargement par lots suivant, puis 30 minutes pour le transfert et l'affichage des fichiers).

Au besoin, le service à la clientèle Adobe peut activer des téléchargements de données par lots de 30 minutes (plutôt que toutes les heures) pour vos suites de rapports les plus utilisées.

## Contributeurs à la latence

La latence est un délai plus long que les 2 heures habituelles de traitement des données par les serveurs de collecte de données. Elle n'affecte pas la collecte de données ; les données sont toujours collectées pour une implémentation opérationnelle, quelle que soit la latence d'une suite de rapports. Sa gravité (en fonction de la taille des données) et de la longueur (temps de résolution) peut varier considérablement. Elle est généralement limitée à une seule suite de rapports.

On distingue plusieurs catégories de latence :

* **Pic de trafic inattendu :** Ce type de latence survient lorsque d'autres données sont envoyées à une suite de rapports qu'une suite de rapports ne l'a pas été. Il s’agit de la cause de latence la plus courante.
* **Problèmes matériels normaux :** Adobe utilise des stratégies de pointe pour la gestion et la surveillance des centres de données, la redondance des données et la fiabilité du matériel. Le matériel est mis à jour régulièrement et conjointement avec les fenêtres de maintenance publiées. La maintenance d'urgence d'un matériel défectueux peut nécessiter un arrêt temporaire et temporaire des données : le traitement (et non la collecte de données) en tant que matériel de remplacement est mis en ligne. Cela peut se traduire par une latence importante.
* **Données anormales :** Les schémas de données anormaux, tels que les visites inhabituellement longues générées par un robot ou un moteur de recherche, peuvent temporairement accroître certaines charges de traitement qui entraînent une latence.

## Fonctionnalités dépendant de la latence

Certaines fonctionnalités d'Adobe Experience Cloud sont accompagnées d'un temps de latence inné au-dessus du temps de traitement standard.

* Analytics pour Target (A 4 T) nécessite 5 à 10 minutes supplémentaires de latence pour que les données collectées des deux plateformes soient stockées dans le même accès.
* Les données horodatées nécessitent une durée supplémentaire due aux différents serveurs sur lesquels ces données sont traitées. Les accès horodatés reçus pendant ou presque en temps réel peuvent prendre jusqu'à 15 minutes. Les accès reçus avec un horodatage d'hier peuvent prendre jusqu'à 2 heures. Les anciens accès peuvent prendre plus de temps, ce qui augmente chaque jour jusqu'à 24 heures environ.

## Méthodes permettant d'atténuer ou d'éviter la latence

Il existe plusieurs stratégies visant à prévenir la latence ou à réduire le temps de récupération à la suite d’une latence :

* **Avertir Adobe des pics de trafic attendus :** Bien qu'il soit impossible d'anticiper chaque pic de trafic sur votre site, il se peut que vous attendiez une augmentation importante du trafic. Par exemple, une période de vacances particulièrement réussie ou peu après une longue campagne Push. Dans ce cas, nous offrons à votre entreprise le moyen de nous avertir d’une hausse prévue du trafic, de sorte que nous puissions allouer davantage de ressources de traitement à votre suite de rapports. See [Schedule a traffic spike](../admin/c-traffic-management/t-traffic-schedule-spike.md) in the Admin user guide to learn how to notify Adobe of increased traffic.
* **Envisagez la charge de traitement lors de l'activation de nouvelles fonctionnalités :** Certaines fonctionnalités consomment plus de ressources de traitement que d'autres. Plus il y a de fonctionnalités activées dans une suite de rapports, plus il est difficile de récupérer à la suite d’une latence. Lors de l’activation de fonctionnalités sur une suite de rapports, veuillez tenir compte du fait que les fonctionnalités suivantes augmentent la quantité de données à traiter :

   * Implémentation de plus de 20 événements sur la même page
   * Règles VISTA complexes
   * Plus de 20 valeurs dans la variable « products »
   * Sérialisation d’événements

* Enable IAB Bot filtering: [Bot filtering](https://marketing.adobe.com/resources/help/en_US/admin/index.html?f=c_bot_rules) can greatly reduce latency if your report suite is frequented by bots or crawlers. Il est conseillé d’utiliser la liste de robots IAB, dans la mesure où elle est mise à jour et gérée par l’[Interactive Advertising Bureau](https://www.iab.net/about_the_iab) (IAB). Un utilisateur peut personnaliser ses propres règles de robots pour compléter celles de l'IAB.

## Que faire en cas de latence ?

Dans les cas où la latence se produit, assurez-vous qu'Adobe contrôle de manière proactive le pipeline de traitement et qu'il effectue tout ce qui est possible pour rétablir le temps de traitement normalement. De nombreux problèmes de latence sont résolus en quelques heures. Si une suite de rapports spécifique vous préoccupe, l’un des utilisateurs de votre société ayant souscrit un plan d’assistance peut contacter le service d’assistance pour communiquer l’identifiant de la suite qui présente un problème de latence. L’agent Adobe peut confirmer la latence et vous tenir informé de l’évolution du dossier de résolution.
