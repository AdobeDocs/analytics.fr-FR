---
title: FAQ sur la mise en œuvre d’Analytics
description: Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# FAQ sur la mise en œuvre d’Analytics

Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.

**Quelle est la différence entre l’attribution des variables et l’expiration ?**

L’attribution et l’expiration sont des paramètres que vous pouvez appliquer aux variables personnalisées. *L’attribution* entre en jeu lorsque vous disposez d’une valeur de variable persistante et d’une nouvelle valeur de variable. Il détermine si l’ancienne ou la nouvelle valeur est conservée. *L’expiration* entre en jeu lorsque vous ne souhaitez pas qu’une valeur de variable persiste.

**Quelle est la différence entre l’identifiant visiteur Experience Cloud et l’identifiant visiteur Analytics ?**

Le service d’identité affecte un identifiant persistant unique qui peut être partagé entre d’autres solutions dans Experience Cloud. L’identifiant visiteur Analytics est utilisé uniquement par Analytics. Adobe recommande d’utiliser le service d’identification des visiteurs d’Experience Cloud dans votre implémentation.

**Comment l’identifiant visiteur est-il défini si les cookies sont bloqués ?**

If the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2-year expiration and is used as the fallback identification method going forward.

**Comment mettre en oeuvre le suivi vidéo de pulsation ?**

Voir [Mesures audio et vidéo dans Adobe Analytics](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html).

**Une interruption de service chez Adobe peut-elle affecter les performances ?**

Non. Le fichier JavaScript n’est pas hébergé sur les serveurs Adobe. Une panne d’Adobe n’affecte donc pas votre bibliothèque AppMeasurement. Si vous utilisez Adobe Experience Platform Launch, le fichier JavaScript est hébergé par Akamai ou sur un emplacement de serveur déterminé par votre entreprise.

**L’envoi de données du navigateur vers les services Adobe peut-il réduire les performances ?**

AppMeasurement crée un objet image dans la page HTML, puis le navigateur le demande aux serveurs de collecte de données Adobe. Si les serveurs de collecte de données étaient lents ou ne répondaient pas, le thread qui gérait cette requête serait retardé jusqu’à ce que l’image soit renvoyée ou qu’un délai d’expiration se produise. Les navigateurs gèrent les images avec plusieurs threads. Pour cette raison, les pannes de serveurs Adobe ont peu d’incidence sur le temps de chargement de la page puisqu’un seul thread est concerné tandis que les autres continuent à fonctionner.

**Comment effectuer le suivi d’une application mobile ?**

Vous pouvez utiliser le SDK Adobe Experience Platform. Voir Présentation [du SDK](https://aep-sdks.gitbook.io/docs/) Adobe Experience Platform pour en savoir plus.

**Que sont les plug-ins ?**

Les plug-ins sont des fragments de code qui exécutent des fonctions avancées. Ils étendent les fonctionnalités d’AppMeasurement pour offrir davantage de fonctionnalités à votre implémentation.
