---
description: Les analyses des pages en temps réel (mode réel) vous permettent d’obtenir des résultats avec une granularité détaillée en temps réel.
seo-description: Les analyses des pages en temps réel (mode réel) vous permettent d’obtenir des résultats avec une granularité détaillée en temps réel.
seo-title: Analyse des pages en temps réel (en direct)
solution: Analytics
title: Analyse des pages en temps réel (en direct)
topic: Activity Map
uuid: a 3 faa 9 bd -73 d 8-48 b 3-be 2 b-f 818 ed 7456 fb
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Analyse des pages en temps réel (en direct)

Les analyses des pages en temps réel (mode réel) vous permettent d’obtenir des résultats avec une granularité détaillée en temps réel.

Activity Map affiche désormais les données d’analyse par incréments de 1 à 15 minutes afin de contrôler la popularité des liens en fonction des micro-tendances pour les pages sélectionnées. Cela est particulièrement important pour les entreprises d’édition afin de suivre et de répondre à l’augmentation et à la réduction de l’intérêt pour les histoires et afin de contrôler le flux de trafic en temps réel.

En tant que propriétaire de contenu de site, une partie de votre travail consiste à promouvoir et à supprimer le contenu et à maintenir notre expérience constamment intéressante. Les données en temps réel sont essentielles à cette responsabilité. Si vous comprenez quels liens et contenus rencontrent du succès à ce moment précis, vous pouvez agir rapidement et résolument pour maintenir l’engagement des lecteurs et des clients.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

## Data latency as a result of A4T configuration {#section_806CE36354FC4C539A0DED9266A5C704}

Une fois l’intégration A4T activée dans Adobe Target, vous remarquerez une latence supplémentaire de 5 à 10 minutes dans Adobe Analytics. Cette augmentation de la latence permet aux données provenant d’Analytics et de Target d’être stockées sur le même accès, permettant de ventiler les tests par page et par section de site.

Cette augmentation se reflète dans tous les services et outils d’Adobe Analytics, notamment la diffusion en continu active et la création de rapports en temps réel, et s’applique dans les scénarios suivants :

* Pour la diffusion en continu active, les rapports en temps réel, les requêtes d’API et les données actives pour les variables de trafic, seuls les accès avec un ID supplémentaire sont retardés.
* Pour les données actives sur les mesures de conversion, les données finalisées et les flux de données, tous les accès sont retardés de 5 à 7 minutes supplémentaires.

Be aware that the latency increase starts after you implement the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), even if you have not fully implemented this integration.
