---
description: Les informations suivantes peuvent vous aider à résoudre les problèmes de latence des suites de rapports dans les données Analytics.
keywords: données manquantes;lent
title: Disponibilité des données et latence
feature: Data Configuration and Collection
exl-id: fedef3ea-dde6-460f-90e3-1e661ed29b78
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 100%

---

# Disponibilité des données et latence dans Adobe Analytics

En règle générale, les données complètes s’affichent dans les rapports 2 heures après avoir été collectées. Les informations suivantes peuvent vous aider à résoudre les problèmes de latence des suites de rapports dans les données Analytics.

## Comprendre le concept de traitement des données par lots

Chaque serveur de collecte de données capture et traite des données d’analyse brutes, puis charge les données mises en lots toutes les heures en vue de la création de rapports. Le processus de transfert prend généralement 30 minutes. Dès lors, une latence normale pour le trafic qui se produit directement après la fin du processus de chargement est d’environ 90 minutes (60 minutes jusqu’au chargement par lots suivant, puis 30 minutes pour le transfert et l’affichage du fichier). Dans le cas du trafic enregistré directement avant un chargement, la latence des données peut être limitée à 30 minutes (0 minute jusqu’au chargement par lots suivant, puis 30 minutes pour le transfert et l’affichage du fichier).

Si nécessaire, l’assistance clientèle d’Adobe peut activer des téléchargements de données par lots toutes les 30 minutes (au lieu de toutes les heures) pour vos suites de rapports les plus utilisées.

## Contributeurs à la latence

Le terme « latence » désigne un délai supérieur aux deux heures habituellement nécessaires aux serveurs de collecte de données pour traiter les données intégralement. Elle n’a aucune incidence sur la collecte de données qui continuent d’être collectées et mises en œuvre de manière opérationnelle, quelle que soit la latence de la suite de rapports. Sa gravité (état d’actualisation des données) et sa durée (temps nécessaire pour y remédier) peuvent varier sensiblement. Toutefois, la latence se limite généralement à une seule suite de rapports.

On distingue les différentes catégories de latence suivantes :

* **Pic de trafic imprévu :** ce type de latence se produit lorsque la quantité de données envoyées vers une suite de rapports est supérieure à ce qui était prévu dans le contrat. Il s’agit de la cause de latence la plus courante.
* **Problèmes matériels normaux :** Adobe applique les meilleures stratégies en termes de gestion et de surveillance des centres de données, de redondance des données et de fiabilité du matériel. Le matériel est mis à jour régulièrement et conjointement avec les fenêtres de maintenance publiées. En cas de maintenance d’urgence d’un matériel défectueux, un arrêt temporaire du traitement des données (et non de la collecte des données) peut s’avérer nécessaire pendant la mise en service du matériel de remplacement. Cela peut entraîner une latence importante.
* **Données anormales :** des schémas de données anormaux, tels que des visites inhabituellement longues associées à un robot ou à un robot d’indexation, peuvent accroître temporairement certaines charges de traitement, ce qui entraîne une latence.

## Fonctions dépendant de la latence

Certaines fonctionnalités d’Adobe Experience Cloud s’accompagnent d’une latence innée en plus du temps de traitement standard.

* Analytics for Target (A4T) provoque 5 à 10 minutes de latence supplémentaires pour permettre le stockage des données collectées sur les deux plateformes lors du même accès.
* Les données horodatées prennent plus de temps à cause des différents serveurs sur lesquels elles sont traitées. Les accès horodatés reçus en temps réel ou presque peuvent prendre jusqu’à 15 minutes. Les accès reçus avec un horodatage datant de la veille peuvent prendre jusqu’à 2 heures. Les accès plus anciens peuvent prendre plus de temps, augmentant chaque jour jusqu’à une limite d’environ 24 heures.

## Moyens d’atténuer ou d’éviter une latence

Il existe plusieurs stratégies visant à prévenir la latence ou à réduire le temps de récupération à la suite d’une latence :

* **Informer Adobe des pics de trafic prévus :** bien qu’il soit impossible d’anticiper tous les pics de trafic sur votre site, vous pouvez, dans certains cas, prévoir une hausse sensible du trafic. Cela peut survenir, par exemple, en cas de période de vacances particulièrement prospère ou juste après la diffusion d’une vaste campagne. Dans de tels cas, Adobe fournit à votre entreprise le moyen de nous avertir d’une hausse prévue du trafic afin que nous puissions allouer davantage de ressources de traitement à votre suite de rapports. Voir [Planifier un pic de trafic](/help/admin/tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md) dans le guide d’utilisation destiné à l’administrateur pour savoir comment avertir Adobe d’une hausse du trafic.
* **Tenir compte de la charge de traitement lors de l’activation de nouvelles fonctionnalités :** certaines fonctionnalités consomment plus de ressources de traitement que d’autres. Plus il y a de fonctionnalités activées dans une suite de rapports, plus il est difficile de récupérer à la suite d’une latence. Lors de l’activation de fonctionnalités sur une suite de rapports, veuillez tenir compte du fait que les fonctionnalités suivantes augmentent la quantité de données à traiter :

   * Mise en œuvre de plus de 20 événements sur la même page
   * Règles VISTA complexes
   * Plus de 20 valeurs dans la variable « products »
   * Sérialisation d’événements

* Activer les règles de filtrage des robots IAB : le [filtrage des robots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) peut réduire sensiblement la latence si votre suite de rapports est fréquentée par des robots ou des robots d’indexation. Il est conseillé d’utiliser la liste de robots IAB, dans la mesure où elle est mise à jour et gérée par l’[Interactive Advertising Bureau](https://www.iab.net/about_the_iab) (IAB). Un utilisateur peut personnaliser ses propres règles de filtrage des robots pour compléter celles émises par l’IAB.

## Que faire en cas de latence ?

En cas de latence, assurez-vous qu’Adobe surveille de manière proactive le pipeline de traitement et fait tout ce qui est possible pour ramener le temps de traitement à la normale le plus vite possible. De nombreux problèmes de latence sont résolus en quelques heures. Si une suite de rapports spécifique vous préoccupe, l’un des utilisateurs de votre société ayant souscrit un plan d’assistance peut contacter l’assistance clientèle pour communiquer l’identifiant de la suite qui présente un problème de latence. L’agent Adobe peut confirmer la latence et vous tenir informé de l’évolution du dossier de résolution.
