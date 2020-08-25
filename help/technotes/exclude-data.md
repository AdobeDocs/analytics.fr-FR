---
title: Exclure des données dans Adobe Analytics
description: Découvrez différentes méthodes pour exclure des données avant et après la collecte de données.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# Exclure des données dans Adobe Analytics

L’exclusion de données est généralement utilisée pour empêcher les efforts de test de votre entreprise de renseigner les données de production ou pour empêcher les données indésirables de gonfler faussement les rapports. Utilisez l’une des méthodes suivantes pour exclure des données d’Adobe Analytics en fonction de votre cas d’utilisation.

## Exclure la collecte de données après la collecte de données

Les méthodes suivantes permettent d’exclure des données dans le rapports Analytics après que les serveurs de collecte de données d’Adobe aient reçu des demandes d’image. Les données exclues à l’aide de ces méthodes sont toujours comptabilisées dans les appels serveur facturables.

* **Exclure par adresse IP**: adobe analytics offre une fonctionnalité de base permettant d’exclure des données pour les adresses ou plages IP dans une suite de rapports. Voir [Exclure par adresse IP](/help/admin/admin/exclude-ip.md) dans le guide de l’utilisateur administrateur.
* **Règles** de robots : Les règles de robots prélèvent le trafic provenant de chaînes d’agent utilisateur connues et les excluent des rapports Analytics. Les données exclues par le biais des règles de robots sont placées dans le rapport Robots. Des règles de robots personnalisées peuvent être créées pour exclure des données supplémentaires. See [Bot Rules](/help/admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
* **Règles** VISTA : En fonction des besoins de votre entreprise, les accès qui correspondent à vos besoins sont envoyés à une autre suite de rapports dédiée à la réception de données exclues. Les règles VISTA sont généralement utilisées par rapport aux adresses IP, mais ne sont pas limitées à celles-ci. Vous pouvez utiliser n’importe quelle dimension pour inclure ou exclure des données dans les suites de rapports. Les règles VISTA sont soumises à des coûts supplémentaires ; pour plus d’informations, contactez le gestionnaire de compte de votre organisation.
* **Cookies** d’exclusion : Tous les visiteurs de votre site peuvent volontairement opt-out faire l’objet d’un suivi dans Adobe Analytics en visitant une page spécifique à votre serveur de suivi. Reportez-vous à la section [Mise en oeuvre des liens](/help/implement/js/opt-out.md) d’exclusion dans le guide de l’utilisateur Mise en oeuvre.

>[!TIP]
>
>Les règles de traitement ne peuvent pas exclure des données ni envoyer des données à une autre suite de rapports. Cependant, certaines variables peuvent être définies de manière conditionnelle et un segment peut être utilisé pour exclure ces données du rapports.

## Exclure la collecte de données avant la collecte de données

Si vous souhaitez empêcher certains accès d’atteindre les serveurs de collecte de données Analytics, utilisez la [`abort`](/help/implement/vars/config-vars/abort.md) variable. Cet indicateur empêche l’envoi de la demande d’image. Les appels serveur facturables ne sont pas incrémentés pour les demandes d’image abandonnées, puisqu’ils n’atteignent pas les serveurs de collecte de données d’Adobe.
