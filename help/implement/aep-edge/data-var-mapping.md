---
title: Mappage des variables d’objet de données vers Adobe Analytics
description: Affichez les champs d’objet de données Experience Platform Edge automatiquement mis en correspondance avec les variables Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 3a530e3e47ac9d6cf2b711cecd07f2c33765d63c
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 5%

---

# Mappage des variables d’objet de données vers Adobe Analytics

Le tableau suivant présente les variables d’objet de données que Adobe Experience Platform Edge Network mappe automatiquement dans Adobe Analytics. Si vous utilisez ces chemins de champ d’objet de données, aucune configuration supplémentaire n’est nécessaire pour envoyer des données à Adobe Analytics.

L’utilisation de ces champs est recommandée si vous envisagez d’utiliser Customer Journey Analytics à l’avenir. Cette méthode d’implémentation permet à votre entreprise d’envoyer des données à Adobe à l’aide du SDK Web sans se conformer à un schéma XDM. Lorsque votre entreprise est prête à envoyer des données à Adobe Experience Platform, vous pouvez utiliser [Mappage des flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/data-prep.html#mapping) pour pointer les champs d’objet de données vers leurs champs XDM respectifs.

## Priorités de valeur

La plupart des champs d’objet de données de ce tableau correspondent à un [champ XDM mappé](xdm-var-mapping.md). Si vous définissez les deux `data` et son champ XDM respectif, le champ d’objet de données est prioritaire. Si vous utilisez à la fois le champ d’objet XDM et le champ d’objet de données, Adobe recommande de définir des événements personnalisés à l’aide du champ d’objet de données. Si le champ `data.__adobe.analytics.events` est présent, il remplace tous les champs d’objet XDM liés aux événements commerciaux et personnalisés.

Certains champs d’objet de données prennent également en charge leurs [Valeur du paramètre de requête](../validate/query-parameters.md) comme valeurs abrégées. Vous pouvez utiliser des champs d’objet de données standard et des champs d’objet de données abrégés de manière interchangeable, à condition qu’ils soient chacun pour des variables uniques. Évitez de définir simultanément un champ d’objet de données standard et son champ d’objet de données de courte longueur respectif. Adobe ne peut pas garantir quel champ a la priorité.

## Mappage des champs d’objet de données

Vous trouverez les mises à jour précédentes de ce tableau dans la section [historique de validation sur GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md) de cette page.

| Chemin du champ de l’objet de données | Variable et description Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | La variable [Hauteur du navigateur](../../components/dimensions/browser-height.md) dimension. Champ abrégé `data.__adobe.analytics.bh` est également prise en charge. |
| `data.__adobe.analytics.browserWidth` | La variable [Largeur du navigateur](../../components/dimensions/browser-width.md) dimension. Champ abrégé `data.__adobe.analytics.bw` est également prise en charge. |
| `data.__adobe.analytics.campaign` | La variable [Code de suivi](../../components/dimensions/tracking-code.md) dimension. Champ abrégé `data.__adobe.analytics.v0` est également prise en charge. |
| `data.__adobe.analytics.channel` | La variable [Section du site](../../components/dimensions/site-section.md) dimension. Champ abrégé `data.__adobe.analytics.ch` est également prise en charge. |
| `data.__adobe.analytics.colorDepth` | La variable [Profondeur de couleur](../../components/dimensions/color-depth.md) dimension. Champ abrégé `data.__adobe.analytics.c` est également prise en charge. |
| `data.__adobe.analytics.connectionType` | La variable [Type de connexion](../../components/dimensions/connection-type.md) dimension. Champ abrégé `data.__adobe.analytics.ct` est également prise en charge. |
| `data.__adobe.analytics.contextData` | [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | La variable [Prise en charge des cookies](../../components/dimensions/cookie-support.md) dimension. Champ abrégé `data.__adobe.analytics.k` est également prise en charge. |
| `data.__adobe.analytics.currencyCode` | La variable [`currencyCode`](../vars/config-vars/currencycode.md) de mise en oeuvre. Champ abrégé `data.__adobe.analytics.cc` est également prise en charge. |
| `data.__adobe.analytics.dynamicVariablePrefix` | La variable [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) de mise en oeuvre. |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) dimensions. Champs abrégés `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` sont également prises en charge. |
| `data.__adobe.analytics.events` | [Événements personnalisés](../../components/metrics/custom-events.md). Mettez ce champ en forme de la même manière que le champ [`events`](../vars/page-vars/events/events-overview.md) de mise en oeuvre. |
| `data.__adobe.analytics.javaEnabled` | La variable [Compatible Java](../../components/dimensions/java-enabled.md) dimension. Champ abrégé `data.__adobe.analytics.v` est également prise en charge. |
| `data.__adobe.analytics.latitude` | Permet de définir la variable [Emplacement](../../components/dimensions/lifecycle-dimensions.md) dimensions de cycle de vie mobile. Champ abrégé `data.__adobe.analytics.lat` est également prise en charge. |
| `data.__adobe.analytics.linkName` | La variable [Lien personnalisé](../../components/dimensions/custom-link.md), [Lien de téléchargement](../../components/dimensions/download-link.md), ou [Lien de sortie](../../components/dimensions/exit-link.md) selon la valeur de la variable `data.__adobe.analytics.linkType`. Champ abrégé `data.__adobe.analytics.pev2` est également prise en charge. |
| `data.__adobe.analytics.linkURL` | La variable [`linkURL`](../vars/config-vars/linkurl.md) de mise en oeuvre. Champ abrégé `data.__adobe.analytics.pev1` est également prise en charge. |
| `data.__adobe.analytics.linkType` | Détermine le type de lien sur lequel l’utilisateur a cliqué. Les valeurs valides incluent : `o` (Liens personnalisés), `d` (Liens de téléchargement) et `e` (Liens de sortie). Champ abrégé `data.__adobe.analytics.pe` est également prise en charge. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) variables d’implémentation. Champs abrégés `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` sont également prises en charge. |
| `data.__adobe.analytics.longitude` | Permet de définir [Emplacement](../../components/dimensions/lifecycle-dimensions.md) dimensions de cycle de vie mobile. Champ abrégé `data.__adobe.analytics.lon` est également prise en charge. |
| `data.__adobe.analytics.pageName` | La dimension [Page](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | La variable [URL de la page](/help/components/dimensions/page-url.md) dimension. Champ abrégé `data.__adobe.analytics.g` est également prise en charge. |
| `data.__adobe.analytics.pageType` | La variable [`pageType`](../vars/page-vars/pagetype.md) de mise en oeuvre. |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) dimensions. Champs abrégés `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` sont également prises en charge. |
| `data.__adobe.analytics.purchaseID` | La variable [`purchaseID`](../vars/page-vars/purchaseid.md) de mise en oeuvre. |
| `data.__adobe.analytics.products` | La variable [`products`](../vars/page-vars/products.md) , selon une mise en forme similaire. |
| `data.__adobe.analytics.referrer` | La dimension [Référent](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | La variable [Résolution de l’écran](../../components/dimensions/monitor-resolution.md) dimension. Champ abrégé `data.__adobe.analytics.s` est également prise en charge. |
| `data.__adobe.analytics.server` | La dimension [Serveur](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.tnta` | Utilisé dans les intégrations A4T. |
| `data.__adobe.analytics.transactionID` | La variable [`transactionID`](../vars/page-vars/transactionid.md) de mise en oeuvre. Champ abrégé `data.__adobe.analytics.xact` est également prise en charge. |
| `data.__adobe.analytics.zip` | La variable [Code postal](../../components/dimensions/zip-code.md) dimension. |

{style="table-layout:auto"}
