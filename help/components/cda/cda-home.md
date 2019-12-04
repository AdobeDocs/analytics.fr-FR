---
title: Analyses entre appareils
description: Les analyses entre appareils font en sorte que vos données ne soient plus axées sur l’appareil, mais plutôt sur la personne, en regroupant les données de l’appareil.
translation-type: tm+mt
source-git-commit: c358df811f23a57441e6f9410c957e34954de712

---


# Analyses entre appareils

> [!NOTE] La documentation des analyses entre appareils peut être modifiée au fur et à mesure que la fonctionnalité est développée. Consultez régulièrement les mises à jour.

Les analyses entre appareils sont une fonctionnalité qui transforme les analyses, en passant d’une vue axée sur l’appareil à une vue axée sur la personne. Cette fonctionnalité utilise le graphique Co-op ou Privé du service d’identité d’Adobe Experience Platform pour ainsi identifier les appareils appartenant à des personnes et les regrouper. Dès lors, les analystes peuvent comprendre le comportement des utilisateurs qui s’étend sur plusieurs navigateurs, appareils ou applications. Grâce à CDA, vous pouvez répondre à des questions telles que :

* Combien de personnes interagissent avec ma marque ? Combien de types de périphériques utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un périphérique mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne amenant à un périphérique conduisent-ils à une conversion ailleurs ?
* Comment ma compréhension de l’efficacité de la campagne change-t-elle si je prends en compte les trajets entre plusieurs périphériques ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un périphérique à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs périphériques diffère-t-il de celui des utilisateurs disposant d’un seul périphérique ?

Lorsque des périphériques sont regroupés, la persistance de variable est réalisée sur plusieurs périphériques. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur trouve votre application mobile, l’installe et effectue un achat sur son périphérique mobile. Grâce aux analyses entre appareils, les recettes peuvent être attribuées à la publicité sur laquelle il a cliqué sur son ordinateur de bureau.

