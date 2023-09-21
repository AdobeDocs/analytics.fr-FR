---
title: Visiteurs uniques
description: Nombre d’identifiants de visiteur uniques.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 96%

---

# Visiteurs uniques

&quot;Visiteurs uniques&quot; [metric](overview.md) indique le nombre d’identifiants visiteur pour l’élément de dimension. Il s’agit de l’une des mesures les plus courantes utilisées pour déterminer le trafic, car elle fournit un aperçu général de la popularité d’un élément de dimension. Par exemple, un visiteur peut venir sur votre site tous les jours pendant un mois et, néanmoins, ne représenter qu’un visiteur unique.

Si vous utilisez l’[analyse entre appareils](../cda/overview.md), cette mesure est remplacée par la mesure [Appareils uniques](unique-devices.md).

## Visiteurs uniques par jour, par semaine, par mois, par trimestre et par an

Reports &amp; Analytics offre des options pour les visiteurs uniques par jour, par semaine, par mois, par trimestre et par an. Au lieu de comptabiliser un seul visiteur unique pour toute la période, les visiteurs uniques sont comptabilisés en fonction de la mesure sélectionnée. Par exemple, vous pouvez consulter les visiteurs uniques par jour sur votre site. Si un visiteur consulte votre site le matin et à nouveau le soir, il compte comme un seul visiteur unique par jour. Si un visiteur consulte votre site le lundi et à nouveau le mardi, il compte comme deux visiteurs uniques par jour.

Analysis Workspace traite les visiteurs uniques en fonction de la granularité du rapport. Par exemple, si vous utilisez la dimension [Jour](../dimensions/day.md), vous verrez les visiteurs uniques par jour pour chaque élément de dimension. Toutefois, le total du rapport indique le nombre de visiteurs uniques dédupliqué pour la période du tableau à structure libre.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’ID de visiteur unique pour un élément de dimension donné. Elle utilise plusieurs mécanismes avancés pour identifier les visiteurs uniques, puisqu’il existe plusieurs façons de les identifier. Le tableau suivant liste les méthodes d’identification d’un visiteur, ainsi que leur priorité. Certains accès peuvent avoir plusieurs méthodes d’identification des visiteurs, auquel cas, la méthode à la priorité la plus élevée est utilisée.

| Ordre utilisé | Paramètre de requête (méthode de collecte) | Présenter quand |
| --- | --- | --- |
| 1 | `vid` | La variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) est définie. |
| 2 | `aid` | Le visiteur a un cookie [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=fr) existant. Défini lors de l’implémentation, sans ou avant l’implémentation du service d’identifiant de visiteur. |
| 3 | `mid` | Le visiteur a un cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=fr) existant. Défini lors de l’implémentation, à l’aide du service [Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr). |
| 4 | `fid` | Le visiteur a un cookie [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=fr) existant, ou `aid` et `mid` ne peuvent être définis pour aucune raison. |
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
