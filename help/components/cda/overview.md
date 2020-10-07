---
title: Analyses entre appareils
description: Modifiez vos données pour passer des données axées sur les appareils aux données axées sur les personnes en regroupant les données des appareils.
translation-type: tm+mt
source-git-commit: 954927359420cfdb3d0e908758fc36464e15fee5
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 98%

---


# Analyses entre appareils

Les analyses entre appareils sont une fonctionnalité qui transforme les analyses, en passant d’une vue axée sur l’appareil à une vue axée sur la personne. Dès lors, les analystes peuvent comprendre le comportement des utilisateurs qui s’étend sur plusieurs navigateurs, appareils ou applications. Adobe prend en charge deux workflows globaux pour lier les données des appareils :

* [**Groupement basé sur les champs**](field-based-stitching.md) : permet de choisir une variable Analytics comme base pour le groupement entre appareils dans une suite de rapports virtuelle. Utilise une correspondance déterministe pour relier les appareils. Adobe recommande l’utilisation d’un groupement basé sur les champs pour la plupart des cas d’utilisation de correspondance déterministe.
* [**Graphique d’appareil**](device-graph.md) : les analyses entre appareils communiquent avec un graphique d’appareil pour regrouper les appareils. Le graphique coopératif utilise à la fois une correspondance déterministe et probabiliste.

Les analyses entre appareils vous permettent de répondre à des questions telles que :

* Combien de personnes interagissent avec ma marque ? Combien de types de périphériques utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un périphérique mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne amenant à un périphérique conduisent-ils à une conversion ailleurs ?
* Comment ma compréhension de l’efficacité de la campagne change-t-elle si je prends en compte les trajets entre plusieurs périphériques ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un périphérique à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs périphériques diffère-t-il de celui des utilisateurs disposant d’un seul périphérique ?

Lorsque des périphériques sont regroupés, la persistance de variable est réalisée sur plusieurs périphériques. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur trouve votre application mobile, l’installe et effectue un achat sur son périphérique mobile. Grâce aux analyses entre appareils, les recettes peuvent être attribuées à la publicité sur laquelle il a cliqué sur son ordinateur de bureau.

Dans un souci de partenariat et de transparence, nous voulons que nos clients soient conscients de notre utilisation de Microsoft Azure en association avec les analyses entre appareils. Adobe utilise Azure pour stocker les données graphiques des appareils et effectuer le regroupement entre appareils. Ainsi, les données Adobe Analytics sont échangées entre le centre de traitement des données d’Adobe et les instances configurées d’Adobe dans Microsoft Azure.

Voir [Journey IQ : page de lancement des analyses entre appareils](http://adobe.ly/aacda) pour en savoir plus sur les capacités et les fonctionnalités des analyses entre appareils.

## Conditions préalables

L’utilisation des analyses entre appareils requiert tous les éléments suivants. Les méthodes [Groupement basé sur les champs](field-based-stitching.md) et [Graphique d’appareil](device-graph.md) comportent également leurs propres conditions préalables.

* Un contrat doit être signé avec Adobe et inclure Adobe Analytics Ultimate.
* Les analyses entre appareils sont activées sur base des suites de rapports. Adobe recommande une suite de rapports contenant des données interpériphériques, ce qui signifie qu’elles proviennent de plusieurs types d’appareils (Web, applications, etc.). Certaines entreprises considèrent ce concept comme une suite de rapports « globale », bien que les analyses entre appareils ne doivent pas nécessairement être globales du point de vue géographique.

## Limites

Les analyses entre appareils sont une fonctionnalité innovante et robuste, mais leur utilisation a ses limites. Les méthodes [Groupement basé sur les champs](field-based-stitching.md) et [Graphique d’appareil](device-graph.md) présentent également leurs propres limites.

* Les analyses entre appareils sont uniquement disponibles dans Analysis Workspace.
* Les analyses entre appareils ne fonctionnent pas entre les suites de rapports et ne combinent pas non plus les données de plusieurs suites de rapports.
* Les suites de rapports Adobe Analytics ne peuvent pas mapper à plusieurs organisations IMS. Étant donné que les analyses entre appareils regroupent des appareils dans une suite de rapports donnée, il est impossible de les utiliser pour regrouper des données entre plusieurs organisations IMS.
* Les analyses entre appareils ne sont actuellement pas compatibles avec les attributs du client. Ces deux fonctionnalités peuvent coïncider dans des suites de rapports virtuelles distinctes qui référencent la même suite de rapports source.
* Les analyses entre appareils utilisent une suite de rapports virtuelle et le traitement du temps de la période de rapport, qui ont leurs propres limites. Voir [Suites de rapports virtuelles](../vrs/vrs-about.md) et [traitement de la période de rapport](../vrs/vrs-report-time-processing.md) pour en savoir plus sur ces limitations.
* L’API 1.4 n’est pas prise en charge. Les connecteurs Power BI et le Report Builder reposent tous les deux sur l’API 1.4 et ne sont donc pas compatibles avec les analyses entre appareils.
* Les données historiques de la suite de rapports virtuelle changent en fonction de la reconnaissance par Adobe des périphériques et de leur regroupement. Les données de la suite de rapports source ne changent pas.
