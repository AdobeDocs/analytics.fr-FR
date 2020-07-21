---
title: Analyses entre appareils
description: Remplacez vos données par des données axées sur le périphérique par des données axées sur la personne en regroupant les données du périphérique.
translation-type: tm+mt
source-git-commit: eb2bee26dd58dcff13b4ddf41c6f6ab337d8d374
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 72%

---


# Analyses entre appareils

Les analyses entre appareils sont une fonctionnalité qui transforme les analyses, en passant d’une vue axée sur l’appareil à une vue axée sur la personne. Dès lors, les analystes peuvent comprendre le comportement des utilisateurs qui s’étend sur plusieurs navigateurs, appareils ou applications. Adobe prend en charge deux workflows généraux pour associer les données des périphériques :

* [**Raccord **](field-based-stitching.md)basé sur les champs : Permet de choisir une variable Analytics comme base pour l’assemblage sur plusieurs périphériques dans une suite de rapports virtuelle. Utilise une correspondance déterministe pour relier les périphériques. Adobe recommande l’utilisation d’un assemblage basé sur les champs pour la plupart des cas d’utilisation de correspondance déterministes.
* [**Graphique **](device-graph.md)du périphérique : CDA communique avec un graphique de périphérique pour assembler les périphériques. Le graphique coopératif utilise une correspondance déterministe et probablistique.

L&#39;ADC vous permet de répondre à des questions telles que :

* Combien de personnes interagissent avec ma marque ? Combien de types de périphériques utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un périphérique mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne amenant à un périphérique conduisent-ils à une conversion ailleurs ?
* Comment ma compréhension de l’efficacité de la campagne change-t-elle si je prends en compte les trajets entre plusieurs périphériques ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un périphérique à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs périphériques diffère-t-il de celui des utilisateurs disposant d’un seul périphérique ?

Lorsque des périphériques sont regroupés, la persistance de variable est réalisée sur plusieurs périphériques. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur trouve votre application mobile, l’installe et effectue un achat sur son périphérique mobile. Grâce aux analyses entre appareils, les recettes peuvent être attribuées à la publicité sur laquelle il a cliqué sur son ordinateur de bureau.

Dans un souci de partenariat et de transparence, nous voulons que nos clients soient conscients de notre utilisation de Microsoft Azure en association avec les analyses entre appareils. Adobe utilise Azure pour stocker les données graphiques des appareils et effectuer le regroupement entre appareils. Ainsi, les données Adobe Analytics sont échangées entre le centre de traitement des données d’Adobe et les instances configurées d’Adobe dans Microsoft Azure.

See the [Journey IQ: Cross-Device Analytics Spark page](http://adobe.ly/aacda) to learn more about the capabilities and features of Cross-Device Analytics.

## Conditions préalables

L&#39;utilisation de l&#39;ADC exige tous les éléments suivants. [Les méthodes d’assemblage](field-based-stitching.md) basé sur les champs et les méthodes de graphique [](device-graph.md) de périphérique comportent également leurs propres conditions préalables.

* Un contrat doit être signé avec Adobe et inclure Adobe Analytics Ultimate.
* Les analyses entre appareils sont activées sur base des suites de rapports. Adobe recommande une suite de rapports contenant des données sur plusieurs périphériques, c’est-à-dire des données provenant de plusieurs types d’appareils (Web, application, etc.). Certaines entreprises considèrent ce concept comme une suite de rapports « globale », bien que les analyses entre appareils ne doivent pas nécessairement être globales du point de vue géographique.

## Limites

Les analyses entre appareils sont une fonctionnalité innovante et robuste, mais leur utilisation a ses limites. [Les méthodes d’assemblage](field-based-stitching.md) basées sur les champs et les méthodes de graphique [](device-graph.md) de périphérique présentent également leurs propres limites.

* Les analyses entre appareils sont uniquement disponibles dans Analysis Workspace.
* Les analyses entre appareils ne fonctionnent pas entre les suites de rapports et ne combinent pas non plus les données de plusieurs suites de rapports.
* Les suites de rapports Adobe Analytics ne peuvent pas mapper à plusieurs organisations IMS. Étant donné que les analyses entre appareils regroupent des appareils dans une suite de rapports donnée, il est impossible de les utiliser pour regrouper des données entre plusieurs organisations IMS.
* Les analyses entre appareils ne sont actuellement pas compatibles avec les attributs du client. Ces deux fonctionnalités peuvent coïncider dans des suites de rapports virtuelles distinctes qui référencent la même suite de rapports source.
* Les analyses entre appareils utilisent une suite de rapports virtuelle et le traitement du temps de la période de rapport, qui ont leurs propres limites. Voir [Suites de rapports virtuelles](../vrs/vrs-about.md) et [traitement de la période de rapport](../vrs/vrs-report-time-processing.md) pour en savoir plus sur ces limitations.
* L’API 1.4 n’est pas prise en charge. Les connecteurs Power BI et le Report Builder reposent tous les deux sur l’API 1.4 et ne sont donc pas compatibles avec les analyses entre appareils.
* Les données historiques de la suite de rapports virtuelle changent en fonction de la reconnaissance par Adobe des périphériques et de leur regroupement. Les données de la suite de rapports source ne changent pas.
