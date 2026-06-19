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
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 1079
ht-degree: 44%

---

# Paramètres de requête de la collecte de données

Le tableau suivant répertorie tous les paramètres de chaîne de requête utilisés par Adobe dans les demandes d’image. Ces informations sont utiles lors du débogage avec les [analyseurs de paquets](packet-monitor.md), lors du [codage de requêtes d’images](../other/hardcoded.md) ou lors de l’utilisation de [variables dynamiques](../vars/page-vars/dynamic-variables.md).

| Paramètre | Variable de mise en œuvre Analytics | Description |
| --- | --- | --- |
| `aamlh` | Aucun | Indicateur d’emplacement Audience Manager. Identifie le centre de données régional utilisé pour la synchronisation des Audience Manager ID via le service Experience Cloud ID. |
| `aamb` | Aucun | Audience Manager blob. Données de profil Audience Manager codées transmises lors de la synchronisation des identifiants via le service Experience Cloud ID. |
| `aid` | Aucun | Identifiant visiteur Analytics hérité, stocké dans le cookie `s_vi`. Remplacé par le paramètre `mid` dans les implémentations modernes. |
| `AQB` | Aucun | Indique le début d’une chaîne de requête de demande d’image. |
| `AQE` | Aucun | Indique la fin d’une demande d’image, ce qui signifie que la demande n’a pas été tronquée. |
| `bh` | Aucun | Hauteur du navigateur (en pixels). Utilisé dans la dimension [[!UICONTROL Hauteur du navigateur]](/help/components/dimensions/browser-height.md). |
| `bw` | Aucun | Largeur du navigateur (en pixels). Utilisé dans la dimension [[!UICONTROL Largeur du navigateur]](/help/components/dimensions/browser-width.md). |
| `c` | Aucun | Qualité des couleurs (en bits). Utilisé dans la dimension [[!UICONTROL Profondeur de couleur]](/help/components/dimensions/color-depth.md). |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indique le début des variables de données contextuelles. Ne contient jamais de valeur. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indique la fin des variables de données contextuelles. Ne contient jamais de valeur. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md) ou variables de trafic personnalisées. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Type de devise utilisée sur l’accès. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Plus utilisé.** Nombre de points dans un domaine. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Codage de caractères de la demande d’image. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Durée de vie du cookie visiteur. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Utilisé dans la dimension [[!UICONTROL Section du site]](/help/components/dimensions/site-section.md). |
| `cp` | [`customerPerspective`](../vars/page-vars/customerperspective.md) | Indique si un accès à l’application mobile s’est produit alors que l’application était en premier plan ou en arrière-plan. Utilisé dans la dimension [[!UICONTROL Type d’accès]](/help/components/dimensions/hit-type.md). |
| `ct` | Aucun | Utilisé dans la dimension [[!UICONTROL Type de connexion]](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indique ce qu’il faut utiliser pour les variables dynamiques. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Abrégé pour le paramètre `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Liste d’événements séparés par des virgules sur la page. Utilisé par la plupart des [mesures](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | URL actuelle de la page, jusqu’à 255 octets. Utilisé dans la dimension [[!UICONTROL URL de page]](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../vars/page-vars/pageurl.md) | Les URL de plus de 255 octets sont fractionnées. Les 255 premiers octets apparaissent dans le paramètre `g` et tous les autres dans le paramètre `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Abrégé pour le paramètre `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Abrégé pour le paramètre `pageType`. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Préfixe pour plusieurs variables qui représentent les [Indications du client](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/page-variables.md#retired-page-variables) | **Plus utilisé.** Dimensions hiérarchiques. |
| `hp` | Aucun | **Plus utilisé.** Dans les versions précédentes d’Adobe Analytics, déterminez si l’URL active était la page d’accueil du navigateur. |
| `j` | Aucun | **Plus utilisé.** Version JavaScript installée dans le navigateur. |
| `k` | Aucun | Utilisé dans la dimension [[!UICONTROL Prise en charge des cookies]](/help/components/dimensions/cookie-support.md). |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variables de liste. |
| `lat` | Aucun | **Plus utilisé.** Latitude. Définies par les implémentations mobiles SDK héritées ; les implémentations mobiles actuelles envoient la géolocalisation par le biais de flux de données. |
| `lon` | Aucun | **Plus utilisé.** Longitude. Définies par les implémentations mobiles SDK héritées ; les implémentations mobiles actuelles envoient la géolocalisation par le biais de flux de données. |
| `lrt` | Aucun | Le « délai de la dernière requête », qui correspond au délai d’aller-retour de la dernière requête, en millisecondes. Elle est envoyée uniquement lorsque plusieurs requêtes sont envoyées à partir d’une seule page, par exemple dans une application d’une seule page (SPA). |
| `mcorgid` | Aucun | L’ID d’organisation Experience Cloud, qui identifie l’organisation pour le service Experience Cloud ID. |
| `mid` | Aucun | Utilisé dans la dimension [[!UICONTROL Identifiant visiteur Experience Cloud]](/help/components/dimensions/experience-cloud-visitor-id.md). |
| `ms_a` | Aucun | Défini par Media SDK sur `1` lorsque le média en flux continu suivi est de type audio plutôt que vidéo. |
| `ndh` | Aucun | Ajouté par AppMeasurement à chaque demande d’image générée. Comme les requêtes codées en dur l’omettent généralement, sa présence indique que l’accès provient d’AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Plus utilisé.** Permet de déterminer l’emplacement des cookies. |
| `oi` | Aucun | **Plus utilisé.** Instance d&#39;objet de la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificateur d’objet de la dernière page. Utilisé dans la version actuelle d’Activity Map. |
| `oidt` | Aucun | **Plus utilisé.** Type d’identifiant d’objet de la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `ot` | Aucun | **Plus utilisé.** Nom d’objet de la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `p` | Aucun | **Plus utilisé.** Liste des plug-ins utilisés dans le navigateur. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Utilisé dans la dimension [[!UICONTROL Page]](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Utilisé dans la dimension [[!UICONTROL Pages introuvables]](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Aucun | Indicateur de redirection de vérification de cookie persistant. Défini par les serveurs de collecte de données Adobe pour les nouveaux visiteurs et toujours défini sur `true`. Lorsque la prise en charge des cookies d’un nouveau visiteur est inconnue, le serveur de collecte de données redirige la demande d’image vers lui-même avec cet indicateur afin de confirmer que la vérification des cookies persistants a déjà eu lieu. Ce paramètre empêche les redirections infinies si le visiteur rejette les cookies. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Détermine le type d’accès. Les valeurs valides sont les suivantes : `lnk_o` ([[!UICONTROL Lien personnalisé]](/help/components/dimensions/custom-link.md)), `lnk_d` ([[!UICONTROL Lien de téléchargement]](/help/components/dimensions/download-link.md)), `lnk_e` ([[!UICONTROL Lien de sortie]](/help/components/dimensions/exit-link.md)) et `tnt` (accès à Analytics for Target). |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | URL sur laquelle le lien personnalisé a été créé. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Nom convivial du [ lien personnalisé ](/help/components/dimensions/custom-link.md). |
| `pev3` | Aucun | **Plus utilisé.** Jalons suivis dans les versions précédentes des rapports vidéo. |
| `pf` | Aucun | Indicateur de plateforme ; pour utilisation par Adobe uniquement. Ne pas modifier. |
| `pid` | Aucun | **Plus utilisé.** Identifiant de page pour la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `pidt` | Aucun | **Plus utilisé.** Type d’identificateur de page pour la dernière page. Utilisé dans les versions précédentes d’Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Abrégé pour le paramètre `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variable products. Utilisé dans les dimensions [[!UICONTROL Produit]](/help/components/dimensions/product.md) et [[!UICONTROL Catégorie]](/help/components/dimensions/category.md). |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Utilisé dans la dimension [[!UICONTROL ID d’achat]](/help/components/dimensions/purchase-id.md). |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL de l’accès référent. Utilisé dans les dimensions de sources de trafic, telles que [[!UICONTROL Référent]](/help/components/dimensions/referrer.md) et [[!UICONTROL Domaine référent]](/help/components/dimensions/referring-domain.md). |
| `s` | Aucun | Résolution d’écran, dans `width x height`. Utilisé dans la dimension [[!UICONTROL Résolutions d’écran]](/help/components/dimensions/monitor-resolution.md). |
| `sdid` | Aucun | ID de données supplémentaires. Associe plusieurs accès décrivant le même événement, tels que les accès Analytics et Target dans une intégration [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html). |
| `server` | [`server`](../vars/page-vars/server.md) | Utilisé dans la dimension [[!UICONTROL Serveur]](/help/components/dimensions/server.md). |
| `sv` | [`server`](../vars/page-vars/server.md) | Abrégé pour le paramètre `server`. |
| `state` | [`state`](../vars/page-vars/page-variables.md#retired-page-variables) | **Plus utilisé.** Capturé l’État américain qu’un visiteur a saisi, généralement par le biais d’un formulaire de livraison ou de facturation. |
| `t` | Aucun | Date/heure générée de l’accès. Utilise le format `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` correspond à la date/l’heure dans JavaScript. Le mois `0` est janvier, tandis que le mois `11` est décembre.<br>- `w` est le jour de la semaine. `0` est dimanche, tandis que `6` est samedi.<br>- `o` est le décalage GMT négatif en minutes. Par exemple, `420` désigne GMT-7. |
| `tnt` | Aucun | Payload des données Target utilisée dans les intégrations [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html). Envoyé lors de l’`pe=tnt`. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | L’horodatage personnalisé défini avec l’accès. Généralement utilisé pour le suivi hors ligne. |
| `u` | Aucun | **Plus utilisé.** Marque de compte utilisée dans les versions précédentes d’Activity Map. |
| `v` | Aucun | Utilisé dans la dimension [[!UICONTROL Compatible Java]](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | Utilisé dans la dimension [[!UICONTROL Code de suivi]](/help/components/dimensions/tracking-code.md). |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md) ou dimensions de conversion personnalisées. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variable de remplacement de l’identifiant visiteur. |
| `vidn` | Aucun | Défini par les serveurs de collecte de données Adobe pour les nouveaux visiteurs, accompagnant le paramètre `pccr` dans la demande d’image redirigée. Contient la valeur de l’identifiant visiteur stockée dans le cookie du visiteur. |
| `vmf` | [`visitorMigrationServer`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Plus utilisé.** Serveur de migration de visiteurs utilisé lors de la migration de cookies tiers vers des cookies propriétaires. |
| `vmt` | [`visitorMigrationKey`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Plus utilisé.** Clé de migration de visiteur, qui a permis de migrer des implémentations de cookies tiers vers des cookies propriétaires. |
| `vvp` | Aucun | **Plus utilisé.** Fournisseur de variables utilisé dans Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Utilisé avec les sources de données pour associer les données en ligne et hors ligne. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Utilisé dans la dimension [Code postal](/help/components/dimensions/zip-code.md). |
