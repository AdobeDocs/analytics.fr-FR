---
title: Adobe Analytics et les cookies de navigateur
description: Découvrez comment les mesures de prévention du suivi affectent les cookies tiers et propriétaires définis par Adobe Analytics.
source-git-commit: b2f606e74aa0d2ab0f01ab7cbfc795bfd7cda461
workflow-type: tm+mt
source-wordcount: '1985'
ht-degree: 7%

---


# Adobe Analytics et les cookies de navigateur

Ce document explique comment les principales mesures de prévention du suivi des navigateurs affectent les cookies tiers et propriétaires définis par Adobe Analytics. Il contient des informations sur le programme ITP (Intelligent Tracking Prevention) d’Apple, ainsi que les restrictions de Chrome sur les cookies tiers via l’attribut MêmeSite.

## Comment les navigateurs ont-ils limité l&#39;utilisation des cookies ?

>[!NOTE]
>[Analytics sur plusieurs périphériques ](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en#cda) et [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#comparing-cja-to-traditional-adobe-analytics) peuvent recouper les cookies à l’aide d’un identifiant de personne, tel qu’un identifiant de connexion haché, si disponible.

### Limites des cookies tiers

Les cookies utilisés dans un contexte tiers sont largement abandonnés. Firefox et Safari ont commencé à bloquer les cookies tiers par défaut à partir de 2019 et 2020, respectivement. Chrome a annoncé son intention de cesser de prendre en charge les cookies tiers en 2022. Dans ce cas, les cookies tiers seront inutilisables.

De plus, Chrome n’autorise actuellement le fonctionnement des cookies que dans un contexte tiers si l’attribut &quot;MêmeSite&quot; est défini sur Aucun et que les cookies sont étiquetés comme sécurisés, ce qui signifie qu’ils ne peuvent être utilisés que par HTTPS. Pour plus d’informations, consultez la section &quot;[Qu’est-ce que l’attribut de cookie Siteidentique et comment cela affecte Analytics ?](#samesite-effect)&quot;.

#### Quels cookies tiers d’Adobe sont affectés ?

Le service d’identification des Visiteurs utilise le cookie &quot;[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)&quot; pour fournir un identifiant persistant aux visiteurs de différents domaines de clients. Le cookie s_vi, ancien service d’identification Analytics, est défini comme cookie tiers pour les implémentations n’utilisant pas de domaine de collecte CNAME personnalisé.

Dans les navigateurs où les cookies tiers sont bloqués, le suivi inter-domaines n’est pas disponible.

### Limites des cookies propriétaires {#limitations-first-party-cookies}

Les cookies propriétaires sont autorisés sur tous les principaux navigateurs. Cependant, Apple limite la durée de vie des cookies propriétaires définis par l’Adobe via son Programme de suivi intelligent (ITP). Cela affecte Safari ainsi que tous les navigateurs sous iOS et iPadOS.

Les cookies propriétaires d’Adobe sont limités à une expiration de 7 jours ou, pour les clics publicitaires qu’Apple détermine provenant de suivis, à une expiration de 24 heures. Avec une expiration de 7 jours, si un utilisateur visite votre site et revient dans les sept jours, la date d’expiration du cookie est prolongée de sept jours supplémentaires. Cependant, si un utilisateur consulte votre site et revient dans les huit jours, il est traité comme un nouvel utilisateur lors de sa deuxième visite.

Actuellement, les stratégies ITP s’appliquent à tous les cookies propriétaires définis par Adobe, que vous utilisiez le service d’identification des Visiteurs ou le cookie Analytics ID hérité (&quot;s_vi&quot;). A un moment donné, ces stratégies s’appliquaient uniquement aux cookies définis côté client et non aux cookies définis côté serveur via une implémentation CNAME. En novembre 2020, cependant, le PTI a été mis à jour pour s&#39;appliquer également aux mises en oeuvre du CNAME.

#### Calendrier des modifications majeures apportées à la stratégie ITP {#ITP-timeline}

* Février 2019 avec [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) : Les cookies côté client ont été limités à une expiration de sept jours.
* Avril 2019 avec [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) : Les cookies côté client étaient limités à 24 heures pour les clics publicitaires lorsque le domaine référent était a) impliqué dans le suivi intersite et b) que l’URL finale contenait une chaîne de requête et/ou un identifiant de fragment.
* Novembre 2020 avec [CNAME Cloaking and Bounce Tracking Defense](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/) : Les limitations du protocole ITP ont été étendues aux implémentations CNAME.

