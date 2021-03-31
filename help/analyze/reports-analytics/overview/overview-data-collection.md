---
description: En savoir plus sur la méthode de collecte des données pour Adobe Analytics.
subtopic: Get started
title: Collecte de données
uuid: 4dd9a23d-ad49-4841-8f4c-32c3993851f2
feature: Concepts de base des rapports et analyses
role: Professionnel, Administrateur
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 96%

---


# Collecte de données

En savoir plus sur la méthode de collecte des données pour Adobe Analytics.

Chaque page suivie par Adobe comporte un extrait de code JavaScript autorisé par Adobe. Ce code est fourni par votre gestionnaire de compte.

A un haut niveau, le processus de collecte de données s’effectue comme suit :

![](assets/data_collection.png)

1. Un visiteur consulte une page web qui contient le code de collecte de données.
1. Tandis que la page se charge, le code de collecte de données envoie une demande d’image (appelée balise web) aux serveurs de collecte de données Adobe. La demande d’image contient les données que vous cherchez à collecter sur l’interaction du visiteur avec votre site web.
1. Adobe stocke les données dans les suites de rapports. Vous pouvez vous connecter pour accéder aux données de la suite de rapports et générer des rapports sur l’activité des visiteurs sur votre site web.

La collecte de données est très rapide et n’affecte pas de manière notable la durée de chargement d’une page. Les données collectées comprennent les pages vues qui résultent du fait d’avoir cliqué sur les boutons **Actualiser** ou **Précédent** du navigateur. Le code JavaScript s’exécute même si la page est récupérée à partir de la mémoire cache.

Reportez-vous à la section [Collecte de données dans Analytics](/help/import/home.md).
