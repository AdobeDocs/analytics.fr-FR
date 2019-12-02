---
title: Accès tardifs
description: Découvrez comment les flux de données traitent les accès tardifs.
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Accès tardifs

Les données historiques peuvent arriver une fois qu’une tâche de flux de données a terminé le traitement pendant une heure ou un jour donné, par exemple par le biais d’accès horodatés ou de sources de données. Les accès tardifs sont un paramètre de personnalisation du serveur principal fourni par Adobe pour aider à inclure ces données dans les flux de données.

## Fonctionnement des accès en retard

Lorsqu’un flux de données traite normalement des données, il ne les examine que dans sa fenêtre de création de rapports (généralement l’heure ou le jour le plus récent). Si des données arrivent après la fin du traitement d’un flux dans cette fenêtre de création de rapports, elles ne sont jamais incluses dans un flux de données.

Lorsque les accès arrivant tardivement sont activés, la méthode de traitement change pour inclure ces données. Chaque fois qu’un flux de données traite des données, il examine les accès tardifs qui sont arrivés et les remue par lots dans le fichier de flux de données suivant envoyé sur votre site FTP.

## Activation des accès tardifs

Les accès tardifs peuvent être activés manuellement par Adobe sur des flux de données individuels. Avant de procéder, tenez compte des points suivants :

* Les données relatives à différents jours apparaissent fréquemment dans les flux de données lorsque des accès tardifs sont activés. Assurez-vous que la plate-forme que vous utilisez pour importer des flux de données peut contenir des données provenant de différents jours au sein du même fichier.
* Les accès tardifs augmentent le temps de traitement. En règle générale, ce délai est inférieur à une heure, mais il peut être de plusieurs heures ou plus si votre suite de rapports reçoit un grand nombre d’accès tardifs. Adobe recommande de ne pas activer ce paramètre si l’arrivée en temps voulu des flux de données est indispensable au flux de travail de votre entreprise.
* Si un fichier de flux de données est retraité, les accès tardifs inclus dans le fichier d’origine ne sont pas inclus dans le fichier retraité.

Si vous souhaitez activer les accès tardifs pour un flux de données récurrent existant, demandez à un utilisateur ayant souscrit un plan d’assistance dédié de contacter le service d’assistance clientèle et d’inclure les éléments suivants :

* Remarque que vous souhaitez activer les accès tardifs pour un flux de données spécifique
* Identifiant de suite de rapports
* Nom du flux de données