Les politiques du PTI évoluent fréquemment. Pour connaître les dernières stratégies, voir [Prévention du suivi d’Apple dans Webkit](https://webkit.org/tracking-prevention).

#### Quels cookies propriétaires d’Adobe sont affectés ?

Tous les cookies propriétaires définis par Adobe et les bibliothèques JavaScript associées sont affectés par les stratégies ITP :

* [Le ](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) cookie &quot;AMCV&quot; est défini par la bibliothèque de service ECID (Adobe Experience Cloud Visiteur ID)
* Le cookie [&quot;s_vi&quot; hérité d’Analytics](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) lorsqu’il est configuré avec la collecte de données propriétaires à l’aide d’un CNAME
* Le cookie hérité [&quot;s_fid&quot; d’Analytics](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html), qui est le cookie de secours utilisé lorsque &quot;s_vi&quot; ne peut pas être défini.

#### Quel est l’impact de ITP sur Safari pour Analytics ?

L&#39;impact des limitations ITP peut varier considérablement, en fonction du comportement de vos utilisateurs. Seuls les visiteurs qui utilisent un navigateur impacté par le protocole ITP (par exemple Safari) et qui reviennent après une absence de sept jours sont concernés. Si les visiteurs n&#39;utilisent pas de navigateur ITP ou ne reviennent pas dans les sept jours, ils ne sont pas affectés. Il est important de revoir vos propres données dans Analytics pour comprendre l’ampleur de l’impact de cette limitation. Pour obtenir des conseils sur la façon de mesurer l&#39;impact sur vos sites, voir &quot;[Comment puis-je déterminer si les modifications de Safari affectent mon activité ?](#measure-itp-effect)&quot;

Si ces limitations affectent vos données, vous verrez :

1. Augmentation du nombre de Visiteurs qui retournent chez eux sont traités comme de nouveaux visiteurs parce que leurs cookies ont expiré. Toutes les mesures basées sur la mesure du Visiteur (comme les ventes par Visiteur) sont également affectées.
2. Modifications apportées à l’attribution. L’attribution repose sur le fait de lier les événements de conversion aux activités précédentes par le même visiteur. Une fois qu’un cookie arrive à expiration, les événements suivants sont associés à un nouveau visiteur. Les activités du nouveau visiteur ne peuvent pas être liées aux activités du visiteur précédent.

>[!NOTE]
>
>Actuellement, les technologies ITP ne s&#39;appliquent pas aux navigateurs intégrés dans les applications mobiles.

## Quelle est la différence entre les cookies tiers et les cookies propriétaires ?

### Cookies tiers

Les cookies tiers ne sont pas créés par les sites Web que les utilisateurs visitent.

Bien que les navigateurs traitent actuellement tous les cookies tiers de la même manière et les stockent, les cookies tiers peuvent se comporter différemment. Avec l’implémentation des cookies tiers Analytics d’un client, les navigateurs stockent l’Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html) ID en tant que cookie tiers, mais le client effectue des appels uniquement à l’Adobe et non à des domaines tiers inconnus ou suspects. Ce cookie fournit des identifiants persistants sur plusieurs domaines et permet le contenu sécurisé (HTTPS). Pour plus d’informations, voir [Cookies et Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html).

Dans les implémentations d’Analytics, les cookies tiers sont utilisés pour le suivi inter-domaines et pour les cas d’utilisation des publicités, y compris le reciblage des publicités. Les cookies tiers vous permettent d&#39;identifier les visiteurs qui visitent différents domaines que vous possédez ou qui affichent des publicités sur des sites que vous ne possédez pas.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### Cookies propriétaires

