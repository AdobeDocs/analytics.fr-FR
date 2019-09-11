---
title: Analyses multiterminaux
description: Analytics de plusieurs périphériques convertit vos données de manière à cibler les personnes en assemblant les données de périphériques.
translation-type: tm+mt
source-git-commit: 40d8ecae1ac7e0a1df4a2df17f5104bee6ecf336

---


# Analyses multiterminaux

> [!NOTE] La documentation sur les analyses inter-périphériques peut faire l'objet de modifications lorsque la fonctionnalité est développée. Vérifiez régulièrement les mises à jour.

Analytics inter-périphériques est une fonctionnalité qui transforme Analytics d'une vue orientée périphérique vers une vue axée sur la personne. Cette fonctionnalité utilise Adobe Experience Platform Identity Service Co-op Graph ou Private Graph pour identifier les périphériques qui appartiennent à des individus et les assembler. Par conséquent, les analystes peuvent comprendre le comportement des utilisateurs qui franchissent les navigateurs, les appareils ou les applications. Grâce à CDA, vous pouvez répondre à des questions telles que :

* Combien de personnes interagissent avec ma marque ? Combien de types de périphériques utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un périphérique mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne amenant à un périphérique conduisent-ils à une conversion ailleurs ?
* Comment ma compréhension de l’efficacité de la campagne change-t-elle si je prends en compte les trajets entre plusieurs périphériques ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un périphérique à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs périphériques diffère-t-il de celui des utilisateurs disposant d’un seul périphérique ?

Lorsque les périphériques sont assemblés, la persistance de variable est reportée sur les périphériques. Par exemple, un utilisateur visite votre site pour la première fois via une publicité sur son ordinateur de bureau. Cet utilisateur trouve votre application mobile, l'installe et effectue finalement un achat sur son périphérique mobile. Avec Analytics sur plusieurs périphériques, les recettes peuvent être attribuées à la publicité sur laquelle les utilisateurs cliquent sur leur ordinateur de bureau.

Voir [Parcours IQ : Page Spark d'analyses inter-périphériques](http://adobe.ly/aacda) pour en savoir plus sur les fonctionnalités et fonctionnalités d'Analytics inter-périphériques.

## Conditions préalables

Depuis septembre 2019, les analyses inter-périphériques nécessitent les éléments suivants. Collaborez avec les équipes de votre société et votre gestionnaire de compte Adobe pour vous assurer que vous remplissez tous les critères ci-dessous.

> [!IMPORTANT] Si l'utilisateur ne parvient pas à respecter toutes les conditions préalables, il est possible qu'il soit impossible d'activer Analytics sur plusieurs périphériques ou de mauvais résultats lors de l'assemblage des données.

* Les données de votre organisation doivent résider dans le centre de données nord-ouest du Pacifique d'Adobe. La prise en charge des centres de données dans d'autres régions du monde est prévue.
* Contactez le gestionnaire de compte de votre entreprise pour définir ces points clés :
   * Un contrat doit être signé avec Adobe qui inclut Adobe Analytics Ultimate.
   * Votre entreprise doit utiliser le graphique Adobe Experience Platform Identity Service Co-op Graph ou le graphique privé. Voir la page [d'accueil](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) du guide de l'utilisateur Device Co-op.
   * Votre entreprise doit accepter d'autoriser Adobe à traiter et à stocker les données Analytics sur les serveurs Microsoft Azure. Adobe utilise Azure pour stocker les données du graphique de périphérique et effectuer l'assemblage de périphériques. Par conséquent, les données Adobe Analytics sont transmises de nouveau entre les données d'Adobe - centre de traitement et présence d'Adobe dans Microsoft Azure.
* La fonction Analyses croisées est activée par suite de rapports. Votre suite de rapports requiert les éléments suivants :
   * Actuellement, une suite de rapports ne peut pas compter plus de 100 millions de visites par jour. Ce seuil augmentera au cours des mois à venir.
   * Une suite de rapports « plusieurs périphériques », ce qui signifie que toutes les données doivent être envoyées à la même suite de rapports. Certaines organisations y font référence en tant que suite de rapports globale, bien que la norme CDA ne doive pas nécessairement être globale dans un contexte géographique. Les analyses croisées ne fonctionnent pas dans les suites de rapports.
* Votre mise en œuvre doit respecter les exigences suivantes :
   * La dernière version du service Experience Cloud ID doit être déployée. Voir la page [d'accueil](https://docs.adobe.com/content/help/en/id-service/using/home.html) du guide de l'utilisateur d'Experience Cloud ID Service. La plupart des implémentations utilisant le lancement d'Adobe Experience Platform sont probablement déjà déployées.
   * Appelez la `setCustomerIDs` fonction chaque fois qu'un utilisateur peut être identifié, par exemple lorsqu'un utilisateur se connecte ou ouvre un courrier électronique. Cette exigence s'applique à toutes les plates-formes, y compris les applications mobiles si elles sont utilisées. Voir [setcustomerids](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) dans le guide de l'utilisateur du service Experience Cloud Identity Service.

## Limites

L'analyse croisée des périphériques est une fonctionnalité innovante et puissante, mais elle présente des limites quant à son utilisation.

* CDA est disponible uniquement via Analysis Workspace.
* L'assemblage ne peut pas se produire dans les organisations IMS. Veillez à n'utiliser pas plusieurs instances IMS dans votre implémentation.
* L'assemblage ne peut pas se produire dans les suites de rapports comme décrit dans Conditions préalables ci-dessus.
* CDA n'est actuellement pas compatible avec les attributs du client. Les attributs du client ne peuvent pas être utilisés pour créer une suite de rapports virtuelle CDA, dans des segments sur plusieurs périphériques ou pour la création de rapports dans un projet d'espace de travail d'analyse basé sur une suite de rapports virtuelle CDA.
* CDA requiert le graphique Co-op ou le graphique privé. Les graphiques de périphériques tiers ne sont pas pris en charge.
* Les identifiants Analytics hérités ne sont pas pris en charge. Seuls les visiteurs avec des ID d'expérience sont assemblés.
* Le service à la clientèle ne prend pas encore totalement en charge cette fonctionnalité. Le forum Analyses [croisées](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) peut être utilisé pour la prise en charge de cette fonctionnalité, qui inclut une participation active et directe des gestionnaires de produits Adobe.
* Les analyses croisées utilisent une suite de rapports virtuelle et le traitement du temps de rapport, qui ont leurs propres limites. Pour plus d'informations sur ces limites, reportez-vous à la section [Suites](../vrs/vrs-about.md) de rapports virtuelles et [Traitement](../vrs/vrs-report-time-processing.md) du temps de rapport.
* Les nouveaux périphériques qui visitent votre site peuvent prendre jusqu'à deux semaines pour être traités par le graphique Co-op ou le graphique privé. Le niveau d'assemblage dans CDA pour les deux semaines les plus récentes est généralement inférieur à celui des plages de dates antérieures à deux semaines. Adobe prévoit d'améliorer le service d'identité Adobe Experience Platform afin de regrouper les nouveaux périphériques en temps réel.
* Les données historiques de la suite de rapports virtuelle changent en fonction de la manière dont Adobe reconnaît et assemble les périphériques. Les données de la suite de rapports source ne changent pas.

Une fois que votre organisation a répondu à toutes les exigences et que vous connaissez les limites, vous pouvez commencer [la définition de l'option Définition - Analyses croisées entre périphériques](cda-setup.md).
