---
title: Mappage des variables d’objet de données vers Adobe Analytics
description: Affichez les champs d’objet de données que Edge Experience Platform mappe automatiquement aux variables Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 59d9dd8055a13046d05ac4c3b5261a6c5a919b5c
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---

# Mappage des variables d’objet de données vers Adobe Analytics

Le tableau suivant présente les variables d’objet de données que l’Edge Network Adobe Experience Platform mappe automatiquement dans Adobe Analytics. Si vous utilisez ces chemins de champ d’objet de données, aucune configuration supplémentaire n’est nécessaire pour envoyer des données à Adobe Analytics.

L’utilisation de ces champs est recommandée si vous envisagez d’utiliser Customer Journey Analytics à l’avenir. Cette méthode d’implémentation permet à votre entreprise d’envoyer des données à Adobe à l’aide du SDK Web sans se conformer à un schéma XDM. Lorsque votre entreprise est prête à envoyer des données à Adobe Experience Platform, vous pouvez utiliser le [mappage de flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/data-prep#mapping) pour pointer les champs d’objet de données vers leurs champs XDM respectifs.

## Priorités de valeur

La plupart des champs d’objet de données de cette table correspondent à un [champ XDM mappé](xdm-var-mapping.md). Si vous définissez un champ d’objet de données donné et son champ XDM respectif, le champ d’objet de données est prioritaire. Par exemple, si le champ `data.__adobe.analytics.events` est présent, il remplace tous les champs d’objet XDM liés à un événement.

Certains champs d’objet de données prennent également en charge leurs [ valeurs de paramètre de requête ](../validate/query-parameters.md) respectives en tant que valeurs abrégées. Vous pouvez utiliser des champs d’objet de données standard et des champs d’objet de données abrégés de manière interchangeable, à condition qu’ils soient chacun pour des variables uniques. Évitez de définir simultanément un champ d’objet de données standard et son champ d’objet de données de courte longueur respectif. Adobe ne peut pas garantir quel champ a la priorité.

## Mappage des champs d’objet de données

Vous trouverez les mises à jour précédentes de ce tableau dans l’ [historique de validation sur GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md) de cette page. À l’instar des variables d’AppMeasurement, tous les champs d’objet de données sont sensibles à la casse.

| Chemin du champ de l’objet de données | Variable et description Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | Dimension [Hauteur du navigateur](../../components/dimensions/browser-height.md). Le champ abrégé `data.__adobe.analytics.bh` est également pris en charge. |
| `data.__adobe.analytics.browserWidth` | Dimension [Largeur du navigateur](../../components/dimensions/browser-width.md). Le champ abrégé `data.__adobe.analytics.bw` est également pris en charge. |
| `data.__adobe.analytics.campaign` | La dimension [Code de suivi](../../components/dimensions/tracking-code.md). Le champ abrégé `data.__adobe.analytics.v0` est également pris en charge. |
| `data.__adobe.analytics.channel` | Dimension [Section du site](../../components/dimensions/site-section.md). Le champ abrégé `data.__adobe.analytics.ch` est également pris en charge. |
| `data.__adobe.analytics.colorDepth` | Dimension [Profondeur de couleur](../../components/dimensions/color-depth.md). Le champ abrégé `data.__adobe.analytics.c` est également pris en charge. |
| `data.__adobe.analytics.connectionType` | La dimension [Type de connexion](../../components/dimensions/connection-type.md). Le champ abrégé `data.__adobe.analytics.ct` est également pris en charge. |
| `data.__adobe.analytics.contextData` | [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | La dimension [Prise en charge des cookies](../../components/dimensions/cookie-support.md). Le champ abrégé `data.__adobe.analytics.k` est également pris en charge. |
| `data.__adobe.analytics.currencyCode` | La variable de mise en oeuvre [`currencyCode`](../vars/config-vars/currencycode.md). Le champ abrégé `data.__adobe.analytics.cc` est également pris en charge. |
| `data.__adobe.analytics.dynamicVariablePrefix` | La variable de mise en oeuvre [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md). |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | Dimensions [eVar](../../components/dimensions/evar.md). Les champs abrégés `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` sont également pris en charge. |
| `data.__adobe.analytics.events` | [Événements personnalisés](../../components/metrics/custom-events.md). Mettez ce champ en forme de la même manière que la variable d&#39;implémentation [`events`](../vars/page-vars/events/events-overview.md). |
| `data.__adobe.analytics.javaEnabled` | Dimension [Java activé](../../components/dimensions/java-enabled.md). Le champ abrégé `data.__adobe.analytics.v` est également pris en charge. |
| `data.__adobe.analytics.latitude` | Permet de définir les dimensions de cycle de vie mobile [Location](../../components/dimensions/lifecycle-dimensions.md). Le champ abrégé `data.__adobe.analytics.lat` est également pris en charge. |
| `data.__adobe.analytics.linkName` | La dimension [Lien personnalisé](../../components/dimensions/custom-link.md), [Lien de téléchargement](../../components/dimensions/download-link.md) ou [Lien de sortie](../../components/dimensions/exit-link.md), selon la valeur de `data.__adobe.analytics.linkType`. Le champ abrégé `data.__adobe.analytics.pev2` est également pris en charge. |
| `data.__adobe.analytics.linkURL` | La variable de mise en oeuvre [`linkURL`](../vars/config-vars/linkurl.md). Le champ abrégé `data.__adobe.analytics.pev1` est également pris en charge. |
| `data.__adobe.analytics.linkType` | Détermine le type de lien sur lequel l’utilisateur a cliqué. Les valeurs valides sont `o` (liens personnalisés), `d` (liens de téléchargement) et `e` (liens de sortie). Le champ abrégé `data.__adobe.analytics.pe` est également pris en charge. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) variables d’implémentation. Les champs abrégés `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` sont également pris en charge. |
| `data.__adobe.analytics.longitude` | Aide à la définition des dimensions de cycle de vie mobile [Location](../../components/dimensions/lifecycle-dimensions.md). Le champ abrégé `data.__adobe.analytics.lon` est également pris en charge. |
| `data.__adobe.analytics.pageName` | Dimension [Page](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | Dimension [URL de la page](/help/components/dimensions/page-url.md). Le champ abrégé `data.__adobe.analytics.g` est également pris en charge. |
| `data.__adobe.analytics.pageType` | La variable de mise en oeuvre [`pageType`](../vars/page-vars/pagetype.md). |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | Dimensions [Prop](../../components/dimensions/prop.md). Les champs abrégés `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` sont également pris en charge. |
| `data.__adobe.analytics.purchaseID` | La variable de mise en oeuvre [`purchaseID`](../vars/page-vars/purchaseid.md). |
| `data.__adobe.analytics.products` | La variable d’implémentation [`products`](../vars/page-vars/products.md), suivant une mise en forme similaire. |
| `data.__adobe.analytics.referrer` | La dimension [Référent](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | La dimension [Résolution de l’écran](../../components/dimensions/monitor-resolution.md). Le champ abrégé `data.__adobe.analytics.s` est également pris en charge. |
| `data.__adobe.analytics.server` | La dimension [Serveur](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | La variable de mise en oeuvre [`transactionID`](../vars/page-vars/transactionid.md). Le champ abrégé `data.__adobe.analytics.xact` est également pris en charge. |
| `data.__adobe.analytics.zip` | Dimension [Code postal](../../components/dimensions/zip-code.md). |

{style="table-layout:auto"}
