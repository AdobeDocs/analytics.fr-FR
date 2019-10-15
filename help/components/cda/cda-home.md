---
title: Analyses entre appareils
description: Analytics sur plusieurs périphériques change vos données, qui ne sont plus axées sur le périphérique mais sur la personne en assemblant les données du périphérique.
translation-type: tm+mt
source-git-commit: ca79141a353dbd09176dbbe295611656262ba107

---


# Analyses entre appareils

> [!NOTE] La documentation d’Analytics sur plusieurs périphériques peut être modifiée au fur et à mesure que la fonctionnalité est développée. Consultez régulièrement les mises à jour.

Analytics sur plusieurs périphériques est une fonctionnalité qui transforme Analytics d’une vue axée sur les périphériques en une vue axée sur les personnes. Cette fonctionnalité utilise le graphique coopératif ou privé d’Adobe Experience Platform Identity Service pour identifier les périphériques appartenant à des individus et les assembler. En conséquence, les analystes peuvent comprendre le comportement des utilisateurs qui s’étend sur plusieurs navigateurs, appareils ou applications. Grâce à CDA, vous pouvez répondre à des questions telles que :

* Combien de personnes interagissent avec ma marque ? Combien de types de périphériques utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un périphérique mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne amenant à un périphérique conduisent-ils à une conversion ailleurs ?
* Comment ma compréhension de l’efficacité de la campagne change-t-elle si je prends en compte les trajets entre plusieurs périphériques ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un périphérique à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs périphériques diffère-t-il de celui des utilisateurs disposant d’un seul périphérique ?

Lorsque des périphériques sont assemblés, la persistance de variable est transférée sur plusieurs périphériques. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité sur son ordinateur de bureau. Cet utilisateur trouve votre application mobile, l’installe et effectue un achat sur son périphérique mobile. Avec Analytics sur plusieurs périphériques, les recettes peuvent être attribuées à la publicité sur laquelle ils ont cliqué sur leur ordinateur de bureau.

