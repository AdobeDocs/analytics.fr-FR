---
title: Profils de produit pour Adobe Analytics
description: Découvrez comment les profils de produit peuvent être utilisés comme paramètres d’autorisation prédéfinis que les administrateurs des produits peuvent attribuer aux utilisateurs d’une organisation.
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
feature: Admin Tools
role: Admin
source-git-commit: ed7b25491de5c1238e846997ec903df4fd4ee18c
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 65%

---

# Profils de produit pour Adobe Analytics

Les profils de produit sont des paramètres dʼautorisation prédéfinis que les administrateurs des produits peuvent attribuer aux utilisateurs dʼune organisation. Si vous créez un profil de produit et que vous lui affectez un utilisateur Experience Cloud, il hérite des éléments d’autorisation contenus dans le profil de produit.

Pour obtenir des informations générales sur les profils de produit, notamment la création de profils de produit et l’affectation d’utilisateurs, consultez [Gérer les profils de produit pour les utilisateurs d’entreprise](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) dans le guide d’utilisation Enterprise.

## Administrateurs de profil de produit

Les administrateurs de profil de produit sont un groupe facultatif qui peut ajouter des utilisateurs à ce profil de produit ou en supprimer. Notez qu’un administrateur de profil de produit n’est pas identique à un administrateur de produit :

* Les administrateurs de profil de produit ne disposent pas d’un accès complet à Adobe Analytics. L’accès complet à Adobe Analytics est réservé aux administrateurs de produit.
* Les administrateurs de profil de produit ne peuvent pas ajuster les éléments d’autorisations dans leur profil de produit.
* Les administrateurs des profils de produit peuvent affecter des profils de produit à des groupes d’utilisateurs ou en supprimer.
* Les administrateurs des profils de produit sont parfaits pour les chefs dʼéquipe ou les managers qui doivent octroyer et gérer lʼaccès à Adobe Analytics pour leur équipe. Les utilisateurs n’ont pas besoin de demander aux administrateurs système ou aux administrateurs de produit de leur octroyer l’accès à Adobe Analytics.

Pour plus d’informations sur l’affectation des administrateurs de profil de produit, consultez la section « Gérer les administrateurs de profil de produit » de l’article [Gérer les profils de produit pour les utilisateurs d’entreprise](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) dans le guide d’utilisation Enterprise.

## Éléments d’autorisation Adobe Analytics

Les autorisations minimales requises dans un seul profil de produit pour accéder à Adobe Analytics sont les suivantes :

* Le profil de produit doit avoir accès à au moins une suite de rapports.
* Le profil de produit doit appartenir à l’élément d’autorisation Outils Analytics **Accès Analysis Workspace**.

### Suites de rapports

Accorde l’accès aux suites de rapports qui appartiennent à votre organisation Analytics. Un utilisateur doit appartenir à au moins une suite de rapports pour recevoir un accès à Adobe Analytics.

### Mesures

Accorde l’accès aux mesures de votre suite de rapports. Les mesures sont répertoriées comme leur composant respectif dans Analysis Workspace.

Les mesures personnalisées sont étiquetées « Événements personnalisés 1-1 000 » afin de rester indépendantes des suites de rapports. Si « Événement personnalisé 1 » est un élément d’autorisation activé, cet utilisateur a accès à événement1 dans toutes les suites de rapports du profil de produit.

### Dimensions

Accorde l’accès aux dimensions de votre suite de rapports. Les dimensions sont répertoriées comme leurs composants respectifs dans Analysis Workspace.

Les variables personnalisées, telles que les eVars, sont étiquetées « Conversions personnalisées 1-250 » afin de rester indépendantes des suites de rapports. Si « Conversion personnalisée 1 » est un élément d’autorisation activé, cet utilisateur a accès à eVar1 dans toutes les suites de rapports du profil de produit.

### Outils de suites de rapports

Les éléments d’autorisation liés aux outils de suites de rapports octroient l’accès aux fonctionnalités spécifiques aux suites de rapports auxquelles l’utilisateur a accès. Pour obtenir la liste complète des descriptions et des éléments d’autorisation, reportez-vous à la section [Outils de suite de rapports](report-suite-tools.md).

### Outils Analytics

Les éléments d’autorisation liés aux outils Analytics octroient l’accès à des fonctionnalités indépendantes des paramètres de suite de rapports. Reportez-vous aux [Autorisations du profil de produit pour les outils Analytics](analytics-tools.md) afin dʼobtenir la liste complète des éléments et des descriptions dʼautorisation.

## Développeurs de profil de produit

Les développeurs sont similaires aux utilisateurs, à la différence qu’ils peuvent utiliser l’API Experience Cloud sur Adobe Developer. Consultez [Gérer les développeurs](https://helpx.adobe.com/fr/enterprise/using/manage-developers.html) dans le guide d’utilisation Enterprise pour plus d’informations. Si l’utilisateur se voit accorder l’accès développeur pour n’importe quel profil, il peut accéder à la console de développement (console.adobe.io) et modifier les intégrations Adobe Analytics. Les appels et réponses de l’API Analytics autorisés pour l’utilisateur dépendent des autorisations réseau de tous les profils auxquels l’utilisateur a accès en tant que développeur.

Par exemple, avec les autorisations de profil qui incluent toutes les mesures, toutes les dimensions et une suite de rapports, un développeur peut effectuer des appels API pertinents à n’importe quel composant de cette suite de rapports. Si l’élément d’autorisation Détection des anomalies est ajouté, les réponses de l’API peuvent inclure des données d’anomalies. En règle générale, si un profil accorde l’accès à un scénario dans l’interface d’Adobe Analytics, l’accès développeur à un profil défini de manière similaire active les appels et réponses d’API correspondants.
