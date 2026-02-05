---
title: Accès tardifs
description: Découvrez comment les flux de données traitent les accès tardifs.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 4d0007d1a23a81f0d5ba60541b4f7b9ac7b00ace
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 21%

---

# Accès tardifs {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="Autoriser les accès en retard"
>abstract="Sélectionnez cette option pour inclure les données arrivées une fois que la tâche de flux de données a terminé le traitement des données dans la fréquence de création de rapports définie (généralement quotidienne ou horaire). Lorsque cette option est activée, chaque fois qu’un flux de données traite des données, il examine les accès tardifs arrivés et les transfère par lots avec le fichier de flux de données suivant envoyé."

<!-- markdownlint-enable MD034 -->

## Comprendre les accès arrivant tardivement

Les données historiques peuvent arriver une fois qu’une tâche de flux de données a terminé le traitement pendant une heure ou une journée donnée, par exemple par le biais d’accès horodatés ou de sources de données.

Lors du traitement normal des données par un flux des données, seules les données de sa fenêtre de création de rapports sont examinées (en général, l’heure ou le jour le plus récent). Si des données arrivent après qu’un flux a terminé de traiter cette fenêtre de création de rapports, ces données ne sont jamais incluses dans aucun flux de données.

Lorsque les accès tardifs sont activés, la méthode de traitement est modifiée pour inclure ces données. Chaque fois qu’un flux de données traite des données, il examine les accès tardifs arrivés et les transfère par lots dans le fichier de flux de données suivant envoyé.

## Activer les accès arrivant en retard

Avant d’activer l’option permettant d’autoriser les accès tardifs pour un flux de données, tenez compte des points suivants :

* Les données de différents jours apparaissent fréquemment dans les flux de données lorsque les accès tardifs sont activés. Assurez-vous que la plateforme d’assimilation des flux de données que vous utilisez peut traiter des données de jours différents au sein d’un même fichier.
* Si un fichier de flux de données est retraité, les accès tardifs inclus dans le fichier d’origine sont inclus dans le fichier retraité lors du retraitement dans les 5 premiers jours. Au bout de 5 jours, les accès tardifs ne sont pas inclus dans le fichier retraité.

Vous pouvez activer les accès tardifs lors de la création ou de la modification d’un flux de données en activant l’option **[!UICONTROL Autoriser les accès tardifs]**, comme décrit dans la section [Créer un flux de données](/help/export/analytics-data-feed/create-feed.md).
