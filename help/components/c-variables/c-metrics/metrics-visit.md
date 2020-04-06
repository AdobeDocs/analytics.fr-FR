---
description: Une séquence de de page  en session. Cette mesure est généralement utilisée dans les rapports qui affichent le nombre de sessions utilisateurs au cours de la période sélectionnée.
keywords: visit
title: Visite
topic: Metrics
uuid: 91317487-f116-4546-8cd2-421418c49a7a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visite

Une séquence de de page  en session. Cette mesure est généralement utilisée dans les rapports qui affichent le nombre de sessions utilisateurs au cours de la période sélectionnée.

>[!NOTE] Pour en savoir plus sur le calcul des visites et des lancements d’application mobile, voir [Comparaison des visites et des lancements d’application mobile](https://helpx.adobe.com/fr/analytics/kb/compare-visits-and-mobile-app-launches.html) dans la base de connaissances.

Cette mesure est toujours associée à une période afin que vous sachiez si vous comptabilisez ou non une nouvelle visite si le même visiteur revient sur votre site. de session lorsque l’utilisateur arrive pour la première fois sur votre site et se termine dans l’un des scénarios suivants :

* **30 minutes d&#39;inactivité :** Presque toutes les sessions se terminent ainsi. Si plus de 30 minutes se sont écoulées entre les demandes d’image, une nouvelle visite commence.
* **12 heures de  constante  :** Si un utilisateur déclenche des demandes d’images sans intervalle de 30 minutes ou plus pendant 12 heures, une nouvelle visite  automatiquement.
* **2 500 accès :** Si un utilisateur génère un grand nombre d’accès sans commencer une nouvelle session, une nouvelle visite est comptabilisée après 2 500 demandes d’image.
* **100 accès en 100 secondes**: Si une visite comprend plus de 100 accès survenant en moins de 100 secondes, la visite se termine automatiquement. Ce comportement indique généralement   de et cette limitation est appliquée pour empêcher ces visites gourmandes en traitement d’augmenter la latence et le temps nécessaire à la génération des rapports.

>[!NOTE] La définition d’une visite peut être raccourcie pour une suite de rapports si une requête spécifique est formulée dans ce sens, mais elle ne peut pas être rallongée. Demandez à l’un des utilisateurs de votre entreprise ayant souscrit un plan d’assistance dédié de contacter le service d’assistance clientèle pour demander cette modification.

Les scénarios suivants ne  pas une nouvelle visite :

* L’utilisateur ferme l’onglet, le rouvre et revient sur votre site dans les 30 minutes. L’utilisateur peut également fermer son navigateur ou redémarrer l’ordinateur et être compté comme une visite unique (le revient sur votre site dans les 30 minutes).
* Utilisateurs naviguant sur votre site dans plusieurs onglets. Bien que la navigation à onglets multiples n’incrémente pas les visites ou les, c’est le cas avec un navigateur distinct. En effet, les différents onglets font référence aux mêmes cookies, contrairement aux navigateurs distincts.

Une visite ne coïncide pas nécessairement avec une session de navigateur. Par exemple, si un ferme le navigateur, le rouvre et accède à votre site cinq minutes plus tard, il est reconnu comme la suite de la même visite. Cela signifie également que si un reste sur une page pendant 35 minutes, la visite sera fermée et traitée, et une nouvelle visite s’il clique jusqu’à une autre page.

À la fin d’une visite, toutes les variables dont la visite arrive à expiration expirent et ne persistent plus. La mesure du nombre de visites sera incrémentée lors de la prochaine visite pour ce.

>[!NOTE] Si vous utilisez Analytics en tant que source des rapports pour Adobe Target, reportez-vous à la section [Minimisation du nombre de visiteurs ou de visites exagéré dans A4T](https://marketing.adobe.com/resources/help/fr_FR/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) dans la documentation [!DNL Target].

Pour plus d’informations, voir [Identification des](https://marketing.adobe.com/resources/help/fr_FR/sc/implement/visid_overview.html) uniques dans le guide de mise en oeuvre d’Adobe Analytics.

**Périodes**

Une visite est signalée pour chaque période au cours de laquelle   s’est produite. Par exemple, supposons qu’une visite commence à 23h45 le 1er décembre et se poursuit jusqu’à 12h30 le 2 décembre. La visite est comptabilisée les 1er et 2 décembre. Ce s’applique à d’autres périodes, y compris les périodes hebdomadaire, mensuelle, trimestrielle et annuelle.
