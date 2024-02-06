---
title: Exclusion de données dans Adobe Analytics
description: Découvrez différentes méthodes permettant d’exclure des données avant et après la collecte de données.
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
feature: Data Configuration and Collection
role: Admin
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 96%

---

# Exclusion de données dans Adobe Analytics

L’exclusion de données est généralement utilisée pour empêcher les efforts de test de votre organisation de renseigner les données de production ou pour empêcher les données indésirables de gonfler faussement les rapports. Utilisez l’une des méthodes suivantes pour exclure des données d’Adobe Analytics en fonction de votre cas d’utilisation.

## Exclusion de données après la collecte de données

Les méthodes suivantes permettent d’exclure des données dans le compte rendu des performances d’Analytics après la réception des demandes d’image par les serveurs de collecte de données d’Adobe. Les données exclues à l’aide de ces méthodes comptent toujours dans les appels au serveur facturables.

* **Exclure par IP** : Adobe Analytics offre une fonctionnalité de base permettant d’exclure des données pour les adresses IP ou plages d’adresses IP dans une suite de rapports. Voir [Exclure par IP](/help/admin/admin/exclude-ip.md) dans le guide de l’utilisateur des administrateurs.
* **Règles de robots** : les règles de robots prélèvent le trafic provenant de chaînes d’agent utilisateur robot connues et les excluent des rapports Analytics. Les données exclues par le biais des règles de robots sont placées dans le rapport sur les robots. Des règles de robots personnalisées peuvent être créées pour exclure des données supplémentaires. Voir [Règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) dans le guide de l’utilisateur des administrateurs.
* **Règles VISTA** : en fonction des besoins de votre organisation, les accès qui correspondent à vos exigences sont envoyés à une autre suite de rapports dédiée à la réception des données exclues. Les règles VISTA sont généralement utilisées par rapport aux adresses IP, mais ne sont pas limitées à celles-ci. Vous pouvez utiliser n’importe quelle dimension pour inclure ou exclure des données dans les suites de rapports. Les règles VISTA sont soumises à des coûts supplémentaires. Contactez votre équipe de compte d’Adobe pour plus d’informations.
* **Cookies d’exclusion** : tous les visiteurs de votre site peuvent volontairement faire valoir leur droit d’opposition afin de ne pas faire l’objet d’un suivi dans Adobe Analytics en visitant une page spécifique à votre serveur de suivi. Voir [Mise en œuvre des liens d’exclusion](/help/implement/js/opt-out.md) dans le guide de l’utilisateur de l’implémentation.

>[!TIP]
>
>Les règles de traitement ne peuvent ni exclure des données, ni en envoyer à une autre suite de rapports. Cependant, certaines variables peuvent être définies de manière conditionnelle et un segment peut être utilisé pour exclure ces données du compte rendu des performances.

## Exclusion de données avant la collecte de données

Si vous souhaitez empêcher certains accès d’atteindre les serveurs de collecte de données d’Analytics, utilisez la variable [`abort`](/help/implement/vars/config-vars/abort.md). Cet indicateur empêche l’envoi de la demande d’image. Les appels au serveur facturables ne sont pas incrémentés pour les demandes d’image abandonnées, puisqu’ils n’atteignent pas les serveurs de collecte de données d’Adobe.
