---
title: Analyses entre appareils
description: Modifiez vos données pour passer des données axées sur les appareils aux données axées sur les personnes en regroupant les données des appareils.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
source-git-commit: aa4550d7012f76571f7623428d3d4ee08f728f64
workflow-type: ht
source-wordcount: '883'
ht-degree: 100%

---

# Analyses entre appareils

Les analyses entre appareils sont une fonctionnalité qui transforme les analyses, en passant d’une vue axée sur l’appareil à une vue axée sur la personne. Dès lors, les analystes peuvent comprendre le comportement des utilisateurs qui s’étend sur plusieurs navigateurs, appareils ou applications. Adobe prend en charge deux workflows globaux pour lier les données des appareils :

* [**Groupement basé sur les champs**](field-based-stitching.md) : option de regroupement recommandée, car elle utilise uniquement une correspondance déterministe pour relier les appareils.
Vous permet de choisir une variable Analytics comme base pour le groupement entre appareils dans une suite de rapports virtuelle.
* [**Graphique d’appareil**](device-graph.md) : les analyses entre appareils communiquent avec un graphique d’appareil pour regrouper les appareils. Le graphique Co-op utilise une correspondance déterministe et probabiliste.

>[!NOTE]
>
>Pour en savoir plus sur la [fin de vie de Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/about/device-co-op-eol.html?lang=fr).

Les analyses entre appareils vous permettent de répondre à des questions telles que :

* Combien de personnes interagissent avec ma marque ? Combien de types de périphériques utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un périphérique mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne amenant à un périphérique conduisent-ils à une conversion ailleurs ?
* Comment ma compréhension de l’efficacité de la campagne change-t-elle si je prends en compte les trajets entre plusieurs périphériques ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un périphérique à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs périphériques diffère-t-il de celui des utilisateurs disposant d’un seul périphérique ?

Lorsque des périphériques sont regroupés, la persistance de variable est réalisée sur plusieurs périphériques. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur trouve votre application mobile, l’installe et effectue un achat sur son périphérique mobile. Grâce aux analyses entre appareils, le chiffre d’affaires de l’appareil mobile peut être attribué à l’annonce publicitaire sur laquelle un clic a été effectué sur le poste de travail.

Dans un souci de partenariat et de transparence, nous voulons que nos clients soient conscients de notre utilisation de Microsoft Azure en association avec les analyses entre appareils. Adobe utilise Azure pour stocker les données graphiques des appareils et effectuer le regroupement entre appareils. Ainsi, les données Adobe Analytics sont échangées entre le centre de traitement des données d’Adobe et les instances configurées d’Adobe dans Microsoft Azure.

Voir [Journey IQ : page de lancement des analyses entre appareils](https://adobe.ly/aacda) pour en savoir plus sur les capacités et les fonctionnalités des analyses entre appareils.

## Conditions préalables

L’utilisation des analyses entre appareils requiert tous les éléments suivants. Les méthodes [Groupement basé sur les champs](field-based-stitching.md) et [Graphique d’appareil](device-graph.md) comportent également leurs propres conditions préalables.

* Un contrat doit être signé avec Adobe et inclure Adobe Analytics Ultimate.
* Les analyses entre appareils sont activées sur base des suites de rapports. Adobe recommande une suite de rapports contenant des données interpériphériques, ce qui signifie qu’elles proviennent de plusieurs types d’appareils (Web, applications, etc.). Certaines entreprises considèrent ce concept comme une suite de rapports « globale », bien que les analyses entre appareils ne doivent pas nécessairement être globales du point de vue géographique.

## Limites

Les analyses entre appareils sont une fonctionnalité innovante et robuste, mais leur utilisation a ses limites. Les méthodes [Groupement basé sur les champs](field-based-stitching.md) et [Graphique d’appareil](device-graph.md) présentent également leurs propres limites.

* Les analyses entre appareils sont uniquement disponibles dans Analysis Workspace.
* Les analyses entre appareils ne fonctionnent pas entre les suites de rapports et ne combinent pas non plus les données de plusieurs suites de rapports.
* Les suites de rapports d’Adobe Analytics ne peuvent pas mapper plus d’une ID d’organisation. Étant donné que CDA regroupe des appareils dans une suite de rapports donnée, vous ne pouvez pas l’utiliser pour regrouper des données entre plusieurs ID d’organisation.
* L’analyse entre appareils utilise un pipeline de traitement complexe, incorporant plusieurs composants dépendants. Cette opération s’exécute en parallèle du workflow de rapports Analytics de base. Il faut donc s’attendre à une discordance de données d’environ 1 % pour le nombre total d’accès entre la suite de rapports d’origine et la suite de rapports virtuelle des analyses entre appareils.
* Les analyses entre appareils utilisent une suite de rapport virtuelle et untraitement du temps de la période de rapport, qui ont leurs propres limites. Par exemple, ils ne prennent actuellement pas en charge les variables de canaux marketing. Voir [Suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=fr) et [Traitement de la période de rapport](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=fr) pour en savoir plus sur ces limitations.
* Private Graph utilise les mêmes synchronisations d’identifiants que celles utilisées par la fonctionnalité [Attributs du client](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=fr) dans Experience Cloud et Adobe Analytics. Cependant, les suites de rapports virtuelles des analyses entre appareils (qu’elles soient basées sur Private Graph ou sur un groupement basé sur les champs) ne sont pas compatibles avec le reste de la fonctionnalité Attributs du client. En d’autres termes, les dimensions basées sur les attributs du client ne sont pas disponibles pour être utilisées avec les suites de rapports virtuelles des analyses entre appareils.
* Pour le moment, les analyses entre appareils ne sont pas compatibles avec A4T.
* L’API 1.4 n’est pas prise en charge. Les connecteurs Power BI et le Report Builder reposent tous les deux sur l’API 1.4 et ne sont donc pas compatibles avec les analyses entre appareils.
* La surveillance active par Adobe du processus d’assemblage des analyses entre appareils se limite uniquement aux suites de rapports de production.
* Les analyses entre appareils ne sont actuellement pas compatibles avec l’[API Data Repair](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/data-repair.md) d’Adobe Analytics.
* Les données historiques de la suite de rapports virtuelle changent en fonction de la reconnaissance par Adobe des périphériques et de leur regroupement. Les données de la suite de rapports source ne changent pas.
* Les données regroupées affichent une latence comprise entre 8 et 12 heures.
* Les données d’historique de mappage pour un appareil donné sont stockées pendant un an au maximum.
* Si un appareil atteint un nombre très élevé d’entrées d’historique de mappage au cours d’une année, l’historique de mappage est tronqué. La limite exacte dépend de l’option de groupement utilisée.
