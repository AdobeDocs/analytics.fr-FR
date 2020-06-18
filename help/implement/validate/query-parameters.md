---
title: Paramètres de requête de la collecte de données
description: Répertorie tous les paramètres de chaîne de requête utilisés dans les demandes d’image.
translation-type: tm+mt
source-git-commit: edf3ac3ebc99444b86bcd9239cef9ed84d797565
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 75%

---


# Paramètres de requête de la collecte de données

Le tableau suivant répertorie tous les paramètres de chaîne de requête utilisés par Adobe dans les demandes d’image. Ces informations peuvent être utilisées lors du débogage à l’aide des [analyseurs de paquets](packet-monitor.md), lors de la [demande d’image codée en dur](../other/hardcoded.md) ou lors de l’utilisation de [variables dynamiques](../vars/page-vars/dynamic-variables.md).

| Paramètre | Variable de mise en œuvre Analytics | Description |
| --- | --- | --- |
| `aamlh` | Aucun | Conseil relatif à l’emplacement d’Audience Manager utilisé dans l’intégration du profil partagé d’Experience Cloud. |
| `aamb` | Aucun | Audience Manager Blob utilisé dans l’intégration du profil partagé d’Experience Cloud. |
| `aid` | Aucun | Identifiant visiteur Analytics. |
| `AQB` | Aucun | Indique le début d’une chaîne de requête de demande d’image. |
| `AQE` | Aucun | Indique la fin d’une demande d’image, ce qui signifie que la demande n’a pas été tronquée. |
| `bh` | Aucun | Hauteur du navigateur (en pixels). Used in the [Browser height](/help/components/dimensions/browser-height.md) dimension. |
| `bw` | Aucun | Largeur du navigateur (en pixels). Used in the [Browser width](/help/components/dimensions/browser-width.md) dimension. |
| `c` | Aucun | Qualité des couleurs (en bits). Used in the [Color depth](/help/components/dimensions/color-depth.md) dimension. |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indique le début des variables de données contextuelles. Ne contient jamais de valeur. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indique la fin des variables de données contextuelles. Ne contient jamais de valeur. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md)ou variables de trafic personnalisées. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Type de devise utilisée sur l’accès. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Nombre de points dans un domaine. Permet de stocker correctement les cookies. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Codage de caractères de la demande d’image. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Durée de vie du cookie visiteur. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Used in the [Site sections](/help/components/dimensions/site-section.md) dimension. |
| `cp` | Aucun | Used in the [Hit Type](/help/components/dimensions/hit-type.md) dimension. |
| `ct` | Aucun | Used in the [Connection Type](/help/components/dimensions/connection-type.md) dimension. |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indique ce qu’il faut utiliser pour les variables dynamiques. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Raccourci pour la chaîne de requête `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Liste d’événements séparés par des virgules sur la page. Utilisée par la plupart des [mesures](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | URL actuelle de la page, jusqu’à 255 octets. Used in the [Page URL](/help/components/dimensions/page-url.md) dimension. |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | Les URL de plus de 255 octets sont fractionnées. Les 255 premiers octets apparaissent dans le paramètre `g` et tous les autres dans le paramètre `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Raccourci pour la chaîne de requête `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Raccourci pour la chaîne de requête `pageType`. |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Dimensions hiérarchiques. |
| `hp` | Aucun | N’est plus utilisé. Dans les versions précédentes d’Adobe Analytics, déterminez si l’URL active était la page d’accueil du navigateur. |
| `j` | Aucun | Version JavaScript installée dans le navigateur. |
| `k` | Aucun | Used in the [Cookie support](/help/components/dimensions/cookie-support.md) dimension. |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variables de liste. |
| `mid` | Aucun | Identifiant visiteur Experience Cloud. |
| `ndh` | Aucun | Indicateur précisant si la demande d’image provient d’AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Permet de déterminer l’emplacement des cookies. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificateur d’objet de la dernière page. Utilisé dans Activity Map. |
| `ot` | Aucun | Nom d’objet de la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `p` | Aucun | N’est plus utilisé. Liste des plug-ins utilisés dans le navigateur. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Used in the [Page](/help/components/dimensions/page.md) dimension. |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Used in the [Pages not found](/help/components/dimensions/pages-not-found.md) dimension. |
| `pccr` | Aucun | Défini uniquement pour les nouveaux visiteurs et toujours sur `true`. Permet d’empêcher les redirections infinies. |
| `pe` | [`linkType`](../vars/config-vars/linktype.md) | Détermine le type de lien personnalisé. Requis pour les liens [](/help/components/dimensions/custom-link.md)personnalisés, les liens [de](/help/components/dimensions/download-link.md)téléchargement et les liens [de](/help/components/dimensions/exit-link.md)sortie. |
| `pev1` | Aucun | URL sur laquelle le lien personnalisé s’est produit. |
| `pev2` | [`linkName`](../vars/config-vars/linkname.md) | Nom convivial du lien personnalisé. |
| `pev3` | Aucun | N’est plus utilisé. Jalons suivis dans les versions précédentes des rapports vidéo. |
| `pf` | Aucun | Indicateur de plateforme ; pour utilisation par Adobe uniquement. Ne pas modifier. |
| `pid` | Aucun | Identifiant de page pour la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `pidt` | Aucun | Type d’identificateur de page pour la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Raccourci pour la chaîne de requête `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variable products. Utilisé dans les dimensions [Produit](/help/components/dimensions/product.md) et [Catégorie](/help/components/dimensions/category.md) . |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Permet de dédupliquer les achats. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL de l’accès référent. Utilisé dans les dimensions de sources de trafic, telles que [Parrain](/help/components/dimensions/referrer.md) et domaine [référent](/help/components/dimensions/referring-domain.md) |
| `s` | Aucun | Résolution d’écran, dans `width x height`. Used in the [Monitor resolutions](/help/components/dimensions/monitor-resolution.md) dimension. |
| `server` | [`server`](../vars/page-vars/server.md) | [Dimension Serveur.](/help/components/dimensions/server.md) |
| `sv` | [`server`](../vars/page-vars/server.md) | Raccourci pour la chaîne de requête `server`. |
| `state` | [`state`](../vars/page-vars/state.md) | Dimension État. |
| `t` | Aucun | Date/heure générée de l’accès. Utilise le format `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` désigne la date/l’heure dans JavaScript. Le mois `0` est janvier, tandis que le mois `11` est décembre.<br>- `w` désigne le jour de la semaine. `0` désigne le dimanche, tandis que `6` désigne le samedi.<br>- `o` désigne le décalage GMT négatif en minutes. Par exemple, `420` désigne GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | L’horodatage personnalisé défini avec l’accès. Généralement utilisé pour le suivi hors ligne. |
| `v` | Aucun | Used in the [Java enabled](/help/components/dimensions/java-enabled.md) dimension. |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [Dimension Code de suivi.](/help/components/dimensions/tracking-code.md) |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md)ou dimensions de conversion personnalisées. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variable d’identifiant visiteur. |
| `vmk` | `vmk` | N’est plus utilisé. Clé de migration des Visiteurs, qui a aidé à migrer les implémentations de cookies tiers vers des cookies propriétaires. |
| `vvp` | `variableProvider` | Utilisé dans Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Utilisée avec la fonctionnalité Sources de données pour associer les données en ligne et hors ligne. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Used in the [Zip code](/help/components/dimensions/zip-code.md) dimension. |
