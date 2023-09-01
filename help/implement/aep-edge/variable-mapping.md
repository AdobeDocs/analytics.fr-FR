---
title: Mappage des variables Analytics dans Adobe Experience Edge
description: Afficher les champs XDM que Edge mappe automatiquement aux variables Analytics.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
feature: Implementation Basics
source-git-commit: b6a92b8ca79422d2ba857cd98c172a824658a7a6
workflow-type: tm+mt
source-wordcount: '1506'
ht-degree: 96%

---

# Mappage des variables Analytics dans Adobe Experience Edge

Le tableau suivant répertorie les variables que le réseau Adobe Experience Platform Edge mappe automatiquement dans Adobe Analytics. Si vous utilisez ces chemins de champ XDM, aucune configuration supplémentaire n’est nécessaire pour envoyer des données à Adobe Analytics. Ces champs sont inclus dans la variable **[!UICONTROL Modèle ExperienceEvent Adobe Analytics]** groupe de champs.

Vous trouverez les mises à jour précédentes de ce tableau dans la section [historique de validation sur GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/variable-mapping.md) de cette page.

| Chemin d’accès au champ XDM | Dimension et description d’Analytics |
| --- | --- |
| `application.isClose` | Permet de définir la mesure mobile [Blocages](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#metrics). |
| `application.isInstall` | Permet de déterminer quand augmenter la mesure mobile [Premiers lancements](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#metrics). |
| `application.isLaunch` | Permet de déterminer quand augmenter la mesure mobile [Premiers lancements](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#metrics). |
| `application.closeType` | Détermine si un événement de fermeture est un blocage ou non. Les valeurs valides sont les suivantes : `close` (Une session de cycle de vie se termine et un événement pause a été reçu pour la session précédente) et `unknown` (Une session de cycle de vie se termine sans événement pause). Aide à définir la mesure des [accidents](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#metrics). |
| `application.isInstall` | Mesure mobile [Installations](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#metrics). |
| `application.isLaunch` | Mesure mobile [Lancements](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#metrics). |
| `application.name` | Permet de définir la dimension mobile [ID de l’application](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#dimensions). |
| `application.isUpgrade` | Mesure mobile [Mises à niveau](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#metrics). |
| `application.version` | Permet de définir la dimension mobile [ID de l’application](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#dimensions). |
| `application.sessionLength` | La mesure mobile de [durée de la session précédente](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#metrics). |
| `commerce.checkouts.id` | Applique la [sérialisation des événements](../vars/page-vars/events/event-serialization.md) à la mesure [Passages en caisse](../../components/metrics/checkouts.md). |
| `commerce.checkouts.value` | Incrémente la mesure [Passages en caisse](../../components/metrics/checkouts.md) de la quantité souhaitée. |
| `commerce.order.currencyCode` | Définit la variable de configuration [currencyCode](../vars/config-vars/currencycode.md). |
| `commerce.order.purchaseID` | Définit la variable de page [purchaseID](../vars/page-vars/purchaseid.md). |
| `commerce.order.payments[0].transactionID` | Définit la variable de page [transactionID](../vars/page-vars/transactionid.md). |
| `commerce.productListAdds.id` | Applique la [sérialisation des événements](../vars/page-vars/events/event-serialization.md) à la mesure [Ajouts au panier](../../components/metrics/cart-additions.md). |
| `commerce.productListAdds.value` | Incrémente la mesure [Ajouts au panier](../../components/metrics/cart-additions.md). |
| `commerce.productListOpens.id` | Applique la [sérialisation des événements](../vars/page-vars/events/event-serialization.md) à la mesure [Paniers](../../components/metrics/carts.md). |
| `commerce.productListOpens.value` | Incrémente la mesure [Paniers](../../components/metrics/carts.md). |
| `commerce.productListRemovals.id` | Applique la [sérialisation des événements](../vars/page-vars/events/event-serialization.md) à la mesure [Suppression du panier](../../components/metrics/cart-removals.md). |
| `commerce.productListRemovals.value` | Incrémente la mesure [Retraits du panier](../../components/metrics/cart-removals.md). |
| `commerce.productListViews.id` | Applique la [sérialisation des événements](../vars/page-vars/events/event-serialization.md) à la mesure [Vues du panier](../../components/metrics/cart-views.md). |
| `commerce.productListViews.value` | Incrémente la mesure [Consultations du panier](../../components/metrics/cart-views.md). |
| `commerce.productViews.id` | Applique la [sérialisation des événements](../vars/page-vars/events/event-serialization.md) à la mesure [Vues des produits](../../components/metrics/product-views.md). |
| `commerce.productViews.value` | Incrémente la mesure [Consultations de produit](../../components/metrics/product-views.md). |
| `commerce.purchases.value` | Incrémente la mesure [Commandes](../../components/metrics/orders.md). |
| `device.model` | La dimension mobile [Nom de l’appareil](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#dimensions). |
| `device.colorDepth` | Permet de définir la dimension [Profondeur de la couleur](../../components/dimensions/color-depth.md). |
| `device.screenHeight` | Permet de définir la dimension [Résolution du moniteur.](../../components/dimensions/monitor-resolution.md) |
| `device.screenWidth` | Permet de définir la dimension [Résolution du moniteur.](../../components/dimensions/monitor-resolution.md) |
| `device.type` | Type d’appareil mobile. |
| `environment.browserDetails.acceptLanguage` | Permet de définir la dimension [Langue](../../components/dimensions/language.md). |
| `environment.browserDetails.cookiesEnabled` | Définit la dimension [Prise en charge des cookies](../../components/dimensions/cookie-support.md). Les valeurs valides sont les suivantes : `Y` (le navigateur accepte les cookies) et `N` (le navigateur rejette les cookies). |
| `environment.browserDetails.javaEnabled` | Définit la dimension [Compatible Java](../../components/dimensions/java-enabled.md). Les valeurs valides sont les suivantes : `Y` (Java est activé) et `N` (Java est désactivé). |
| `environment.browserDetails.userAgent` | Utilisé comme méthode d’identification [visiteur unique](../../components/metrics/unique-visitors.md) de secours. Généralement renseignée à l’aide de l’en-tête de requête HTTP `User-Agent`. Vous pouvez associer ce champ à une eVar si vous souhaitez l’utiliser dans des rapports. |
| `environment.browserDetails.viewportHeight` | Définit la dimension [Hauteur du navigateur](../../components/dimensions/browser-height.md). |
| `environment.browserDetails.viewportWidth` | Définit la dimension [Largeur du navigateur](../../components/dimensions/browser-width.md). |
| `environment.carrier` | La dimension mobile [Nom de l’opérateur](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#dimensions). |
| `environment.connectionType` | Permet de définir la dimension [Type de connexion](../../components/dimensions/connection-type.md). |
| `environment.ipV4` | Utilisé comme méthode d’identification [visiteur unique](../../components/metrics/unique-visitors.md) de secours. Généralement renseignée à l’aide de l’en-tête HTTP `X-Forwarded-For`. |
| `environment.language` | La dimension mobile Paramètres régionaux. |
| `environment.operatingSystem` | La dimension mobile [Système d’exploitation](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#dimensions). |
| `environment.operatingSystemVersion` | Permet de définir la dimension [Version du système d’exploitation](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=fr#dimensions). |
| `_experience.analytics.customDimensions.`<br/>`eVars.eVar1`<br/>`[...]`<br/>`_experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Définit la dimension [eVar](../../components/dimensions/evar.md) correspondante. |
| `_experience.analytics.customDimensions.`<br/>`hierarchies.hier1`<br/>`[...]`<br/>`_experience.analytics.customDImensions.`<br/>`hierarchies.hier5` | Définit la dimension [Hiérarchie](/help/components/dimensions/hierarchy.md) correspondante. |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter`<br/>`[...]`<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | Remplacement du délimiteur de props de liste. L’utilisation de ce champ n’est pas recommandée, car le délimiteur est automatiquement récupéré depuis [Admin des variables de trafic](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) dans les paramètres de la suite de rapports. L’utilisation de ce champ peut créer une incohérence entre le délimiteur utilisé et le délimiteur attendu par Analytics. |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.values`<br/>`[...]`<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | Un tableau de chaînes contenant les valeurs correspondantes de [prop de liste](../vars/page-vars/prop.md#list-props). |
| `_experience.analytics.customDimensions.`<br/>`lists.list1.list[].value`<br/>`[...]`<br/>`_experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatène toutes les chaînes `value` de chaque tableau `list[]` à sa [variable de liste](../vars/page-vars/list.md). Le délimiteur est automatiquement sélectionné en fonction de la valeur définie dans les [Paramètres de la suite de rapports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). |
| `_experience.analytics.customDimensions.`<br/>`props.prop1`<br/>`[...]`<br/>`_experience.analytics.customDimensions.`<br/>`props.prop75` | Définit la dimension [prop](../../components/dimensions/prop.md) correspondante. |
| `_experience.analytics.event1to100.`<br/>`event1.id`<br/>`[...]`<br/>`_experience.analytics.event901to1000.`<br/>`event1000.id` | Applique la [sérialisation des événements](../vars/page-vars/events/event-serialization.md) à la mesure correspondante des [événements personnalisés. ](../../components/metrics/custom-events.md) Chaque ID d’événement réside dans son parent de 100 groupes. Par exemple, pour appliquer la sérialisation à `event678`, utilisez `_experience.analytics.event601to700.event678.id`. |
| `_experience.analytics.event1to100.`<br/>`event1.value`<br/>`[...]`<br/>`_experience.analytics.event901to1000.`<br/>`event1000.value` | Incrémente la mesure correspondante des [événements personnalisés](../../components/metrics/custom-events.md) par la quantité désirée. Chaque événement réside dans son parent de 100 groupes. Par exemple, le champ pour `event567` is `_experience.analytics.event501to600.event567.value`. |
| `identityMap.ECID[0].id` | L’[identifiant du service d’identités Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr). |
| `marketing.trackingCode` | Définit la dimension [Code de suivi](../../components/dimensions/tracking-code.md). |
| `media.mediaTimed.completes.value` | La mesure Media Analytics [Contenu terminé](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#content-complete). |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `media.mediaTimed.federated.value` | La mesure Media Analytics [Données fédérées](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#federated-data). |
| `media.mediaTimed.firstQuartiles.value` | La mesure Media Analytics [Marqueur de progression de 25 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#twenty-five-progress-marker). |
| `media.mediaTimed.mediaSegmentView.value` | La mesure Media Analytics [Vues de segments de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#content-segment-views). |
| `media.mediaTimed.midpoints.value` | La mesure Media Analytics [Marqueur de progression de 50 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#fifty-progress-marker). |
| `media.mediaTimed.pauseTime.value` | La mesure Media Analytics [Durée totale de pause](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#total-pause-duration). |
| `media.mediaTimed.pauses.value` | La mesure Media Analytics [Mise en pause des événements](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#pause-events). |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | La dimension Media Analytics [ID de ressource](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#asset-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | La dimension Media Analytics [Nom de la vidéo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#video-name). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | La dimension Media Analytics [Émetteur](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#originator). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | La dimension Media Analytics [Épisode](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#episode). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | La dimension Media Analytics [Genre](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#genre). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | La dimension Media Analytics [Notation du contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#content-rating). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | La dimension Media Analytics [Saison](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#season). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | La dimension Media Analytics [ID de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#content-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | La dimension Media Analytics [Affichage](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#show). |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | La dimension Media Analytics [Type d’affichage](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#show-type). |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | La dimension Media Analytics [Longueur de la vidéo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#video-length). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | La dimension Media Analytics [ID de session de médias](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#media-session-id). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | La dimension Media Analytics [Canal de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#content-channel). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | La dimension Media Analytics [Type de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#content-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | La dimension Media Analytics [Réseau](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#network). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | La dimension Media Analytics [Segment de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#content-segment). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | La dimension Media Analytics [Nom du lecteur de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#content-player-name). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | La dimension Media Analytics [Version du SDK](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#sdk-version). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | La dimension Media Analytics [Type de flux de médias](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#media-feed-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | La dimension Media Analytics [Format de flux](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#stream-format). |
| `media.mediaTimed.progress10.value` | La mesure Media Analytics [Marqueur de progression de 10 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#ten-progress-marker). |
| `media.mediaTimed.progress95.value` | La mesure Media Analytics [Marqueur de progression de 95 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#ninety-five-progress-marker). |
| `media.mediaTimed.resumes.value` | La mesure Media Analytics [Reprise du contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#content-resumes). |
| `media.mediaTimed.starts.value` | La mesure Media Analytics [Démarrage des médias](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#media-starts). |
| `media.mediaTimed.thirdQuartiles.value` | La mesure Media Analytics [Marqueur de progression de 75 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#seventy-five-progress-marker). |
| `media.mediaTimed.timePlayed.value` | La mesure Media Analytics [Durée de contenu utilisée](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#content-time-spent). |
| `media.mediaTimed.totalTimePlayed.value` | La mesure Media Analytics [Durée des médias utilisée](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=fr#media-time-spent). |
| `placeContext.geo.latitude` | La latitude de la dimension mobile. |
| `placeContext.geo.longitude` | La longitude de la dimension mobile. |
| `placeContext.geo.postalCode` | La dimension [Code postal](../../components/dimensions/zip-code.md). |
| `placeContext.geo.stateProvince` | La dimension [États américains](../../components/dimensions/us-states.md). |
| `placeContext.localTime` | Permet de renseigner la variable [Fuseaux horaires](/help/analyze/reports-analytics/reports.md) dans Report &amp; Analytics. Apparaît comme `t_time_info` dans [Flux de données](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1`<br/>`[...]`<br/>`productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Applique le marchandisage de la [syntaxe du produit](../vars/page-vars/products.md) aux eVars. |
| `productListItems[]._experience.analytics.`<br/>`event1to100.event1.value`<br/>`[...]`<br/>`productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Applique le marchandisage de la [syntaxe de produit](../vars/page-vars/products.md) aux événements. |
| `productListItems[].lineItemId` | La dimension [Catégorie](../../components/dimensions/category.md). Voir aussi la variable de la page des [produits](../vars/page-vars/products.md). |
| `productListItems[].name` | La dimension [Produit](../../components/dimensions/product.md). Voir aussi la variable de la page des [produits](../vars/page-vars/products.md). Si `productListItems[].SKU` et `productListItems[].name` contiennent tous deux des données, la valeur de `productListItems[].SKU` est utilisée. |
| `productListItems[].priceTotal` | Permet de déterminer la mesure [Revenu](../../components/metrics/revenue.md). Voir aussi la variable de la page des [produits](../vars/page-vars/products.md). |
| `productListItems[].quantity` | Permet de déterminer la mesure [Unités](../../components/metrics/units.md). Voir aussi la variable de la page des [produits](../vars/page-vars/products.md). |
| `productListItems[].SKU` | La dimension [Produit](../../components/dimensions/product.md). Voir aussi la variable de la page des [produits](../vars/page-vars/products.md). Si `productListItems[].SKU` et `productListItems[].name` contiennent tous deux des données, la valeur de `productListItems[].SKU` est utilisée. |
| `web.webInteraction.URL` | La variable de mise en œuvre [linkURL](../vars/config-vars/linkurl.md). |
| `web.webInteraction.name` | La dimension [Lien personnalisé](../../components/dimensions/custom-link.md), [Lien de téléchargement](../../components/dimensions/download-link.md) ou [Lien de sortie](../../components/dimensions/exit-link.md) selon la valeur dans `web.webInteraction.type` |
| `web.webInteraction.type` | Détermine le type de lien sur lequel l’utilisateur a cliqué. Les valeurs valides sont les suivantes : `other` (Liens personnalisés), `download` (Liens de téléchargement) et `exit` (Liens de sortie). |
| `web.webPageDetails.URL` | La dimension [URL de la page](../../components/dimensions/page-url.md). |
| `web.webPageDetails.isErrorPage` | Indicateur qui permet de déterminer la [dimension](../../components/dimensions/pages-not-found.md) et la [mesure](../../components/metrics/pages-not-found.md) « Pages introuvables ». |
| `web.webPageDetails.name` | La dimension [Page](../../components/dimensions/page.md). |
| `web.webPageDetails.server` | La dimension [Serveur](../../components/dimensions/server.md). |
| `web.webPageDetails.siteSection` | La dimension [Section du site](../../components/dimensions/site-section.md). |
| `web.webReferrer.URL` | La dimension [Référent](../../components/dimensions/referrer.md). |

{style="table-layout:auto"}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mappage d’autres champs XDM aux variables Analytics

Si vous souhaitez ajouter des dimensions ou des mesures à Adobe Analytics, vous pouvez le faire via [Variables de données contextuelles](../vars/page-vars/contextdata.md). Tous les éléments de champ XDM qui ne sont pas automatiquement mappés sont envoyés à Adobe Analytics en tant que données contextuelles avec le préfixe a.x. Vous pouvez ensuite mapper cette variable de données contextuelles à la variable Analytics de votre choix à l’aide des [Règles de traitement](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=fr). Par exemple, si vous définissez l’évènement suivant :

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "search":{
                "term":"Example search term"
            }
        }
    }
})
```

Le SDK Web envoie ces données à Adobe Analytics en tant que variable de données contextuelles `a.x._atag.search.term`. Vous pouvez ensuite utiliser une règle de traitement pour affecter cette valeur de variable de données contextuelles à la variable Analytics souhaitée, par exemple une eVar :

![Règle de traitement des termes de recherche](assets/examplerule.png)
