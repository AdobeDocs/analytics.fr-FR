---
title: Adobe Analytics et les cookies de navigateur
description: Découvrez comment les mesures de prévention du suivi affectent les cookies tiers et propriétaires définis par Adobe Analytics.
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
role: Admin
source-git-commit: ac9221bd7d9397ed0f085245663f1f0056f7d68f
workflow-type: tm+mt
source-wordcount: '1909'
ht-degree: 100%

---

# Adobe Analytics et les cookies de navigateur

Ce document explique comment les mesures de prévention du suivi des principaux navigateurs affectent les cookies tiers et propriétaires définis par Adobe Analytics. Il comprend des informations sur le programme ITP (Intelligent Tracking Prevention) d’Apple, ainsi que sur les restrictions de Chrome sur les cookies tiers via l’attribut SameSite.

## Comment les navigateurs ont-ils limité l’utilisation des cookies ?

>[!NOTE]
>Les [analyses entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr#cda) et l’[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr#comparing-cja-to-traditional-adobe-analytics) peuvent regrouper les cookies à l’aide d’un identifiant personnel, tel qu’un identifiant de connexion haché, si disponible.

### Limitations des cookies tiers

Les cookies utilisés dans un contexte tiers sont largement abandonnés. Firefox et Safari ont commencé à bloquer par défaut les cookies tiers à partir de 2019 pour Firefox et de 2020 pour Safari Chrome a annoncé son intention d’arrêter la prise en charge des cookies tiers en 2023. Quand ils arrêteront, les cookies tiers seront inutilisables.

De plus, Chrome ne permet aujourd’hui aux cookies de fonctionner dans un contexte tiers que si l’attribut « SameSite » est défini sur Aucun et que les cookies sont étiquetés comme sécurisés, ce qui signifie qu’ils ne peuvent être utilisés que sur des sites HTTPS. Pour plus d’informations, reportez-vous à la section « [Qu’est-ce que l’attribut de cookie SameSite et comment affecte-t-il Analytics ?](#samesite-effect) »

#### Quels cookies tiers Adobes sont affectés ?

Le service d’identification des visiteurs utilise le cookie « [demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=fr) » pour fournir un identifiant persistant pour les visiteurs dans différents domaines client. Le service d’identification Analytics hérité, le cookie « s_vi », est défini comme cookie tiers pour les implémentations n’utilisant pas de domaine de collecte CNAME personnalisé.

Dans les navigateurs où les cookies tiers sont bloqués, le suivi interdomaines n’est pas disponible.

### Limitations des cookies propriétaires {#limitations-first-party-cookies}

Les cookies propriétaires sont autorisés sur tous les navigateurs principaux. Cependant, Apple limite la durée de vie des cookies propriétaires définis par Adobe par le biais de son programme de suivi intelligent (ITP). Cela affecte Safari ainsi que tous les navigateurs sur iOS et iPadOS.

Les cookies propriétaires d’Adobe sont limités à un délai d’expiration de sept jours ou, pour les clics publicitaires qu’Apple détermine comme provenant de dispositifs de suivi, un délai d’expiration de 24 heures. Avec un délai d’expiration de sept jours, si un utilisateur visite votre site et revient dans les sept jours, alors la date d’expiration du cookie est prolongée de sept jours supplémentaires. Cependant, si un utilisateur visite votre site et revient huit jours plus tard, alors il est traité comme un nouvel utilisateur lors de la deuxième visite.

Actuellement, les politiques ITP s’appliquent à tous les cookies propriétaires définis par Adobe, que vous utilisiez le service d’identification des visiteurs ou l’identifiant Analytics hérité (cookie « s_vi »). À un moment donné, ces politiques ne s’appliquaient qu’aux cookies définis côté client et non aux cookies définis côté serveur via une implémentation CNAME. Toutefois, en novembre 2020, ITP a été mis à jour pour s’appliquer également aux implémentations CNAME.

#### Calendrier des modifications majeures apportées à la politique ITP {#ITP-timeline}

* Février 2019 avec [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) : les cookies côté client étaient limités à un délai d’expiration de sept jours.
* Avril 2019 avec [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) : les cookies côté client étaient limités à 24 heures pour les clics publicitaires lorsque le domaine référent était a) impliqué dans le suivi intersite et b) que l’URL finale contenait une chaîne de requête ou un identifiant de fragment.
* Novembre 2020 avec [CNAME Cloaking and Bounce Tracking Defense](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/) (CNAME cloaking et défense du dispositif de suivi Bounce) : Les limitations d’ITP ont été étendues aux implémentations CNAME.

