---
title: Accès tardifs
description: Découvrez comment les flux de données traitent les accès tardifs.
translation-type: ht
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Accès tardifs

Les données historiques peuvent arriver après la fin du traitement d’une heure ou d’un jour donné par une tâche de flux de données par le biais d’accès horodatés ou de sources de données. Adobe fournit les accès tardifs en tant que paramètre de personnalisation du serveur principal pour aider à inclure ces données dans les flux de données.

## Fonctionnement des accès tardifs

Lors du traitement normal des données par un flux des données, seules les données de sa fenêtre de création de rapports sont examinées (en général, l’heure ou le jour le plus récent). Si des données arrivent après qu’un flux a terminé de traiter cette fenêtre de création de rapports, ces données ne sont jamais incluses dans aucun flux de données.

En activant les accès tardifs, la méthode de traitement change de manière à inclure ces données. Chaque fois qu’un flux de données traite des données, il tient compte de l’arrivée des accès tardifs et les regroupe dans le fichier de données de flux suivant envoyé vers votre site FTP.

## Activation des accès tardifs

Adobe peut activer manuellement les accès tardifs sur des flux de données individuels. Avant de procéder à l’activation, tenez compte des points suivants :

* Les données de jours différents apparaissent fréquemment dans les flux de données lorsque les accès tardifs sont activés. Assurez-vous que la plateforme d’assimilation des flux de données que vous utilisez peut traiter des données de jours différents au sein d’un même fichier.
* Les accès tardifs augmentent les temps de traitement. En règle générale, ce retard est inférieur à une heure, mais il peut s’élever à plusieurs heures voire plus si votre suite de rapports reçoit un nombre important d’accès tardifs. Adobe recommande de ne pas activer ce paramètre si l’arrivée des flux de données dans les temps est impérative pour le flux de travail de votre entreprise.
* Si un fichier de flux de données est traité à nouveau, les accès tardifs inclus dans le fichier d’origine ne sont pas inclus dans le fichier retraité.

Si vous souhaitez activer les accès tardifs pour un fichier de données récurrent existant, demandez à un utilisateur habilité de contacter l’assistance clientèle et incluez les éléments suivants :

* Une note disant que vous aimeriez activer les accès tardifs dans un fichier de données spécifique
* Identifiant de suite de rapports
* Nom du flux de données
