---
title: Mappage des champs d’objet de données à Adobe Analytics
description: Affichez les champs d’objets de données qu’Experience Platform Edge mappe automatiquement aux variables Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: b3546e67cccc37cbdb89db2e80b3b34b2dbe417b
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 77%

---

# Mappage des champs d’objet de données à Adobe Analytics

Le tableau suivant montre le champ d’objet de données que Adobe Experience Platform Edge Network mappe automatiquement dans Adobe Analytics. Si vous utilisez ces chemins de champ d’objet de données, aucune configuration supplémentaire n’est nécessaire pour envoyer des données à Adobe Analytics.

L’utilisation de ces champs est recommandée si vous envisagez d’utiliser Customer Journey Analytics à l’avenir. Cette méthode de mise en œuvre permet à votre entreprise d’envoyer des données à Adobe à l’aide du SDK web sans se conformer à un schéma XDM. Lorsque votre organisation est prête à envoyer des données à Adobe Experience Platform, vous pouvez utiliser [Mappage de train de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/data-prep#mapping) pour pointer les champs d’objet de données vers leurs champs XDM respectifs.

## Priorités des valeurs

La plupart des champs d’objet de données de ce tableau correspondent à un [&#x200B; champ XDM mappé &#x200B;](xdm-var-mapping.md). Lors de l’ingestion Adobe Analytics, les valeurs sont d’abord mappées de XDM aux variables Analytics. Les champs d’objet de données reconnus sont ensuite mappés et remplacent toutes les valeurs précédemment définies lorsqu’ils sont mappés à la même variable Analytics. Par exemple, si `data.__adobe.analytics.events` est présent, il remplace l’ensemble complet des événements qui seraient autrement dérivés de XDM ; les événements ne sont pas combinés entre les deux sources. Une chaîne vide (`""`) dans un champ d’objet de données vide sa variable Analytics mappée pour l’accès, même si le champ XDM correspondant contient une valeur.

Certains champs d’objet de données prennent également en charge leur [valeur du paramètre de requête](../validate/query-parameters.md) respective en tant que valeurs abrégées. Vous pouvez utiliser de manière interchangeable des champs d’objet de données standard et des champs d’objet de données abrégés, à condition qu’ils soient chacun destinés à des variables uniques. Évitez de définir simultanément un champ d’objet de données standard et son champ d’objet de données abrégé respectif. Adobe ne peut pas garantir quel champ est prioritaire.

## Mappage de champ d’objet de données

Vous trouverez les mises à jour précédentes de ce tableau dans la section [historique de validation sur GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md) de cette page. Comme les variables AppMeasurement, tous les champs d’objet de données sont sensibles à la casse.

| Chemin du champ d’objet de données | Variable et description d’Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | La dimension [Hauteur du navigateur](../../components/dimensions/browser-height.md). Le champ abrégé `data.__adobe.analytics.bh` est également pris en charge. |
| `data.__adobe.analytics.browserWidth` | La dimension [Largeur du navigateur](../../components/dimensions/browser-width.md). Le champ abrégé `data.__adobe.analytics.bw` est également pris en charge. |
| `data.__adobe.analytics.campaign` | La dimension [Code de suivi](../../components/dimensions/tracking-code.md). Le champ abrégé `data.__adobe.analytics.v0` est également pris en charge. |
| `data.__adobe.analytics.channel` | La dimension [Section du site](../../components/dimensions/site-section.md). Le champ abrégé `data.__adobe.analytics.ch` est également pris en charge. |
| `data.__adobe.analytics.colorDepth` | La dimension [Profondeur de couleur](../../components/dimensions/color-depth.md). Le champ abrégé `data.__adobe.analytics.c` est également pris en charge. |
| `data.__adobe.analytics.connectionType` | La dimension [Type de connexion](../../components/dimensions/connection-type.md). Le champ abrégé `data.__adobe.analytics.ct` est également pris en charge. |
| `data.__adobe.analytics.contextData` | [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | La dimension [Prise en charge des cookies](../../components/dimensions/cookie-support.md). Le champ abrégé `data.__adobe.analytics.k` est également pris en charge. |
| `data.__adobe.analytics.currencyCode` | La variable de mise en œuvre [`currencyCode`](../vars/config-vars/currencycode.md). Le champ abrégé `data.__adobe.analytics.cc` est également pris en charge. |
| `data.__adobe.analytics.dynamicVariablePrefix` | La variable de mise en œuvre [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md). |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | Dimensions [eVar](../../components/dimensions/evar.md). Les champs abrégés `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` sont également pris en charge. |
| `data.__adobe.analytics.events` | [Événements personnalisés](../../components/metrics/custom-events.md). Formatez ce champ de manière similaire à celui de la variable d’implémentation [`events`](../vars/page-vars/events/events-overview.md). |
| `data.__adobe.analytics.javaEnabled` | La dimension [Compatible Java](../../components/dimensions/java-enabled.md). Le champ abrégé `data.__adobe.analytics.v` est également pris en charge. |
| `data.__adobe.analytics.latitude` | Permet de définir les dimensions du cycle de vie mobile [Emplacement](../../components/dimensions/lifecycle-dimensions.md). Le champ abrégé `data.__adobe.analytics.lat` est également pris en charge. |
| `data.__adobe.analytics.linkName` | La dimension [Lien personnalisé](../../components/dimensions/custom-link.md), [Lien de téléchargement](../../components/dimensions/download-link.md) ou [Lien de sortie](../../components/dimensions/exit-link.md) selon la valeur dans `data.__adobe.analytics.linkType`. Le champ abrégé `data.__adobe.analytics.pev2` est également pris en charge. |
| `data.__adobe.analytics.linkURL` | La variable de mise en œuvre [`linkURL`](../vars/config-vars/linkurl.md). Le champ abrégé `data.__adobe.analytics.pev1` est également pris en charge. |
| `data.__adobe.analytics.linkType` | Détermine le type de lien sur lequel la personne a cliqué. Les valeurs valides sont les suivantes : `o` (Liens personnalisés), `d` (Liens de téléchargement) et `e` (Liens de sortie). Le champ abrégé `data.__adobe.analytics.pe` est également pris en charge. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | Variables d’implémentation [`list`](/help/implement/vars/page-vars/list.md). Les champs abrégés `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` sont également pris en charge. |
| `data.__adobe.analytics.longitude` | Aide à la définition des dimensions de cycle de vie mobile [Emplacement](../../components/dimensions/lifecycle-dimensions.md). Le champ abrégé `data.__adobe.analytics.lon` est également pris en charge. |
| `data.__adobe.analytics.pageName` | Dimension [Page](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | La dimension [URL de la page](/help/components/dimensions/page-url.md). Le champ abrégé `data.__adobe.analytics.g` est également pris en charge. |
| `data.__adobe.analytics.pageType` | La variable de mise en œuvre [`pageType`](../vars/page-vars/pagetype.md). |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | Dimensions [prop](../../components/dimensions/prop.md). Les champs abrégés `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` sont également pris en charge. |
| `data.__adobe.analytics.purchaseID` | La variable de mise en œuvre [`purchaseID`](../vars/page-vars/purchaseid.md). |
| `data.__adobe.analytics.products` | La variable d’implémentation [`products`](../vars/page-vars/products.md), avec une mise en forme similaire. |
| `data.__adobe.analytics.referrer` | La dimension [Référent](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | La dimension [Résolution de l’écran](../../components/dimensions/monitor-resolution.md). Le champ abrégé `data.__adobe.analytics.s` est également pris en charge. |
| `data.__adobe.analytics.server` | La dimension [Serveur](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | La variable de mise en œuvre [`transactionID`](../vars/page-vars/transactionid.md). Le champ abrégé `data.__adobe.analytics.xact` est également pris en charge. |
| `data.__adobe.analytics.zip` | La dimension [Code postal](../../components/dimensions/zip-code.md). |

{style="table-layout:auto"}
