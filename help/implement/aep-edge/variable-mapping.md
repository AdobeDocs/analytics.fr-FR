---
title: Mappage des variables Analytics dans Adobe Experience Edge
description: Afficher les champs XDM que Edge mappe automatiquement aux variables Analytics.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
source-git-commit: 1ed07727530ef5e3c9afbb291772f668fdee5d45
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 0%

---

# Mappage des variables Analytics dans Adobe Experience Edge

Le tableau suivant répertorie les variables que le réseau Adobe Experience Platform Edge mappe automatiquement dans Adobe Analytics. Si vous utilisez ces chemins de champ XDM, aucune configuration supplémentaire n’est nécessaire pour envoyer des données à Adobe Analytics.

| Chemin d’accès au champ XDM | Dimension et description d’Analytics |
| --- | --- |
| `application.id` | La dimension mobile [ID de l’application](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.isClose` | Permet de définir la mesure mobile [Blocages](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.closeType` | Détermine si un événement de fermeture est un blocage ou non. Les valeurs valides sont les suivantes : `close` (Une session de cycle de vie se termine et un événement pause a été reçu pour la session précédente) et `unknown` (Une session de cycle de vie se termine sans événement pause). |
| `application.isInstall` | Mesure mobile [Installations](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | Mesure mobile [Lancements](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.name` | Permet de définir la dimension mobile [ID de l’application](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.launches.value` | Mesure mobile [Lancements](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isUpgrade` | Mesure mobile [Mises à niveau](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.version` | Permet de définir la dimension mobile [ID de l’application](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.sessionLength` | Mesure mobile [Durée totale de la session](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `commerce.checkouts.id` | Application [sérialisation des événements](../vars/page-vars/events/event-serialization.md) au [Passages en caisse](../../components/metrics/checkouts.md) mesure. |
| `commerce.checkouts.value` | Incrémente le [Passages en caisse](../../components/metrics/checkouts.md) par le montant souhaité. |
| `commerce.order.currencyCode` | Définit la variable [currencyCode](../vars/config-vars/currencycode.md) de configuration. |
| `commerce.order.purchaseID` | Définit la variable [purchaseID](../vars/page-vars/purchaseid.md) Variable de page. |
| `commerce.productListAdds.id` | Application [sérialisation des événements](../vars/page-vars/events/event-serialization.md) au [Ajouts au panier](../../components/metrics/cart-additions.md) mesure. |
| `commerce.productListAdds.value` | Incrémente le [Ajouts au panier](../../components/metrics/cart-additions.md) par le montant souhaité. |
| `commerce.productListOpens.id` | Application [sérialisation des événements](../vars/page-vars/events/event-serialization.md) au [Paniers](../../components/metrics/carts.md) mesure. |
| `commerce.productListOpens.value` | Incrémente le [Paniers](../../components/metrics/carts.md) par le montant souhaité. |
| `commerce.productListRemovals.id` | Application [sérialisation des événements](../vars/page-vars/events/event-serialization.md) au [Retraits du panier](../../components/metrics/cart-removals.md) mesure. |
| `commerce.productListRemovals.value` | Incrémente le [Retraits du panier](../../components/metrics/cart-removals.md) par le montant souhaité. |
| `commerce.productListViews.id` | Application [sérialisation des événements](../vars/page-vars/events/event-serialization.md) au [Consultations du panier](../../components/metrics/cart-views.md) mesure. |
| `commerce.productListViews.value` | Incrémente le [Consultations du panier](../../components/metrics/cart-views.md) par le montant souhaité. |
| `commerce.productViews.id` | Application [sérialisation des événements](../vars/page-vars/events/event-serialization.md) au [Consultations produits](../../components/metrics/product-views.md) mesure. |
| `commerce.productViews.value` | Incrémente le [Consultations produits](../../components/metrics/product-views.md) par le montant souhaité. |
| `commerce.purchases.value` | Incrémente le [Commandes](../../components/metrics/orders.md) par le montant souhaité. |
| `device.manufacturer` | fabricant du périphérique mobile. |
| `device.model` | La dimension mobile [Nom de l’appareil](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `device.modelNumber` | Numéro de modèle de l’appareil mobile. |
| `device.colorDepth` | Permet de définir la variable [Profondeur de couleur](../../components/dimensions/color-depth.md) dimension. |
| `device.screenHeight` | Permet de définir la variable [Résolution de l’écran](../../components/dimensions/monitor-resolution.md) dimension. Veillez également à définir le champ XDM `device.screenWidth`. |
| `device.screenWidth` | Permet de définir la variable [Résolution de l’écran](../../components/dimensions/monitor-resolution.md) dimension. Veillez également à définir le champ XDM `device.screenHeight`. |
| `device.type` | Type d’appareil mobile. |
| `environment.browserDetails.acceptLanguage` | Permet de définir la variable [Langue](../../components/dimensions/language.md) dimension. |
| `environment.browserDetails.cookiesEnabled` | Définit la variable [Prise en charge des cookies](../../components/dimensions/cookie-support.md) dimension. Les valeurs valides sont les suivantes : `Y` (le navigateur accepte les cookies) et `N` (le navigateur rejette les cookies). |
| `environment.browserDetails.javaEnabled` | Définit la variable [Compatible Java](../../components/dimensions/java-enabled.md) dimension. Les valeurs valides sont les suivantes : `Y` (Java est activé) et `N` (Java est désactivé). |
| `environment.browserDetails.userAgent` | Utilisé comme solution de secours [visiteur unique](../../components/metrics/unique-visitors.md) méthode d&#39;identification. Généralement renseignée à l’aide de la variable `User-Agent` En-tête de requête HTTP. Vous pouvez associer ce champ à un eVar si vous souhaitez l’utiliser dans des rapports. |
| `environment.browserDetails.viewportHeight` | Définit la variable [Hauteur du navigateur](../../components/dimensions/browser-height.md) dimension. |
| `environment.browserDetails.viewportWidth` | Définit la variable [Largeur du navigateur](../../components/dimensions/browser-width.md) dimension. |
| `environment.carrier` | La dimension mobile [Nom de l’opérateur](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.connectionType` | Permet de définir la variable [Type de connexion](../../components/dimensions/connection-type.md) dimension. |
| `environment.ipV4` | Utilisé comme solution de secours [visiteur unique](../../components/metrics/unique-visitors.md) méthode d&#39;identification. Généralement renseignée à l’aide de la variable `X-Forwarded-For` En-tête HTTP. |
| `environment.language` | La dimension mobile Paramètres régionaux. |
| `environment.operatingSystem` | La dimension mobile [Système d’exploitation](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.operatingSystemVersion` | La dimension mobile [Version du système d’exploitation](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.type` | Indique si l’événement provient d’un événement [wearable](https://experienceleague.adobe.com/docs/mobile-services/android/wearables-android/c-android-wearables--additional-notes.html) appareil. Les valeurs valides sont les suivantes : `Application` (l’événement provient de l’application), `Extension` (l’événement provient de l’application portable), ou `Widget` (l’événement provient d’un widget mobile). |
| `identityMap.ECID[0].id` | Le [Identifiant du service Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr). |
| `marketing.trackingCode` | Définit la variable [Code de suivi](../../components/dimensions/tracking-code.md) dimension. |
| `media.mediaTimed.completes.value` | Mesure Media Analytics [Fin de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-complete). |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `media.mediaTimed.federated.value` | Mesure Media Analytics [Données fédérées](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#federated-data). |
| `media.mediaTimed.firstQuartiles.value` | Mesure Media Analytics [Marqueur de progression de 25 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#twenty-five-progress-marker). |
| `media.mediaTimed.mediaSegmentView.value` | Mesure Media Analytics [Affichages de segments de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment-views). |
| `media.mediaTimed.midpoints.value` | Mesure Media Analytics [Marqueur de progression de 50 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#fifty-progress-marker). |
| `media.mediaTimed.pauseTime.value` | Mesure Media Analytics [Durée totale de pause](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#total-pause-duration). |
| `media.mediaTimed.pauses.value` | Mesure Media Analytics [Événements de mise en pause](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#pause-events). |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | Dimension Media Analytics [ID de ressource](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#asset-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | Dimension Media Analytics [Nom de la vidéo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-name). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | Dimension Media Analytics [Émetteur](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#originator). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | Dimension Media Analytics [Épisode](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#episode). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | Dimension Media Analytics [Genre](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#genre). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | Dimension Media Analytics [Évaluation du contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-rating). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | Dimension Media Analytics [Saison](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#season). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | Dimension Media Analytics [ID de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | Dimension Media Analytics [Afficher](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show). |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | Dimension Media Analytics [Type de programme](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show-type). |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | Dimension Media Analytics [Durée de la vidéo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-length). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | Dimension Media Analytics [ID de session multimédia](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-session-id). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | Dimension Media Analytics [Canal de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-channel). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | Dimension Media Analytics [Type de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | Dimension Media Analytics [Réseau](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#network). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | Dimension Media Analytics [Segment de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | Dimension Media Analytics [Nom du lecteur de contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-player-name). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | Dimension Media Analytics [Version du SDK](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#sdk-version). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | Dimension Media Analytics [Type de flux multimédia](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-feed-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | Dimension Media Analytics [Format de diffusion](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#stream-format). |
| `media.mediaTimed.progress10.value` | Mesure Media Analytics [Marqueur de progression de 10 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ten-progress-marker). |
| `media.mediaTimed.progress95.value` | Mesure Media Analytics [Marqueur de progression de 95 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ninety-five-progress-marker). |
| `media.mediaTimed.resumes.value` | Mesure Media Analytics [Le contenu reprend](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-resumes). |
| `media.mediaTimed.starts.value` | Mesure Media Analytics [Démarrages de média](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-starts). |
| `media.mediaTimed.thirdQuartiles.value` | Mesure Media Analytics [Marqueur de progression de 75 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#seventy-five-progress-marker). |
| `media.mediaTimed.timePlayed.value` | Mesure Media Analytics [Temps passé sur le contenu](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-time-spent). |
| `media.mediaTimed.totalTimePlayed.value` | Mesure Media Analytics [Temps passé sur le média](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-time-spent). |
| `placeContext.geo.latitude` | Latitude de la dimension mobile. |
| `placeContext.geo.longitude` | Longitude de la dimension mobile. |
| `placeContext.geo.postalCode` | Le [Code postal](../../components/dimensions/zip-code.md) dimension. |
| `placeContext.geo.stateProvince` | Le [États américains](../../components/dimensions/us-states.md) dimension. |
| `productListItems[N].lineItemId` | Le [Catégorie](../../components/dimensions/category.md) dimension. |
| `productlistitems[N].name` | Le [Produit](../../components/dimensions/product.md) dimension. |
| `productlistitems[N].priceTotal` | Permet de déterminer la variable [Recettes](../../components/metrics/revenue.md) mesure. |
| `productlistitems[N].quantity` | Permet de déterminer la variable [Unités](../../components/metrics/units.md) mesure. |
| `web.webInteraction.URL` | Le [linkURL](../vars/config-vars/linkurl.md) de mise en oeuvre. |
| `web.webInteraction.name` | Le [Lien personnalisé](../../components/dimensions/custom-link.md), [Lien de téléchargement](../../components/dimensions/download-link.md)ou [Lien de sortie](../../components/dimensions/exit-link.md) selon la valeur de la variable `web.webInteraction.type` |
| `web.webInteraction.type` | Détermine le type de lien sur lequel l’utilisateur a cliqué. Les valeurs valides sont les suivantes : `lnk_o` (Liens personnalisés), `lnk_d` (Liens de téléchargement) et `lnk_e` (Liens de sortie). |
| `web.webPageDetails.URL` | Le [URL de la page](../../components/dimensions/page-url.md) dimension. |
| `web.webPageDetails.errorPage` | Indicateur qui permet de déterminer &quot;Pages introuvables&quot; [dimension](../../components/dimensions/pages-not-found.md) et [metric](../../components/metrics/pages-not-found.md). |
| `web.webPageDetails.name` | Le [Page](../../components/dimensions/page.md) dimension. |
| `web.webPageDetails.server` | Le [Serveur](../../components/dimensions/server.md) dimension. |
| `web.webPageDetails.siteSection` | Le [Section du site](../../components/dimensions/site-section.md) dimension. |
| `web.webReferrer.URL` | Le [Référent](../../components/dimensions/referrer.md) dimension. |

{style=&quot;table-layout:auto&quot;}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mappage d’autres champs XDM aux variables Analytics

Si vous souhaitez ajouter des dimensions ou des mesures à Adobe Analytics, vous pouvez le faire via [Variables de données contextuelles](../vars/page-vars/contextdata.md). Tous les éléments de champ XDM sont envoyés à Adobe Analytics en tant que données contextuelles avec le préfixe . `a.x`. Vous pouvez ensuite mapper cette variable de données contextuelles à la variable Analytics souhaitée à l’aide de la variable [Règles de traitement](../../admin/admin/c-processing-rules/processing-rules.md). Par exemple, si vous envoyez l’événement suivant :

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

Le SDK Web envoie ces données à Adobe Analytics en tant que variable de données contextuelles. `a.x._atag.search.term`. Vous pouvez ensuite utiliser une règle de traitement pour affecter cette valeur de variable de données contextuelles à la variable Analytics souhaitée, par exemple un eVar :

![Règle de traitement des termes de recherche](assets/examplerule.png)
