---
title: Mappage de la variable d’objet de données à Adobe Analytics
description: Affichez les champs d’objet de données qu’Experience Platform Edge mappe automatiquement aux variables Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 59d9dd8055a13046d05ac4c3b5261a6c5a919b5c
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---

# Mappage de la variable d’objet de données à Adobe Analytics

Le tableau ci-dessous présente les variables d’objet de données que Adobe Experience Platform Edge Network mappe automatiquement dans Adobe Analytics. Si vous utilisez ces chemins de champ d’objet de données, aucune configuration supplémentaire n’est nécessaire pour envoyer des données à Adobe Analytics.

L’utilisation de ces champs est recommandée si vous envisagez d’utiliser Customer Journey Analytics à l’avenir. Cette méthode de mise en œuvre permet à votre entreprise d’envoyer des données à Adobe à l’aide de Web SDK sans se conformer à un schéma XDM. Lorsque votre organisation est prête à envoyer des données à Adobe Experience Platform, vous pouvez utiliser [mappage de flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/data-prep#mapping) pour pointer les champs d’objet de données vers leurs champs XDM respectifs.

## Priorités des valeurs

La plupart des champs d’objet de données de ce tableau correspondent à un [champ XDM mappé](xdm-var-mapping.md). Si vous définissez à la fois un champ d’objet de données donné et son champ XDM respectif, le champ d’objet de données est prioritaire. Par exemple, si le champ `data.__adobe.analytics.events` est présent, il remplace tous les champs d’objet XDM liés à l’événement.

Certains champs d’objet de données prennent également en charge leur [valeur du paramètre de requête](../validate/query-parameters.md) respective en tant que valeurs courtes. Vous pouvez utiliser de manière interchangeable des champs d’objet de données standard et des champs d’objet de données courts, à condition qu’ils soient chacun destinés à des variables uniques. Évitez de définir simultanément un champ d’objet de données standard et son champ d’objet de données abrégé respectif. Adobe ne peut pas garantir quel champ est prioritaire.

## Mappage des champs de l’objet de données

Les mises à jour précédentes de ce tableau se trouvent dans l’historique [commit) de cette page sur GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md). Comme les variables AppMeasurement, tous les champs d’objet de données sont sensibles à la casse.

| Chemin du champ de l’objet de données | Variable et description Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | La dimension [Hauteur du navigateur](../../components/dimensions/browser-height.md). Le `data.__adobe.analytics.bh` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.browserWidth` | La dimension [&#x200B; Largeur du navigateur &#x200B;](../../components/dimensions/browser-width.md). Le `data.__adobe.analytics.bw` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.campaign` | La dimension [Code de suivi](../../components/dimensions/tracking-code.md). Le `data.__adobe.analytics.v0` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.channel` | La dimension [Section du site](../../components/dimensions/site-section.md). Le `data.__adobe.analytics.ch` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.colorDepth` | La dimension [&#x200B; Profondeur de la couleur &#x200B;](../../components/dimensions/color-depth.md). Le `data.__adobe.analytics.c` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.connectionType` | La dimension [Type de connexion](../../components/dimensions/connection-type.md). Le `data.__adobe.analytics.ct` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.contextData` | [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | La dimension [Prise en charge des cookies](../../components/dimensions/cookie-support.md). Le `data.__adobe.analytics.k` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.currencyCode` | Variable d’implémentation [`currencyCode`](../vars/config-vars/currencycode.md). Le `data.__adobe.analytics.cc` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.dynamicVariablePrefix` | Variable d’implémentation [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md). |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [dimensions eVar](../../components/dimensions/evar.md). Les champs courts `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` sont également pris en charge. |
| `data.__adobe.analytics.events` | [&#x200B; Événements personnalisés &#x200B;](../../components/metrics/custom-events.md). Le format de ce champ est similaire à celui de la variable d’implémentation [`events`](../vars/page-vars/events/events-overview.md). |
| `data.__adobe.analytics.javaEnabled` | La dimension [Compatible Java](../../components/dimensions/java-enabled.md). Le `data.__adobe.analytics.v` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.latitude` | Permet de définir les dimensions du cycle de vie mobile [Emplacement](../../components/dimensions/lifecycle-dimensions.md). Le `data.__adobe.analytics.lat` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.linkName` | La dimension [Lien personnalisé](../../components/dimensions/custom-link.md), [Lien de téléchargement](../../components/dimensions/download-link.md) ou [Lien de sortie](../../components/dimensions/exit-link.md) selon la valeur dans `data.__adobe.analytics.linkType`. Le `data.__adobe.analytics.pev2` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.linkURL` | Variable d’implémentation [`linkURL`](../vars/config-vars/linkurl.md). Le `data.__adobe.analytics.pev1` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.linkType` | Détermine le type de lien sur lequel l’utilisateur a cliqué. Les valeurs valides sont les suivantes : `o` (Liens personnalisés), `d` (Liens de téléchargement) et `e` (Liens de sortie). Le `data.__adobe.analytics.pe` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) des variables d’implémentation. Les champs courts `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` sont également pris en charge. |
| `data.__adobe.analytics.longitude` | Aide à la définition des dimensions de cycle de vie mobile [Emplacement](../../components/dimensions/lifecycle-dimensions.md). Le `data.__adobe.analytics.lon` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.pageName` | Dimension [Page](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | La dimension [URL de la page](/help/components/dimensions/page-url.md). Le `data.__adobe.analytics.g` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.pageType` | Variable d’implémentation [`pageType`](../vars/page-vars/pagetype.md). |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | Dimensions [prop](../../components/dimensions/prop.md). Les champs courts `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` sont également pris en charge. |
| `data.__adobe.analytics.purchaseID` | Variable d’implémentation [`purchaseID`](../vars/page-vars/purchaseid.md). |
| `data.__adobe.analytics.products` | Variable d’implémentation [`products`](../vars/page-vars/products.md), avec une mise en forme similaire. |
| `data.__adobe.analytics.referrer` | La dimension [Référent](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | La dimension [&#x200B; Résolution du moniteur &#x200B;](../../components/dimensions/monitor-resolution.md). Le `data.__adobe.analytics.s` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.server` | La dimension [Serveur](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | Variable d’implémentation [`transactionID`](../vars/page-vars/transactionid.md). Le `data.__adobe.analytics.xact` de champs abrégé est également pris en charge. |
| `data.__adobe.analytics.zip` | La dimension [&#x200B; Code postal &#x200B;](../../components/dimensions/zip-code.md). |

{style="table-layout:auto"}
