---
title: Paramètres de requête de la collecte de données
description: Répertorie tous les paramètres de chaîne de requête utilisés dans les demandes d’image.
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/aB92GXPxYSkjcDD9wi0vj47jijqndMbOGaECvXs38-Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 725
ht-degree: 92%

---

# Paramètres de requête de la collecte de données

Le tableau suivant répertorie tous les paramètres de chaîne de requête utilisés par Adobe dans les demandes d’image. Ces informations peuvent être utilisées lors du débogage à l’aide des [analyseurs de paquets](packet-monitor.md), lors de la [demande d’image codée en dur](../other/hardcoded.md) ou lors de l’utilisation de [variables dynamiques](../vars/page-vars/dynamic-variables.md).

| Paramètre | Variable de mise en œuvre Analytics | Description |
| --- | --- | --- |
| `aamlh` | Aucun | Indicateur d’emplacement Audience Manager. Utilisé dans l’intégration du profil partagé d’entreprise CX. |
| `aamb` | Aucun | Audience Manager blob. Utilisé dans l’intégration du profil partagé d’entreprise CX. |
| `aid` | Aucun | Identifiant visiteur Analytics. |
| `AQB` | Aucun | Indique le début d’une chaîne de requête de demande d’image. |
| `AQE` | Aucun | Indique la fin d’une demande d’image, ce qui signifie que la demande n’a pas été tronquée. |
| `bh` | Aucun | Hauteur du navigateur (en pixels). Utilisé dans la dimension [Hauteur du navigateur](/help/components/dimensions/browser-height.md). |
| `bw` | Aucun | Largeur du navigateur (en pixels). Utilisé dans la dimension [Largeur du navigateur](/help/components/dimensions/browser-width.md). |
| `c` | Aucun | Qualité des couleurs (en bits). Utilisé dans la dimension [Profondeur de couleur](/help/components/dimensions/color-depth.md). |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indique le début des variables de données contextuelles. Ne contient jamais de valeur. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indique la fin des variables de données contextuelles. Ne contient jamais de valeur. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md) ou variables de trafic personnalisées. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Type de devise utilisée sur l’accès. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Nombre de points dans un domaine. Permet de stocker correctement les cookies. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Codage de caractères de la demande d’image. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Durée de vie du cookie visiteur. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Utilisé dans la dimension [Section du site](/help/components/dimensions/site-section.md). |
| `cp` | Aucun | Utilisé dans la dimension [Type d’accès](/help/components/dimensions/hit-type.md). |
| `ct` | Aucun | Utilisé dans la dimension [Type de connexion](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indique ce qu’il faut utiliser pour les variables dynamiques. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Raccourci pour la chaîne de requête `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Liste d’événements séparés par des virgules sur la page. Utilisé par la plupart des [mesures](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | URL actuelle de la page, jusqu’à 255 octets. Utilisé dans la dimension [URL de page](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | Les URL de plus de 255 octets sont fractionnées. Les 255 premiers octets apparaissent dans le paramètre `g` et tous les autres dans le paramètre `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Raccourci pour la chaîne de requête `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Raccourci pour la chaîne de requête `pageType`. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Préfixe pour plusieurs variables qui représentent les [Indications du client](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Dimensions hiérarchiques. |
| `hp` | Aucun | N’est plus utilisé. Dans les versions précédentes d’Adobe Analytics, déterminez si l’URL active était la page d’accueil du navigateur. |
| `j` | Aucun | Version JavaScript installée dans le navigateur. |
| `k` | Aucun | Utilisé dans la dimension [Prise en charge des cookies](/help/components/dimensions/cookie-support.md). |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variables de liste. |
| `lrt` | Aucun | Le « délai de la dernière requête », qui correspond au délai d’aller-retour de la dernière requête, en millisecondes. Elle est envoyée uniquement lorsque plusieurs requêtes proviennent d’une page ou lorsque la page est une application monopage. |
| `mid` | Aucun | Identifiant visiteur de l’entreprise CX. |
| `ndh` | Aucun | Indicateur précisant si la demande d’image provient d’AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Permet de déterminer l’emplacement des cookies. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificateur d’objet de la dernière page. Utilisé dans Activity Map. |
| `ot` | Aucun | Nom d’objet de la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `p` | Aucun | N’est plus utilisé. Liste des plug-ins utilisés dans le navigateur. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Utilisé dans la dimension [Page](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Utilisé dans la dimension [Pages introuvables](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Aucun | Défini uniquement pour les nouveaux visiteurs et toujours sur `true`. Permet d’empêcher les redirections infinies si un visiteur ou une visiteuse rejette les cookies. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Détermine le type de lien personnalisé. Requis pour les [liens personnalisés](/help/components/dimensions/custom-link.md), les [liens de téléchargement](/help/components/dimensions/download-link.md) et les [liens de sortie](/help/components/dimensions/exit-link.md). |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | URL sur laquelle le lien personnalisé s’est produit. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Nom convivial du lien personnalisé. |
| `pev3` | Aucun | N’est plus utilisé. Jalons suivis dans les versions précédentes des rapports vidéo. |
| `pf` | Aucun | Indicateur de plateforme ; pour utilisation par Adobe uniquement. Ne pas modifier. |
| `pid` | Aucun | Identifiant de page pour la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `pidt` | Aucun | Type d’identificateur de page pour la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Raccourci pour la chaîne de requête `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variable products. Utilisé dans les dimensions [Produit](/help/components/dimensions/product.md) et [Catégorie](/help/components/dimensions/category.md). |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Permet de dédupliquer les achats. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL de l’accès référent. Utilisé dans les dimensions de sources de trafic, telles que [Référent](/help/components/dimensions/referrer.md) et [Domaine référent](/help/components/dimensions/referring-domain.md). |
| `s` | Aucun | Résolution d’écran, dans `width x height`. Utilisé dans la dimension [Résolutions d’écran](/help/components/dimensions/monitor-resolution.md). |
| `server` | [`server`](../vars/page-vars/server.md) | Dimension [Serveur](/help/components/dimensions/server.md). |
| `sv` | [`server`](../vars/page-vars/server.md) | Raccourci pour la chaîne de requête `server`. |
| `state` | [`state`](../vars/page-vars/state.md) | Dimension État. |
| `t` | Aucun | Date/heure générée de l’accès. Utilise le format `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` correspond à la date/l’heure dans JavaScript. Le mois `0` est janvier, tandis que le mois `11` est décembre.<br>- `w` est le jour de la semaine. `0` est dimanche, tandis que `6` est samedi.<br>- `o` est le décalage GMT négatif en minutes. Par exemple, `420` désigne GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | L’horodatage personnalisé défini avec l’accès. Généralement utilisé pour le suivi hors ligne. |
| `v` | Aucun | Utilisé dans la dimension [Compatible Java](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | Dimension [Code de suivi](/help/components/dimensions/tracking-code.md). |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md) ou dimensions de conversion personnalisées. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variable d’identifiant visiteur. |
| `vidn` | Aucun | Défini par AppMeasurement pour les nouveaux visiteurs et visiteuses. Contient la valeur de l’identifiant stockée dans le cookie du visiteur. |
| `vmk` | `vmk` | N’est plus utilisé. Clé de migration de visite, qui a permis de faire migrer des implémentations de cookies tiers vers des cookies internes. |
| `vvp` | `variableProvider` | Utilisé dans Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Utilisé avec les sources de données pour associer les données en ligne et hors ligne. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Utilisé dans la dimension [Code postal](/help/components/dimensions/zip-code.md). |