Voir [Journey IQ : page de lancement des analyses entre appareils](http://adobe.ly/aacda) pour en savoir plus sur les capacités et les fonctionnalités des analyses entre appareils.

## Conditions préalables

Depuis septembre 2019, les analyses entre appareils imposent les conditions suivantes. Collaborez avec les équipes de votre entreprise et votre gestionnaire de compte Adobe pour vous assurer que vous remplissez toutes les conditions suivantes.

> [!IMPORTANT] Si vous ne remplissez pas toutes les conditions préalables requises, vous risquez de ne pas pouvoir activer les analyses entre appareils ou de ne pas obtenir de résultats satisfaisants lors du regroupement de données.

* Les données de votre entreprise doivent se trouver dans le centre de données du Nord-Ouest du Pacifique d’Adobe. La prise en charge de centres de données dans d’autres régions du monde est prévue.
* Contactez le gestionnaire de compte de votre entreprise pour déterminer les points clés suivants :
   * Un contrat doit être signé avec Adobe et inclure Adobe Analytics Ultimate.
   * Votre entreprise doit utiliser le graphique Co-op ou Privé du service d’identité d’Adobe Experience Platform. Consultez la [page d’accueil](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) du guide de l’utilisateur Device Co-op.
   * Votre entreprise doit accepter qu’Adobe puisse traiter et stocker des données Analytics sur des serveurs Microsoft Azure. Adobe utilise Azure pour stocker les données graphiques des appareils et effectuer leur regroupement. Ainsi, les données Adobe Analytics sont échangées entre le centre de traitement des données d’Adobe et la présence d’Adobe dans Microsoft Azure.
* Les analyses entre appareils sont activées sur base des suites de rapports. Les suites de rapports qui ont été activées pour les analyses entre appareils exigent ce qui suit :
   * La suite de rapports ne peut pas contenir plus de 100 millions d’accès par jour. Ce seuil augmentera au cours des prochains mois.
   * Adobe recommande qu’une suite de rapports contienne des données interpériphériques, ce qui signifie qu’elles proviennent de plusieurs types d’appareils (web, applications, etc.). Certaines entreprises considèrent ce concept comme une suite de rapports « globale », bien que les analyses entre appareils ne doivent pas nécessairement être globales du point de vue géographique. Les analyses entre appareils ne fonctionnent pas entre les suites de rapports et ne combinent pas non plus les données de plusieurs suites de rapports.
* Votre mise en œuvre doit satisfaire aux exigences suivantes :
   * La dernière version du service Experience Cloud ID doit être déployée. Consultez la [page d’accueil](https://docs.adobe.com/content/help/en/id-service/using/home.html) du guide de l’utilisateur du service d’identité d’Experience Cloud. La plupart des implémentations utilisant Adobe Experience Platform Launch disposent déjà probablement d’un ECID déployé.
   * Appelez la fonction `setCustomerIDs` chaque fois qu’une personne peut être identifiée, par exemple lorsqu’un utilisateur se connecte ou ouvre un courrier électronique. Cette exigence s’applique à toutes les plates-formes, y compris les applications mobiles si elles sont utilisées. Voir [setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) dans le guide de l’utilisateur du service d’identité d’Experience Cloud.

## Limites

Les analyses entre appareils sont une fonctionnalité innovante et robuste, mais leur utilisation a ses limites.

* Les analyses entre appareils sont uniquement disponibles dans Analysis Workspace.
* Le regroupement ne peut pas se produire entre les suites de rapports, comme décrit dans les conditions préalables ci-dessus.
* Les suites de rapports Adobe Analytics ne peuvent pas mapper à plusieurs organisations IMS. Étant donné que les analyses entre appareils regroupent des appareils dans une suite de rapports donnée, il est impossible de les utiliser pour regrouper des données entre plusieurs organisations IMS.
* Les analyses entre appareils ne sont actuellement pas compatibles avec les attributs du client. Les attributs du client ne peuvent pas être utilisés pour créer une suite de rapports virtuelle d’analyses entre appareils, dans des segments interpériphériques, ou pour la création de rapports dans un projet Analysis Workspace basé sur une suite de rapports virtuelle d’analyses entre appareils.
   > [!TIP] Bien que les attributs du client ne puissent pas être utilisés dans CDA, les deux fonctionnalités dépendent de la `setCustomerIDs` fonction. Ces deux fonctionnalités peuvent coïncider dans des suites de rapports distinctes (virtuelles).
* L'ADC a besoin du graphique coopératif ou du graphique privé. Les graphiques d’appareils tiers ne sont pas pris en charge.
* Les identifiants Analytics hérités ne sont pas pris en charge. Seuls les visiteurs avec un Experience Cloud ID sont regroupés.
* L’assistance clientèle ne prend pas encore entièrement en charge cette fonctionnalité. Le forum [Analyses entre appareils](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) peut être utilisé pour la prise en charge de cette fonctionnalité, qui inclut une participation active et directe des responsables produits Adobe.
* Les analyses entre appareils utilisent une suite de rapports virtuelle et le traitement du temps de la période de rapport, qui ont leurs propres limites. Voir [Suites de rapports virtuelles](../vrs/vrs-about.md) et [traitement de la période de rapport](../vrs/vrs-report-time-processing.md) pour en savoir plus sur ces limitations.
* L’API 1.4 n’est pas prise en charge. Les connecteurs Power BI et le créateur de rapports reposent tous deux sur l’API 1.4 et ne sont donc pas compatibles avec CDA.
* Les nouveaux appareils qui visitent votre site peuvent prendre jusqu’à deux semaines pour être traités par le graphique Co-op ou Privé. Le niveau de groupement dans les analyses entre appareils pour les deux dernières semaines est généralement inférieur à celui des plages de dates datant de plus de deux semaines. Adobe prévoit d’améliorer le service d’identité d’Adobe Experience Platform afin de regrouper de nouveaux périphériques en temps réel à l’avenir.
* Les données historiques de la suite de rapports virtuelle changent en fonction de la reconnaissance par Adobe des périphériques et de leur regroupement. Les données de la suite de rapports source ne changent pas.

Une fois que toutes les conditions requises sont remplies et que vous avez compris les limites, vous pouvez commencer à [configurer Analytics sur plusieurs appareils](cda-setup.md).
