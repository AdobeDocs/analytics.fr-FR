---
title: Accès tardifs
description: Découvrez comment les flux de données traitent les accès tardifs.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
TQID: https://experienceleague.adobe.com/eNLHiK8xI-O-E7UDfIkxEfFB0oAQoum6lTXH7OFQJ3c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 317
ht-degree: 48%

---

# Accès tardifs {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="Autoriser les accès tardifs"
>abstract="Sélectionnez cette option pour inclure les données arrivées après la fin du traitement des données par le traitement de flux de données dans la fréquence de création de rapports définie (généralement par semaine ou par heure). Lorsque cette option est activée, chaque fois qu’un flux de données traite des données, il tient compte de l’arrivée des accès tardifs et les regroupe dans le fichier de flux de données suivant envoyé."

<!-- markdownlint-enable MD034 -->

## Comprendre les accès arrivant tardivement

Les données historiques peuvent arriver après la fin du traitement d’une heure ou d’un jour donné par une tâche de flux de données par le biais d’accès horodatés ou de sources de données.

Lors du traitement normal des données par un flux des données, seules les données de sa fenêtre de création de rapports sont examinées (en général, l’heure ou le jour le plus récent). Si des données arrivent après qu’un flux a terminé de traiter cette fenêtre de création de rapports, ces données ne sont jamais incluses dans aucun flux de données.

Lorsque les accès tardifs sont activés, la méthode de traitement est modifiée pour inclure ces données. Chaque fois qu’un flux de données traite des données, il examine les accès tardifs arrivés et les transfère par lots dans le fichier de flux de données suivant envoyé.

## Activer les accès arrivant en retard

Avant d’activer l’option permettant d’autoriser les accès tardifs pour un flux de données, tenez compte des points suivants :

* Les données de différents jours apparaissent fréquemment dans les flux de données lorsque les accès tardifs sont activés. Assurez-vous que la plateforme d’assimilation des flux de données que vous utilisez peut traiter des données de jours différents au sein d’un même fichier.
* Si un fichier de flux de données est retraité, les accès tardifs inclus dans le fichier d’origine sont inclus dans le fichier retraité lors du retraitement dans les 5 premiers jours. Au bout de 5 jours, les accès tardifs ne sont pas inclus dans le fichier retraité.

Vous pouvez activer les accès tardifs lors de la création ou de la modification d’un flux de données en activant l’option **[!UICONTROL Autoriser les accès tardifs]**, comme décrit dans la section [Créer un flux de données](/help/export/analytics-data-feed/create-feed.md).
