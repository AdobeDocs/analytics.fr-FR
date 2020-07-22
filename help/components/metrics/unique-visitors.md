---
title: Visiteurs uniques
description: Nombre d’individus (ou de dispositifs) uniques.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 10%

---


# Visiteurs uniques

La mesure &quot;visiteurs uniques&quot; indique le nombre d’ID de visiteur pour l’élément de dimension. Il s’agit de l’une des mesures les plus courantes utilisées pour déterminer le trafic, car il fournit un aperçu général de la popularité d’un élément de dimension. Par exemple, un visiteur peut venir sur votre site tous les jours pendant un mois, mais il compte toujours comme un seul visiteur unique.

Si vous utilisez les analyses [](../cda/overview.md)multipériphériques, cette mesure est renommée &quot;Périphériques uniques&quot;.

## visiteurs uniques quotidiens, hebdomadaires, mensuels, trimestriels et annuels

Les rapports et Analytics offrent des options pour les visiteurs uniques quotidiens, hebdomadaires, mensuels, trimestriels et annuels. Au lieu de comptabiliser un seul visiteur unique pour toute la période, les visiteurs uniques comptent en fonction de la mesure sélectionnée. Par exemple, vous souhaitez consulter les visiteurs uniques quotidiens de votre site. Si un visiteur vient sur votre site le matin et de nouveau la nuit, il compte comme un visiteur unique quotidien unique. Si un visiteur vient sur votre site le lundi et de nouveau le mardi, il compte comme deux visiteurs uniques par jour.

L’Analysis Workspace traite les visiteurs uniques en fonction de la granularité du rapport. Par exemple, si vous utilisez la dimension [Jour](../dimensions/day.md) , vous verrez des visiteurs uniques quotidiens pour chaque élément de dimension. Toutefois, pour le total du rapport, il est dédupliqué en visiteurs uniques pour la période du tableau à structure libre.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’ID de visiteur uniques pour un élément de dimension donné. Il utilise plusieurs mécanismes avancés pour identifier les visiteurs uniques, puisqu&#39;il existe plusieurs façons de les identifier. Le tableau suivant liste les méthodes d’identification d’un visiteur, ainsi que sa priorité. Certains accès peuvent avoir plusieurs méthodes d&#39;identification des visiteurs ; dans ces cas, la méthode de priorité la plus élevée est utilisée.

| Ordre utilisé | Paramètre de requête (méthode de collecte) | Présenter quand |
| --- | --- | --- |
| 1 | `vid` | La [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable est définie. |
| 2 | `aid` | Le Visiteur a un [`s_vi`](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-analytics.html) cookie existant. Définissez sur les implémentations sans ou avant la mise en oeuvre du service d’ID de Visiteur. |
| 3 | `mid` | Le Visiteur a un [`s_ecid`](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-analytics.html) cookie existant. Définissez les mises en oeuvre à l’aide du service [d’identité](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html)Adobe Experience Cloud. |
| 4 | `fid` | Le Visiteur possède un [`s_fid`](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-analytics.html) cookie existant ou si `aid` et `mid` ne peuvent être définis pour aucune raison. |
| 5 | Adresse IP, Agent utilisateur, Adresse IP de passerelle | Dernier recours pour identifier un visiteur unique si le navigateur du visiteur n’accepte pas les cookies. |

>[!NOTE]
>
>Chaque ID de visiteur Analytics est lié à un profil sur les serveurs Adobe. Ces profils de visiteur sont supprimés après au moins 13 mois d’inactivité, quelle que soit l’expiration du cookie d’ID de visiteur.

## Comportement affectant le nombre de visiteurs uniques

Les identifiants de visiteur uniques sont généralement stockés dans un cookie de navigateur. Un nouveau visiteur unique est comptabilisé s’il effectue l’une des opérations suivantes :

* Efface leur cache à tout moment
* Ouvre un navigateur différent sur le même ordinateur. Un visiteur unique est comptabilisé par navigateur.
* Même personne qui consulte votre site sur différents périphériques. Un visiteur unique distinct est comptabilisé par périphérique. Vous pouvez utiliser les analyses [](../cda/overview.md) inter-périphériques pour combiner des visiteurs à l’aide de la mesure [Personnes](people.md) .
* Ouvre une session de navigation privée (comme l’onglet Incognito de Chrome).

Un nouveau visiteur unique *n’est* pas comptabilisé, tant que l’identifiant du cookie est conservé :

* Ferme leur navigateur pendant une période prolongée.
* Met son navigateur à niveau vers la dernière version
