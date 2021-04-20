---
description: Les analyses des pages en temps réel (mode réel) vous permettent d’obtenir des résultats avec une granularité détaillée en temps réel.
title: Analyse des pages en temps réel (mode réel)
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 71%

---


# Analyse des pages en temps réel (mode réel)

Les analyses des pages en temps réel (mode réel) vous permettent d’obtenir des résultats avec une granularité détaillée en temps réel.

Le Activity Map affiche désormais les données d’analyse par incréments de 1 minute à 15 minutes afin de surveiller la popularité des liens en fonction des micro-tendances pour les pages sélectionnées. Cela est particulièrement important pour les entreprises d’édition afin de suivre et de répondre à l’augmentation et à la réduction de l’intérêt pour les histoires et afin de contrôler le flux de trafic en temps réel.

En tant que propriétaire de contenu de site, une partie de votre travail consiste à promouvoir et à supprimer le contenu et à maintenir notre expérience constamment intéressante. Les données en temps réel sont essentielles à cette responsabilité. Si vous comprenez quels liens et contenus rencontrent du succès à ce moment précis, vous pouvez agir rapidement et résolument pour maintenir l’engagement des lecteurs et des clients.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

Si vous souhaitez vérifier l’élément sur lequel les utilisateurs cliquent le plus souvent en mode réel :

1. Sélectionnez la période sur la ligne de tendance **[!UICONTROL Mode réel]** de la barre d’outils que vous souhaitez analyser.
1. Cliquez sur l&#39;icône &quot;OEil&quot; dans la barre d&#39;outils pour accéder au tableau du rapport Liens.
1. Organisez la table selon le lien.

## Latence des données suite à la configuration d’A4T

Une fois l’intégration [A4T](https://docs.adobe.com/content/help/fr-FR/target/using/integrate/a4t/a4t.html) activée dans Adobe Target, vous allez connaître 5 à 10 minutes de latence supplémentaires dans Adobe Analytics. Cette augmentation de la latence permet aux données provenant d’Analytics et de Target d’être stockées sur le même accès, permettant de ventiler les tests par page et par section de site.

Cette augmentation se reflète dans tous les services et outils d’Adobe Analytics, notamment la diffusion en continu active et la création de rapports en temps réel, et s’applique dans les scénarios suivants :

* Pour la diffusion en continu active, les rapports en temps réel, les requêtes d’API et les données actives pour les variables de trafic, seuls les accès avec un ID supplémentaire sont retardés.
* Pour les données actives sur les mesures de conversion, les données finalisées et les flux de données, tous les accès sont retardés de 5 à 7 minutes supplémentaires.

Gardez à l’esprit que l’augmentation de latence débute une fois que vous avez implémenté le [service d’identité](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html), même si vous n’avez pas entièrement implémenté cette intégration.

Plus d&#39;informations [ici](/help/analyze/activity-map/activitymap-standard-live.md).