Les cookies propriétaires sont propres au domaine et sont créés par les sites Web des clients et stockés dans les navigateurs client lorsque les utilisateurs visitent ces sites. Tous les navigateurs acceptent généralement les cookies propriétaires, bien que [Safari limite l’expiration de certains types de cookies propriétaires](#limitations-first-party-cookies).

Dans les implémentations d’Analytics, les cookies propriétaires sont utilisés pour identifier les utilisateurs lorsqu’ils se trouvent sur votre site et prennent donc en charge toute analyse d’activité des utilisateurs. Vous n’avez pas besoin de cookies tiers pour comprendre l’activité sur site.

Pour plus d’informations, voir [À propos des cookies propriétaires](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html).

![Comparaison des cookies](/help/technotes/assets/cookies2.png)

## Qu’est-ce que l’attribut de cookie Même site et comment affecte-t-il les cookies Analytics ? {#samesite-effect}

Avec la sortie du navigateur Chrome 80 en février 2020 — et les versions successives des navigateurs Firefox et Edge — l’attribut de cookie MêmeSite applique la spécification de trois valeurs différentes qui régissent l’utilisation des cookies dans un contexte tiers :

* `None` : ce paramètre permet l’accès intersite et la transmission de cookies dans un contexte tiers. Pour spécifier cet attribut, vous devez également spécifier `Secure` et toutes les requêtes de navigateur doivent suivre le protocole HTTPS. Par exemple, lorsque vous définissez le cookie, vous associez les valeurs de l’attribut comme suit : `Set-Cookie: example_session=test12; SameSite=None; Secure`. S’ils ne sont pas correctement étiquetés, les cookies ne sont pas utilisables par les nouveaux navigateurs et sont rejetés.

* `Lax`: Permet l’envoi de requêtes intersites avec des cookies du même site uniquement pour la navigation de niveau supérieur avec des méthodes HTTP  *sécurisées*  (lecture seule, par exemple  `GET`).

* `Strict` : le cookie du même site n’est envoyé pour aucune requête de site web tiers. Le cookie n’est envoyé que si le site du cookie correspond au site dans la barre d’URL.

Le comportement par défaut dans ces versions de navigateur consiste à traiter les cookies qui n’ont pas d’attribut `SameSite`spécifié comme `SameSite=Lax`.

### Comment Analytics gère-t-il les attributs de cookie SameSite ?

Pour les clients qui utilisent le service d’identification des Visiteurs, les propriétés `SameSite=None` et `secure` sont définies par défaut, ce qui permet à ces cookies de prendre en charge les cas d’utilisation par des tiers.

Pour les clients qui utilisent des identifiants hérités Analytics (&quot;s_vi&quot; et &quot;s_fid&quot; cookies), les cookies sont également définis pour activer les cas d’utilisation tiers avec des domaines de collecte standard : adobedc.net, 2o7.net et omtrdc.net. Pour les clients qui utilisent une implémentation CNAME, Analytics définit `SameSite=Lax`.

>[!NOTE]
>
>Si vous possédez plusieurs domaines et utilisez le même CNAME pour la collecte de données sur tous vos domaines, le cookie est traité comme un cookie tiers sur ces autres domaines. Si vous utilisez les identifiants Analytics hérités, vous pouvez mettre à jour votre paramètre sur `SameSite=None` afin que ces cookies puissent être partagés sur l’ensemble de vos sites. Pour plus d’informations, voir &quot;[Modifier la valeur MêmeSite lorsque vous utilisez un CNAME pour plusieurs domaines](#samesite-one-cname)&quot; dans la section suivante.

Pour les navigateurs que Google a identifiés comme ne gérant pas correctement les cookies lorsque `SameSite` est défini sur `None`, `SameSite` est à la place désactivé.

Le tableau suivant récapitule les attributs Même site pour les cookies Analytics :

![Tableau des cookies](/help/technotes/assets/cookies1.png)

### Comment mon site peut-il répondre aux exigences de l&#39;attribut Même site ?

#### Servez toutes les pages de votre site avec HTTPS.

Vérifiez que votre configuration JavaScript utilise HTTPS pour tous les appels aux services d’Adobe.

Si votre site utilise le service d’ID de Visiteur Experience Cloud, le service redirige les appels HTTP tiers vers son point de terminaison HTTPS, ce qui peut augmenter la latence mais signifie que vous n’êtes pas tenu de modifier votre configuration.

#### Modifiez la valeur MêmeSite lorsque vous utilisez un CNAME pour plusieurs domaines {#samesite-one-cname}.

>[!NOTE]
>
>Les informations suivantes concernent uniquement les sites qui n’utilisent pas le service d’identification des Visiteurs Experience Cloud.

Si votre implémentation CNAME est définie dans le même domaine que votre site Web, le cookie est alors créé dans un contexte propriétaire et vous n’avez pas besoin d’apporter des modifications.

Cependant, si vous possédez plusieurs domaines et utilisez le même CNAME pour la collecte de données sur tous vos domaines, le cookie est traité comme un cookie tiers sur ces autres domaines. Avec Chrome 80 et les versions ultérieures, il n’est plus visible sur ces autres domaines. Pour rendre le comportement plus similaire dans tous les navigateurs, Analytics a explicitement défini la valeur `SameSite` de ce cookie sur `Lax`. Si vous utilisez ce cookie dans un contexte tiers convivial, vous devez définir le cookie avec la valeur `SameSite=None`, ce qui signifie également que vous devez toujours utiliser HTTPS. Si vous ne l’avez pas déjà fait, contactez le service à la clientèle Adobe pour que la valeur MêmeSite soit modifiée pour vos CNAME sécurisés.

## Comment puis-je déterminer si les modifications de Safari affectent mon activité ? {#measure-itp-effect}

Adobe recommande aux clients de mesurer l’impact dans leur propre société avant de modifier la collecte de données. Vous pouvez utiliser Analysis Workspace pour mesurer l&#39;impact de la prévention du suivi ITP sur votre entreprise :

* Mesurez le pourcentage de votre trafic à partir des navigateurs gérés par ITP :

   1. Créez un segment pour voir combien de visiteurs utilisent une plateforme ITP.

      >[!NOTE]
      >
      >Les navigateurs concernés par ITP dépendent de l’utilisation ou non d’une implémentation CNAME. Voir &quot;[Calendrier des modifications majeures apportées à la stratégie ITP](#ITP-timeline)&quot; pour plus de détails.

      ![Segment pour les visiteurs ITP](/help/technotes/assets/itp-visitor-segment.png)

   2. Appliquez le segment au nombre de visites pour comprendre l’utilisation relative de Safari dans votre base d’utilisateurs. Cela vous permet de créer un tableau comme celui-ci :

      ![Pourcentage de visites effectuées par des visiteurs du PTI](/help/technotes/assets/visits-vs-safari-visits.png)

* Mesurez le pourcentage de visiteurs utilisant des navigateurs non Safari qui ne reviennent pas dans les sept jours. Si vos visiteurs non Safari reviennent plusieurs fois dans les sept jours, votre trafic Safari peut ne pas être affecté de manière significative.

   1. Créez un segment comme celui-ci pour le trafic non Safari.

      ![Segment destiné aux visiteurs qui reviennent après sept jours](/help/technotes/assets/visits-after-seven-days.png)

   2. Appliquez le segment au nombre de visites pour comprendre l’utilisation relative de Safari dans votre base d’utilisateurs. Cela vous permet de créer un tableau comme celui-ci :

      ![Pourcentage de visiteurs qui reviennent après sept jours](/help/technotes/assets/percent-visits-after-seven-days.png)

### Méthodes d’ajustement des données au cours du rapports

Si votre entreprise est affectée par la prévention du suivi ITP, vous pouvez envisager les mesures suivantes pour ajuster vos données pendant le rapports.

* Créez un segment pour filtrer les utilisateurs ITP.

   ![Segment pour les visiteurs non-ITP](/help/technotes/assets/non-itp-visitor-segment.png)

* Créez une mesure calculée à ajuster pour tenir compte de l’inflation visiteuse connue.

   ![Mesure calculée à ajuster pour l&#39;inflation visiteuse](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Options permettant d’atténuer l’effet des limitations des cookies du navigateur](cookieless.md)
>[L&#39;impact du nouveau cadre de transparence du suivi d&#39;application d&#39;Apple sur Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
