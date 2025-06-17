---
title: Accès tardifs
description: Découvrez comment les flux de données traitent les accès tardifs.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 81cbb115d50e1f55a67aac8b107749d0a5a5928b
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 85%

---

# Accès tardifs

Les données historiques peuvent arriver après la fin du traitement d’une heure ou d’un jour donné par une tâche de flux de données par le biais d’accès horodatés ou de sources de données. Adobe fournit les accès tardifs en tant que paramètre de personnalisation du serveur principal pour aider à inclure ces données dans les flux de données.

## Fonctionnement des accès tardifs

Lors du traitement normal des données par un flux des données, seules les données de sa fenêtre de création de rapports sont examinées (en général, l’heure ou le jour le plus récent). Si des données arrivent après qu’un flux a terminé de traiter cette fenêtre de création de rapports, ces données ne sont jamais incluses dans aucun flux de données.

En activant les accès tardifs, la méthode de traitement change de manière à inclure ces données. Chaque fois qu’un flux de données traite des données, il tient compte de l’arrivée des accès tardifs et les regroupe dans le fichier de données de flux suivant envoyé vers votre site FTP.

## Activation des accès tardifs

Adobe peut activer manuellement les accès tardifs sur des flux de données individuels. Avant de procéder à l’activation, tenez compte des points suivants :

* Les données de jours différents apparaissent fréquemment dans les flux de données lorsque les accès tardifs sont activés. Assurez-vous que la plateforme d’assimilation des flux de données que vous utilisez peut traiter des données de jours différents au sein d’un même fichier.
* Si un fichier de flux de données est retraité, les accès tardifs inclus dans le fichier d’origine sont inclus dans le fichier retraité lors du retraitement dans les 5 premiers jours. Au bout de 5 jours, les accès tardifs ne sont pas inclus dans le fichier retraité.

Si vous souhaitez activer les accès tardifs pour un fichier de données récurrent existant, demandez à un utilisateur habilité de contacter l’assistance clientèle et incluez les éléments suivants :

* Une note disant que vous aimeriez activer les accès tardifs dans un fichier de données spécifique
* Identifiant de suite de rapports
* Nom du flux de données
