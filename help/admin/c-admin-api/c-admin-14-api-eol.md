---
description: Lien vers l’API d’administration Adobe Analytics sur github.
title: FAQ sur la fin de vie des API Adobe Analytics 1.4
feature: Admin Tools
role: Admin
source-git-commit: 0aaeb60528f8ff1b1067f059710c9d9fa8e1886f
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 2%

---

# FAQ sur la fin de vie des API Adobe Analytics 1.4

## Avis de fin de vie

**Qu’est-ce qui est en train d’être retiré ?**

* API Adobe Analytics 1.4

* Adobe Analytics WSSE Authentication

**Quand est-ce qu&#39;il est arrêté ?**

Ces services seront abandonnés le 12 août 2026. Après cette date, ils ne seront plus accessibles.

## API 1.4

**Quels sont ces services ?**

Les [ API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/) sont un ensemble d’API qui permettent de nombreuses actions, telles que la création de rapports, les classifications, les flux de données et les configurations de suite de rapports.

**Que dois-je faire pour migrer ?**

Les [ API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) offrent un chemin de migration vers l’avant pour les utilisateurs d’API 1.4. Les clients qui utilisent actuellement les API 1.4 peuvent migrer leurs intégrations vers les API 2.0 (les mêmes API dont dépend l’application Adobe Analytics) et tirer parti des dernières fonctionnalités.

Les API 2.0 vous permettent d’effectuer pratiquement toute action que vous pouvez effectuer dans l’interface utilisateur d’Analytics, comme la création de rapports ou la gestion de composants tels que les segments et les mesures calculées.

**Les API 2.0 offrent-elles les mêmes fonctionnalités que les API 1.4 ?**
Toutes les fonctionnalités disponibles dans les API 1.4 peuvent être réalisées à l’aide des [ API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/). Certaines fonctionnalités offrent les mêmes fonctionnalités que les API de la version 1.4. Elles vous permettent d’effectuer la plupart des actions que vous pouvez effectuer dans l’interface utilisateur d’Analytics, telles que la création de rapports ou la gestion de composants tels que les segments et les mesures calculées.

## Authentification WSSE

**Quels sont ces services ?**

L’authentification WSSE est un protocole d’authentification hérité pris en charge par les API Analytics 1.4. Il a été remplacé par les options d’authentification basées sur OAuth fournies dans le [Adobe Developer Console](https://developer.adobe.com/console/home).

**Que dois-je faire pour migrer ?**

Les clients WSSE doivent mettre à jour leurs authentifications pour utiliser les informations d’identification configurées dans Adobe Developer Console. Pour ce faire, connectez-vous à [Adobe Developer Console](https://developer.adobe.com/console/home) pour créer un projet pour votre intégration de l’API Analytics 2.0. Choisissez entre les méthodes d’authentification OAuth User et OAuth Server-to-Server.

## Questions

Q : **Cela a-t-il un impact sur mes projets d’E/S d’Adobe existants pour les API Analytics ?**

R : Tous les projets existants utilisant les API Analytics 1.4 seront affectés. Ces intégrations doivent être migrées vers les API [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) avant la date limite de fin de vie.

Q : **J’ai partagé mes informations d’identification d’Adobe avec un autre produit ou application qui utilise les API Analytics. Sont-elles affectées ?**

R : Si ce produit ou cette application utilise vos informations d’identification WSSE et/ou appelle les API Analytics 1.4, il est affecté et devra migrer avant la date limite de fin de vie. Contactez le produit ou le fournisseur d’applications pour plus d’informations sur leurs plans de migration et leur calendrier.

Q : **Je ne suis pas sûr de l’API Adobe Analytics que nous utilisons.**

R : Vous pouvez identifier l’API que vous utilisez en fonction de l’adresse appelée dans votre intégration.

Les API d’Adobe Analytics 1.4 sont accessibles en appelant l’une des URL ci-dessous :
* https://api.omniture.com
* https://api3.omniture.com
* https://api4.omniture.com
* https://api5.omniture.com

Les [ API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) sont accessibles en appelant l’URL suivante :
* https://analytics.adobe.io

Si vous utilisez api*.omniture.com, vous devez migrer vers les [API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/).

Q : **Les API Adobe Analytics 2.0 sont-elles identiques aux API 1.4 ? Dans le cas contraire, quelles sont les plus grandes différences ?**

R : Les API Adobe Analytics 2.0 ne sont pas identiques aux API 1.4, mais elles offrent des fonctionnalités comparables, notamment les avantages suivants :

* Des temps de réponse plus rapides avec des méthodes de requête plus simples et plus efficaces, ce qui évite d’avoir à interroger les données

* Fonctionnalité de programmation pour les requêtes et les mises à jour de rapports dynamiques

* Gestion des erreurs plus élégante

* Fonctionnement flexible pour accomplir tout ce que vous pouvez accomplir à partir d’Analysis Workspace

* Cohérence et correspondance des appels API avec les actions de l’interface utilisateur

* Accès à tous les modèles Attribution IQ utilisés dans Analysis Workspace

* Accès à tous les algorithmes de détection des anomalies utilisés dans Analysis Workspace

* La possibilité de s’intégrer à d’autres produits Experience Cloud

* Augmentation de la capacité des rapports de ventilation multiple

* Accès aux dernières fonctionnalités Analytics

Le guide [Migration vers les API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) présente les principales différences entre les API 1.4 et 2.0. Des informations supplémentaires sont également disponibles dans la [FAQ sur l’API Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/).

Q : **Cela a-t-il un impact sur la collecte de données ?**

R : La fin de vie d’Adobe Analytics 1.4 n’a aucune incidence sur vos solutions de balisage, telles que Balises (anciennement Adobe Launch), WebSDK ou AppMeasurement.js. Cependant, si vous utilisez les API Sources de données, Insertion de données ou Classifications 1.4 pour collecter ou améliorer vos données, vous devez migrer ces workflows vers les API Adobe Analytics 2.0. Pour plus d’informations, reportez-vous au [2.0 API Endpoints guide](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/) .

Q : **Que faire si aucune réponse n’a été apportée à ma question dans cette FAQ ?**

R : Si vous avez encore des questions, contactez le représentant de votre compte d’Adobe.