Voir [QI du voyage : Page](http://adobe.ly/aacda) Spark Analytics sur plusieurs périphériques pour en savoir plus sur les fonctionnalités et les fonctionnalités d’Analytics sur plusieurs périphériques.

## Conditions préalables

Depuis septembre 2019, les analyses inter-périphériques requièrent les éléments suivants. Collaborez avec les équipes de votre entreprise et votre gestionnaire de compte Adobe pour vous assurer que vous remplissez toutes les conditions suivantes.

> [!IMPORTANT] Si vous ne remplissez pas toutes les conditions préalables requises, vous risquez de ne pas pouvoir activer Analytics sur plusieurs périphériques ou de ne pas obtenir de résultats satisfaisants lors de l’assemblage de données.

* Les données de votre entreprise doivent se trouver dans le centre de données du Nord-Ouest Pacifique d’Adobe. Le soutien aux centres de données dans d'autres régions du monde est prévu.
* Contactez le gestionnaire de compte de votre entreprise pour déterminer les points clés suivants :
   * Un contrat doit être signé avec Adobe qui inclut Adobe Analytics Ultimate.
   * Votre entreprise doit utiliser le graphique Adobe Experience Platform Identity Service Co-op ou le graphique privé. Consultez la page d' [accueil](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) du guide de l'utilisateur Device Co-op.
   * Votre entreprise doit accepter de permettre à Adobe de traiter et de stocker des données Analytics sur des serveurs Microsoft Azure. Adobe utilise Azure pour stocker les données graphiques des périphériques et effectuer l’assemblage des périphériques. Ainsi, les données Adobe Analytics sont transmises entre le centre de traitement des données d’Adobe et la présence d’Adobe dans Microsoft Azure.
* Analytics sur plusieurs périphériques est activé par suite de rapports. Les suites de rapports qui ont été activées pour CDA nécessitent les éléments suivants :
   * La suite de rapports ne peut pas contenir plus de 100 millions d’accès par jour. Ce seuil augmentera au cours des prochains mois.
   * Adobe recommande qu’une suite de rapports contienne des données inter-périphériques, ce qui signifie que les données proviennent de plusieurs types d’appareils (Web, application, etc.). Certaines organisations considèrent ce concept comme une suite de rapports "globale", bien que l’ACD ne doive pas nécessairement être globale du point de vue géographique. Analytics sur plusieurs périphériques ne fonctionne pas entre les suites de rapports et ne combine pas non plus les données de plusieurs suites de rapports.
* Votre implémentation doit répondre aux exigences suivantes :
   * La dernière version du service d’ID d’Experience Cloud doit être déployée. Voir la page d’ [accueil](https://docs.adobe.com/content/help/en/id-service/using/home.html) du guide de l’utilisateur du service d’identité Experience Cloud. La plupart des implémentations utilisant Adobe Experience Platform Launch ont probablement déjà déployé ECID.
   * Appelez la `setCustomerIDs` fonction chaque fois qu’une personne peut être identifiée, par exemple lorsqu’un utilisateur se connecte ou ouvre un courrier électronique. Cette exigence s’applique à toutes les plates-formes, y compris les applications mobiles si elles sont utilisées. Voir [setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) dans le guide de l’utilisateur du service d’identité Experience Cloud.

## Limites

Les analyses multipériphériques sont une fonctionnalité innovante et robuste, mais leur utilisation est limitée.

* L’outil CDA est disponible uniquement dans Analysis Workspace.
* Le rognage ne peut pas se produire dans les suites de rapports comme décrit dans les conditions préalables ci-dessus.
* Les suites de rapports Adobe Analytics ne peuvent pas mapper sur plusieurs organisations IMS. Etant donné que l’outil CDA rassemble des périphériques dans une suite de rapports donnée, il est impossible d’utiliser l’outil CDA pour assembler des données sur plusieurs organisations IMS.
* CDA n’est actuellement pas compatible avec les attributs du client. Les attributs du client ne peuvent pas être utilisés pour créer une suite de rapports virtuelle CDA, dans des segments inter-périphériques, ni pour la création de rapports dans un projet d’espace de travail Analysis basé sur une suite de rapports virtuelle CDA.
* L'ADC a besoin d'un graphique coopératif ou d'un graphique privé. Les graphiques de périphériques tiers ne sont pas pris en charge.
* Les identifiants Analytics hérités ne sont pas pris en charge. Seuls les visiteurs avec un ID Experience Cloud sont assemblés.
* Le service à la clientèle ne prend pas encore entièrement en charge cette fonctionnalité. Le forum [Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) sur plusieurs périphériques peut être utilisé pour la prise en charge de cette fonctionnalité, qui inclut une participation active et directe des responsables de produits Adobe.
* Analytics sur plusieurs périphériques utilise une suite de rapports virtuelle et le traitement du temps des rapports, qui ont leurs propres limites. Voir Suites [de rapports](../vrs/vrs-about.md) virtuelles et traitement [du temps des](../vrs/vrs-report-time-processing.md) rapports pour en savoir plus sur ces limitations.
* Les nouveaux périphériques qui visitent votre site peuvent prendre jusqu’à deux semaines pour être traités par le graphique Co-op ou le graphique privé. Le niveau de couture dans l’ADC pour les deux dernières semaines est généralement inférieur à celui des plages de dates de plus de deux semaines. Adobe prévoit d’améliorer le service d’identité d’Adobe Experience Platform afin d’assembler de nouveaux périphériques en temps réel à l’avenir.
* Les données historiques de la suite de rapports virtuelle changent en fonction de la reconnaissance par Adobe des périphériques et de leur assemblage. Les données de la suite de rapports source ne changent pas.

Une fois que toutes les conditions requises sont remplies et que vous avez compris les limites, vous pouvez commencer à [configurer Analytics](cda-setup.md)sur plusieurs périphériques.
