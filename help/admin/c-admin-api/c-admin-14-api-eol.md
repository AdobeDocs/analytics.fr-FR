---
description: Détails de l’annonce de fin de vie de l’API Adobe Analytics 1.4.
title: Questions fréquentes sur la fin de vie des API Adobe Analytics 1.4
feature: Admin Tools
role: Admin
exl-id: 88769032-a7cd-4ca8-958f-3300a4bfe71f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 4%

---

# Questions fréquentes sur la fin de vie des API Adobe Analytics 1.4

Adobe prévoit de supprimer l’API Adobe Analytics 1.4 le **12 août 2026**. Ils ne seront plus accessibles après cette date. Cette annonce a une incidence directe sur les éléments suivants :

* API Adobe Analytics 1.4, à l’exclusion de l’API Data Insertion
* Authentification WSSE Adobe Analytics

## API 1.4

Les API [Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/) fournissent un large éventail d’actions, telles que la création de rapports, les classifications, les flux de données et les configurations de suites de rapports. Leur expiration est remplacée par celle des [API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/). Les API 2.0 vous permettent d’effectuer pratiquement toutes les actions réalisables dans l’interface utilisateur d’Analytics, comme créer des rapports ou gérer des composants tels que des segments et des mesures calculées.

Adobe propose un [chemin de migration](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) aux utilisateurs d’API 1.4. Vous pouvez migrer vos intégrations vers les API 2.0 (les mêmes API dont dépend l’application Adobe Analytics) et tirer parti des dernières fonctionnalités. Toutes les fonctionnalités disponibles dans les API 1.4 peuvent être accomplies à l’aide des API [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Authentification WSSE

L’authentification WSSE est un protocole d’authentification hérité pris en charge par les API Analytics 1.4. Il a été remplacé par les options d’authentification basées sur OAuth fournies dans [Adobe Developer Console](https://developer.adobe.com/console/home). Les projets qui utilisent l’authentification WSSE doivent mettre à jour leurs informations d’identification sur celles configurées dans Adobe Developer Console. Pour ce faire, connectez-vous à [Adobe Developer Console](https://developer.adobe.com/console/home) afin de créer un projet pour votre intégration de l’API Analytics 2.0. Sélectionnez la méthode d’authentification Utilisateur OAuth ou Serveur à serveur OAuth .

## FAQ

+++**Cela a-t-il un impact sur mes projets Adobe IO existants pour les API Analytics ?**

Tous les projets existants utilisant les API Analytics 1.4 sont affectés. Ces intégrations doivent être migrées vers les API [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) avant l’échéance de fin de vie.

+++

+++**J’ai partagé mes informations d’identification Adobe avec un autre produit ou une autre application qui utilise les API Analytics. Cela les concerne-t-il ?**

Si ce produit ou cette application utilise vos informations d’identification WSSE et/ou appelle les API Analytics 1.4, ils sont affectés et doivent migrer avant l’échéance de fin de vie. Contactez le fournisseur du produit ou de l’application pour obtenir plus d’informations sur ses plans de migration et son calendrier.

+++

+++**Comment puis-je déterminer l’API utilisée par mon projet ?**

L’URL de base que l’API appelle détermine la version d’API utilisée par votre projet. Les API Adobe Analytics 1.4 utilisent les URL suivantes :
* `https://api.omniture.com`
* `https://api3.omniture.com`
* `https://api4.omniture.com`
* `https://api5.omniture.com`

Les API [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) utilisent l’URL suivante :

* `https://analytics.adobe.io`

Si l’un de vos projets d’API utilise `api*.omniture.com`, il utilise les API Adobe Analytics 1.4 et doit migrer vers les API 2.0.

+++

+++**Cette fin de vie a-t-elle une incidence sur la collecte de données ?**

La fin de vie d’Adobe Analytics 1.4 n’a aucune incidence sur vos solutions de balisage, telles que les balises (anciennement Adobe Launch), Web SDK ou AppMeasurement. Cependant, si vous utilisez les API Data Sources ou Classifications de la version 1.4 pour améliorer vos données, vous devez migrer ces workflows vers les API Adobe Analytics 2.0.

L’API Data Insertion n’est pas affectée par cette annonce de fin de vie. Alors qu’Adobe prévoit de continuer à prendre en charge l’API Data Insertion, Adobe recommande d’utiliser plutôt l’[API Bulk Data Insertion](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).

+++

Si vous avez d’autres questions sur cette annonce de fin de vie auxquelles aucune réponse ne figure sur cette page, contactez l’équipe chargée de votre compte Adobe.