Les politiques d’ITP évoluent fréquemment. Pour connaître les dernières politiques, voir [Prévention du suivi d’Apple dans Webkit](https://webkit.org/tracking-prevention).

#### Quels cookies propriétaires d’Adobe sont affectés ?

Tous les cookies propriétaires définis par Adobe et les bibliothèques JavaScript associées sont affectés par les politiques ITP :

* [Les cookies « AMCV »](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=fr) définis par la bibliothèque de service de l’identifiant visiteur d’Adobe Experience Cloud.
* Le cookie hérité d’Analytics [« s_vi »](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=fr) lorsqu’il est configuré avec la collecte de données propriétaires à l’aide d’un CNAME
* Le cookie hérité d’Analytics [« s_fid »](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=fr), qui est le cookie de secours utilisé lorsque « s_vi » ne peut pas être défini

#### Quel est l’impact d’ITP sur Safari pour Analytics ?

L’impact des restrictions d’ITP peut varier considérablement en fonction du comportement de vos utilisateurs. Seuls les visiteurs qui utilisent un navigateur affecté par ITP (par exemple, Safari) et qui reviennent après une absence de sept jours sont affectés. Si les visiteurs n’utilisent pas de navigateur ITP ou reviennent dans les sept jours, ils ne sont pas affectés. Il est important de passer en revue vos propres données dans Analytics pour comprendre l’ampleur de l’impact de cette restriction. Pour obtenir des conseils sur la manière de mesurer l’impact d’ITP sur vos sites, consultez « [Comment puis-je déterminer si les modifications de Safari affectent mon entreprise ?](#measure-itp-effect) »

Si ces restrictions affectent vos données, vous verrez :

1. Une augmentation du nombre de visiteurs, car les visiteurs qui reviennent sont traités comme de nouveaux visiteurs puisque leurs cookies ont expiré. Toutes les mesures basées sur la mesure Visiteur (telles que les Ventes par visiteur) sont également affectées.
2. Des modifications apportées à l’attribution. L’attribution repose sur le fait de lier les événements de conversion aux activités précédentes par le même visiteur. Une fois qu’un cookie expire, les événements suivants sont associés à un nouveau visiteur. Les activités du nouveau visiteur ne peuvent pas être liées aux activités du visiteur précédent.

>[!NOTE]
>
>Actuellement, les technologies ITP ne s’appliquent pas aux navigateurs intégrés dans les applications mobiles.

## Quelle est la différence entre les cookies tiers et les cookies propriétaires ?

### Cookies tiers

Les cookies tiers ne sont pas créés par les sites que visitent les utilisateurs.

Bien que les navigateurs traitent actuellement tous les cookies tiers de la même manière et les stockent en conséquence, les cookies tiers peuvent se comporter de différentes façons. Avec l’implémentation des cookies tiers Analytics d’un client ou d’une cliente, les navigateurs stockent l’identifiant [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=fr) d’Adobe en tant que cookie tiers, mais le client n’effectue des appels qu’à Adobe, et non à des domaines tiers inconnus ou suspects. Ce cookie fournit des identifiants persistants sur plusieurs domaines et permet d’obtenir du contenu sécurisé (HTTPS). Pour plus d’informations, voir [Cookies et Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=fr).

Dans les implémentations d’Analytics, les cookies tiers sont utilisés pour le suivi interdomaines et pour les cas d’utilisation publicitaire, y compris les annonces de reciblage. Les cookies tiers vous permettent d’identifier les visiteurs qui visitent différents domaines que vous possédez ou qui voient des annonces sur des sites que vous ne possédez pas.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### Cookies propriétaires

Les cookies propriétaires sont spécifiques au domaine et sont créés par les sites Web clients et stockés dans les navigateurs clients lorsque les utilisateurs visitent les sites Web. Tous les navigateurs acceptent généralement les cookies propriétaires, bien que [Safari limite l’expiration de certains types de cookies propriétaires](#limitations-first-party-cookies).

Dans les implémentations Analytics, les cookies propriétaires sont utilisés pour identifier les utilisateurs lorsqu’ils se trouvent sur votre site et donc pour prendre en charge toute analyse de l’activité des utilisateurs. Vous n’avez pas besoin de cookies tiers pour comprendre l’activité sur le site.

Pour plus d’informations, voir [À propos des cookies propriétaires](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=fr).

![Comparaison des cookies](/help/technotes/assets/cookies2.png)

## Qu’est-ce que l’attribut de cookie SameSite et comment affecte-t-il les cookies Analytics ? {#samesite-effect}

Avec la sortie du navigateur Chrome 80 en février 2020 (et les versions successives des navigateurs Firefox et Edge), l’attribut de cookie SameSite applique la spécification de trois valeurs différentes qui régissent l’utilisation des cookies dans un contexte tiers :

* `None` : ce paramètre permet l’accès intersite et la transmission de cookies dans un contexte tiers. Pour spécifier cet attribut, vous devez également spécifier `Secure` et toutes les requêtes de navigateur doivent suivre le protocole HTTPS. Par exemple, lorsque vous définissez le cookie, vous associez les valeurs de l’attribut comme suit : `Set-Cookie: example_session=test12; SameSite=None; Secure`. S’ils ne sont pas correctement étiquetés, les cookies sont inutilisables par les navigateurs les plus récents et sont rejetés.

* `Lax` : permet d’envoyer des requêtes intersites avec les cookies d’un même site, uniquement pour la navigation de niveau supérieur avec des méthodes HTTP *sécurisées* (lecture seule, par exemple `GET`).

* `Strict` : le cookie du même site n’est envoyé pour aucune requête de site web tiers. Le cookie n’est envoyé que si le site du cookie correspond au site dans la barre d’URL.

Le comportement par défaut dans ces versions de navigateur consiste à traiter les cookies qui n’ont pas d’attribut `SameSite`spécifié comme `SameSite=Lax`.

### Comment Analytics gère-t-il les attributs de cookie SameSite ?

Pour les clients qui utilisent le service d’identification des visiteurs, les cookies ont les propriétés `SameSite=None` et `secure` définis par défaut, ce qui leur permet de prendre en charge les cas d’utilisation tiers.

Pour les personnes qui utilisent des identifiants Analytics hérités (cookies `s_vi` et `s_fid`), les cookies sont également définis pour activer les cas d’utilisation tiers avec des domaines de collecte standard : `adobedc.net`, `2o7.net` et `omtrdc.net`. Pour les clients qui utilisent une implémentation CNAME, Analytics définit `SameSite=Lax`.

>[!NOTE]
>
>Si vous possédez plusieurs domaines et utilisez le même CNAME pour la collecte de données sur tous vos domaines, alors le cookie est traité comme un cookie tiers sur ces autres domaines. Si vous utilisez les identifiants Analytics hérités, vous pouvez mettre à jour votre paramètre sur `SameSite=None` afin que ces cookies puissent être partagés sur l’ensemble de vos sites. Pour plus d’informations, voir la section suivante : « [Modifier la valeur SameSite lorsque vous utilisez un CNAME pour plusieurs domaines](#samesite-one-cname) ».

Dans le cas des navigateurs que Google a identifiés comme ne gérant pas correctement les cookies lorsque `SameSite` est défini sur `None`, `SameSite` n’est pas défini.

Le tableau suivant résume les attributs SameSite pour les cookies Analytics :

![Tableau des cookies](/help/technotes/assets/cookies1.png)

### Comment mon site peut-il répondre aux exigences de l’attribut SameSite ?

#### Utilisez HTTPS sur toutes les pages de vos sites

Vérifiez que votre configuration JavaScript utilise HTTPS pour tous les appels aux services d’Adobe.

Si votre site utilise le service d’identification des visiteurs Experience Cloud, le service redirige les appels HTTP tiers vers son point d’entrée HTTPS, ce qui peut augmenter la latence, mais signifie que vous n’êtes pas tenu de modifier votre configuration.

#### Modifiez la valeur SameSite lorsque vous utilisez un CNAME pour plusieurs domaines {#samesite-one-cname}

>[!NOTE]
>
>Les informations suivantes ne concernent que les sites qui n’utilisent pas le service d’identification des visiteurs Experience Cloud.

Si vous avez une implémentation CNAME définie dans le même domaine que votre site Web, alors le cookie est créé dans un contexte de propriétaire et vous n’avez pas besoin d’apporter de modifications.

Cependant, si vous possédez plusieurs domaines et utilisez le même CNAME pour la collecte de données sur tous vos domaines, alors le cookie est traité comme un cookie tiers sur ces autres domaines. Avec la version Chrome 80 ou ultérieure, il n’est plus visible sur ces autres domaines. Pour rendre le comportement plus similaire sur tous les navigateurs, Analytics a défini explicitement la valeur `SameSite` de ce cookie sur `Lax`. Si vous utilisez ce cookie dans un contexte tiers convivial, vous devez définir le cookie avec la valeur `SameSite=None`, ce qui signifie également que vous devez toujours utiliser HTTPS. Si vous ne l’avez pas déjà fait, contactez l’assistance clientèle d’Adobe pour que la valeur SameSite soit modifiée pour vos CNAME sécurisés.

## Comment puis-je déterminer si les modifications de Safari affectent mon entreprise ?  {#measure-itp-effect}

Adobe recommande aux clients de mesurer l’impact au sein de leur propre entreprise avant de modifier la collecte de données. Vous pouvez utiliser Analysis Workspace pour mesurer l’impact de la prévention du suivi ITP sur votre entreprise :

* Mesurez le pourcentage de votre trafic à partir des navigateurs régis par ITP :

   1. Créez un segment pour voir le nombre de visiteurs qui utilisent une plateforme ITP.

      >[!NOTE]
      >
      >Les navigateurs spécifiques affectés par ITP dépendent de si vous utilisiez une implémentation CNAME ou non. Pour plus d’informations, voir « [Calendrier des modifications majeures apportées à la politique ITP](#ITP-timeline) ».

      ![Segment pour les visiteurs ITP](/help/technotes/assets/itp-visitor-segment.png)

   2. Appliquez le segment au nombre de visites pour comprendre l’utilisation relative de Safari dans votre base d’utilisateurs. Vous pouvez ainsi créer un tableau de ce type :

      ![Pourcentage de visites par visiteurs ITP](/help/technotes/assets/visits-vs-safari-visits.png)

* Mesurez le pourcentage de visiteurs utilisant des navigateurs autres que Safari qui ne reviennent pas dans les sept jours. Si vos visiteurs qui n’utilisent pas Safari reviennent plusieurs fois dans les sept jours, votre trafic Safari peut ne pas être affecté de manière significative.

   1. Créez un segment comme celui-ci pour le trafic qui ne vient pas de Safari.

      ![Segment pour les visiteurs qui reviennent après sept jours](/help/technotes/assets/visits-after-seven-days.png)

   2. Appliquez le segment au nombre de visites pour comprendre l’utilisation relative de Safari dans votre base d’utilisateurs. Vous pouvez ainsi créer un tableau de ce type :

      ![Pourcentage de visiteurs qui reviennent après sept jours](/help/technotes/assets/percent-visits-after-seven-days.png)

### Méthodes d’ajustement des données lors de la création de rapports

Si votre entreprise est affectée par la prévention du suivi ITP, vous pouvez envisager les mesures suivantes pour ajuster vos données lors de la création de rapports.

* Créez un segment pour filtrer les utilisateurs ITP.

  ![Segment pour les visiteurs non ITP](/help/technotes/assets/non-itp-visitor-segment.png)

* Créez une mesure calculée pour ajuster le gonflement connu des visiteurs.

  ![Mesure calculée pour ajuster le gonflement des visiteurs](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Options pour atténuer l’effet des restrictions des cookies de navigateur](cookieless.md)
>[Impact du nouveau cadre de transparence du suivi des applications d’Apple sur Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833?profile.language=fr)
