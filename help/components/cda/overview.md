---
title: Analyses entre appareils
description: Découvrez comment remplacer vos données axées sur l’appareil par des données axées sur la personne en assemblant les données de l’appareil.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 59%

---

# Analyses entre appareils

{{available-existing-customers}}

Analytics sur l’ensemble des appareils (CDA) est une fonctionnalité qui transforme Analytics, en passant d’une vue centrée sur l’appareil à une vue centrée sur la personne. Dès lors, les analystes peuvent comprendre le comportement des utilisateurs qui s’étend sur plusieurs navigateurs, appareils ou applications. Adobe prend en charge deux workflows globaux pour lier les données des appareils :

* [**Groupement basé sur les champs**](field-based-stitching.md) : option de regroupement recommandée, car elle utilise uniquement une correspondance déterministe pour relier les appareils.
Le groupement basé sur les champs vous permet de choisir une variable Analytics comme base pour le groupement entre appareils dans une suite de rapports virtuelle.

* [**Graphique d’appareil**](device-graph.md) : Analytics sur l’ensemble des appareils communique avec un graphique privé pour regrouper les appareils.

Les analyses entre appareils vous permettent de répondre à des questions telles que :

* Combien de personnes interagissent avec ma marque ? Combien de types d’appareils utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un appareil mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne amenant à un appareil conduisent-ils à une conversion ailleurs ?
* Comment ma compréhension de l’efficacité de la campagne change-t-elle si je prends en compte les trajets entre plusieurs appareils ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un appareil à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs appareils diffère-t-il de celui des utilisateurs disposant d’un seul appareil ?

Lorsque des appareils sont regroupés, la persistance de variable est réalisée sur plusieurs appareils. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur trouve votre application mobile, l’installe et effectue un achat sur son appareil mobile. Grâce aux analyses entre appareils, le chiffre d’affaires de l’appareil mobile peut être attribué à l’annonce publicitaire sur laquelle un clic a été effectué sur le poste de travail.

Microsoft Azure est utilisé pour les analyses entre appareils. Adobe utilise Azure pour stocker les données graphiques des appareils et effectuer le regroupement entre appareils. Ainsi, les données Adobe Analytics sont transmises entre le centre de traitement des données d’Adobe et les instances configurées d’Adobe de Microsoft Azure.

Consultez la [page Spark d’analyses entre appareils](https://express.adobe.com/page/8ZpjsX6Lp5XTM/) pour en savoir plus sur les fonctionnalités d’Analytics sur l’ensemble des appareils.

## Conditions préalables

L’utilisation d’Analytics sur l’ensemble des appareils nécessite des méthodes [Assemblage basé sur les champs](field-based-stitching.md) et [graphique d’appareil](device-graph.md) et toutes deux ont leurs propres conditions préalables spécifiques.

* Un contrat doit être signé avec Adobe et inclure Adobe Analytics Ultimate.
* Votre entreprise choisit les suites de rapports à activer pour CDA. Adobe recommande les suites de rapports qui contiennent des données multi-appareils, c’est-à-dire des données provenant de plusieurs types d’appareils/navigateurs/applications. Certaines organisations font référence à ce concept en tant que suite de rapports « globale », bien qu’il ne soit pas obligatoire que les analyses entre appareils soient globales d’un point de vue géographique.

## Limites

Les analyses entre appareils sont une fonctionnalité innovante et robuste, mais leur utilisation a ses limites. Les méthodes [Groupement basé sur les champs](field-based-stitching.md) et [Graphique d’appareil](device-graph.md) présentent également leurs propres limites.

* Les analyses entre appareils ne sont disponibles que via Analysis Workspace.
* Les analyses entre appareils ne fonctionnent pas entre les suites de rapports et ne combinent pas non plus les données de plusieurs suites de rapports.
* Les suites de rapports d’Adobe Analytics ne peuvent pas mapper plus d’une ID d’organisation. Comme Analytics sur l’ensemble des appareils regroupe des appareils dans une suite de rapports donnée, il n’est pas possible d’utiliser Analytics sur l’ensemble des appareils pour regrouper des données sur plusieurs ID d’organisation.
* Les analyses entre appareils utilisent un pipeline de traitement complexe, avec plusieurs composants dépendants. Ce pipeline s’exécute en parallèle du workflow de création de rapports Analytics de base. Vous pouvez vous attendre à une incohérence des données d’environ 1 % pour le nombre total d’accès entre la suite de rapports d’origine et la suite de rapports virtuelle Analytics sur l’ensemble des appareils.
* Les analyses entre appareils utilisent une suite de rapport virtuelle et untraitement du temps de la période de rapport, qui ont leurs propres limites. Par exemple, ils ne prennent actuellement pas en charge les variables de canaux marketing. Voir [Suites de rapports virtuelles](/help/components/vrs/vrs-about.md) et [Traitement de la période de rapport](/help/components/vrs/vrs-report-time-processing.md) pour en savoir plus sur ces limitations.
* Private Graph utilise les mêmes synchronisations d’identifiants que celles utilisées par la fonctionnalité [Attributs du client](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) dans Experience Cloud et Adobe Analytics. Cependant, les suites de rapports virtuelles Analytics sur l’ensemble des appareils (qu’elles soient basées sur un graphique privé ou sur un groupement basé sur les champs) ne sont pas compatibles avec le reste de la fonctionnalité Attributs du client. En d’autres termes, les dimensions basées sur les attributs du client ne sont pas disponibles pour être utilisées avec les suites de rapports virtuelles Analytics sur l’ensemble des appareils.
* Les analyses entre appareils ne sont actuellement pas compatibles avec A4T.
* L’API 1.4 n’est pas prise en charge. Les connecteurs Power BI et le Report Builder reposent tous les deux sur l’API 1.4 et ne sont donc pas compatibles avec les analyses entre appareils.
* La surveillance active par Adobe du processus d’assemblage des analyses entre appareils se limite uniquement aux suites de rapports de production.
* Les analyses entre appareils ne sont actuellement pas compatibles avec l’API [Data Repair](https://developer.adobe.com/analytics-apis/docs/2.0/?lang=fr) Adobe Analytics
* Les données historiques de la suite de rapports virtuelle changent en fonction de la reconnaissance par Adobe des appareils et de leur regroupement. Les données de la suite de rapports source ne changent pas.
* Les données regroupées affichent une latence comprise entre 8 et 12 heures.
* Les données d’historique de mappage pour un appareil donné sont stockées pendant un an au maximum.
* Si un appareil atteint un nombre très élevé d’entrées d’historique de mappage au cours d’une année, l’historique de mappage est tronqué. La limite exacte dépend de l’option de groupement utilisée.
