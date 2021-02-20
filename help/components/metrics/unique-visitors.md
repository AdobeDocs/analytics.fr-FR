---
title: Visiteurs uniques
description: Nombre d’identifiants de visiteur uniques.
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 96%

---


# Visiteurs uniques

La mesure « Visiteurs uniques » indique le nombre d’identifiants de visiteur pour l’élément de dimension. Il s’agit de l’une des mesures les plus courantes utilisées pour déterminer le trafic, car elle fournit un aperçu général de la popularité d’un élément de dimension. Par exemple, un visiteur peut venir sur votre site tous les jours pendant un mois et, néanmoins, ne représenter qu’un visiteur unique.

Si vous utilisez [Analyses sur plusieurs périphériques](../cda/overview.md), cette mesure est remplacée par la mesure [Périphériques uniques](unique-devices.md).

## Visiteurs uniques quotidiens, hebdomadaires, mensuels, trimestriels et annuels

Reports &amp; Analytics offre des options pour les visiteurs uniques quotidiens, hebdomadaires, mensuels, trimestriels et annuels. Au lieu de comptabiliser un seul visiteur unique pour toute la période, les visiteurs uniques sont comptabilisés en fonction de la mesure sélectionnée. Par exemple, vous pouvez consulter les visiteurs uniques quotidiens sur votre site. Si un visiteur consulte votre site le matin et à nouveau le soir, il compte comme un seul visiteur unique quotidien. Si un visiteur consulte votre site le lundi et à nouveau le mardi, il compte comme deux visiteurs uniques quotidiens.

Analysis Workspace traite les visiteurs uniques en fonction de la granularité du rapport. Par exemple, si vous utilisez la dimension [Jour](../dimensions/day.md), vous verrez les visiteurs uniques quotidiens pour chaque élément de dimension. Toutefois, le total du rapport indique le nombre de visiteurs uniques dédupliqué pour la période du tableau à structure libre.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’identifiants de visiteur unique pour un élément de dimension donné. Elle utilise plusieurs mécanismes avancés pour identifier les visiteurs uniques, puisqu’il existe plusieurs façons de les identifier. Le tableau suivant liste les méthodes d’identification d’un visiteur, ainsi que leur priorité. Certains accès peuvent avoir plusieurs méthodes d’identification des visiteurs, auquel cas, la méthode à la priorité la plus élevée est utilisée.

| Ordre utilisé | Paramètre de requête (méthode de collecte) | Présenter quand |
| --- | --- | --- |
| 1 | `vid` | La variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) est définie. |
| 2 | `aid` | Le visiteur a un cookie [`s_vi`](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-analytics.html) existant. Défini lors de l’implémentation, sans ou avant l’implémentation du service d’identifiant de visiteur. |
| 3 | `mid` | Le visiteur a un cookie [`s_ecid`](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-analytics.html) existant. Défini lors de l’implémentation, à l’aide du service [Adobe Experience Cloud Identity](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html). |
| 4 | `fid` | Le visiteur a un cookie [`s_fid`](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-analytics.html) existant, ou `aid` et `mid` ne peuvent être définis pour aucune raison. |
| 5 | Adresse IP, Agent utilisateur, Adresse IP de passerelle | Dernier recours pour identifier un visiteur unique si le navigateur du visiteur n’accepte pas les cookies. |

>[!NOTE]
>
>Chaque identifiant de visiteur Analytics est lié à un profil sur les serveurs d’Adobe. Les profils de ces visiteurs sont supprimés après au moins 13 mois d’inactivité, quelle que soit la date d’expiration des cookies d’identifiant de visiteur.

## Comportement affectant le nombre de visiteurs uniques

Les identifiants de visiteur unique sont généralement stockés dans un cookie de navigateur. Un nouveau visiteur unique est comptabilisé s’il :

* Efface son cache à tout moment.
* Ouvre un navigateur différent sur le même ordinateur. Un visiteur unique est comptabilisé par navigateur.
* Consulte votre site depuis un autre appareil. Un visiteur unique distinct est comptabilisé par appareil. Vous pouvez utiliser les [analyses entre appareils](../cda/overview.md) pour combiner les visiteurs à l’aide de la mesure [Personnes](people.md).
* Ouvre une session de navigation privée (comme l’onglet Incognito de Chrome).

Le visiteur n’est *pas* comptabilisé comme un nouveau visiteur unique tant que l’identifiant du cookie est conservé :

* Fermeture du navigateur pendant une période prolongée
* Mise à niveau du navigateur vers la version la plus récente
