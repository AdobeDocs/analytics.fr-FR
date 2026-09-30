---
title: Mettre en œuvre Adobe Analytics à l’aide d’Adobe Experience Platform Edge
description: Vue d’ensemble de l’utilisation des données XDM d’Adobe Experience Platform dans Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/-WWT7-dW4vo8g0DXtuQK9E30DktJ2yjzbc6w69oxJnc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 100%
---
# Mettre en œuvre Adobe Analytics avec Adobe Experience Platform Edge Network

Adobe Experience Platform Edge Network vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. Edge Network transfère les informations appropriées aux produits souhaités. Ce concept vous permet de consolider les efforts de mise en œuvre, en particulier sur plusieurs solutions de données. Adobe Analytics est l’un des produits auxquels vous pouvez envoyer des données à l’aide d’Edge Network.

## Comment Adobe Analytics gère les données d’Edge Network

Les données envoyées à Edge Network et les données AppMeasurement fonctionnant différemment, la payload d’Edge Network détermine la manière dont Adobe Analytics gère le hit. Consultez [Types d’événements Edge Network dans Adobe Analytics](hit-types.md) pour plus d’informations.

Les données envoyées à Adobe Experience Platform Edge Network peuvent suivre trois formats : **objet XDM**, **objet de données** et **données contextuelles**. Lorsqu’un train de données transfère des données vers Adobe Analytics, elles sont traduites dans un format qu’Adobe Analytics peut traiter.

## Objet `xdm`

Respectez les schémas que vous créez sur la base [XDM](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home) (modèle de données d’expérience). XDM vous offre davantage de flexibilité quant aux champs définis comme faisant partie d’événements. Si vous souhaitez utiliser un schéma prédéfini spécifique à Adobe Analytics, vous pouvez ajouter le [groupe de champs de schéma Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) à votre schéma. Une fois ajouté, vous pouvez remplir ce schéma à l’aide de l’objet `xdm` dans le SDK web pour envoyer des données à une suite de rapports. Lorsque les données arrivent sur Edge Network, celui-ci traduit l’objet XDM dans un format compris par Adobe Analytics.

Consultez [Mappage des variables d’objet XDM à Adobe Analytics](xdm-var-mapping.md) pour obtenir une référence complète des champs XDM et de leur mappage aux variables Analytics.

>[!TIP]
>
>Si vous prévoyez de migrer vers [Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-landing) à l’avenir, Adobe vous déconseille d’utiliser le groupe de champs de schéma Adobe Analytics. Adobe recommande plutôt de [créer votre propre schéma](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect) et d’utiliser le mappage de train de données pour renseigner les variables Analytics souhaitées. Cette stratégie ne vous verrouille pas sur un schéma de props et d’eVars lorsque vous souhaitez passer à Customer Journey Analytics.

## Objet `data`

Au lieu d’utiliser l’objet `xdm`, vous pouvez utiliser l’objet `data` à la place. L’objet de données est destiné aux implémentations qui utilisent actuellement AppMeasurement, ce qui facilite considérablement la mise à niveau vers le SDK web. Le réseau Edge Network détecte la présence de ces champs spécifiques à Adobe Analytics sans avoir à se conformer à un schéma.

Consultez [Mappage des variables d’objet de données à Adobe Analytics](data-var-mapping.md) pour consulter une référence complète des champs d’objet de données et de la manière dont ils sont mappés aux variables Analytics.

## Variables de données contextuelles

Envoyez les données à Edge Network dans le format de votre choix. Tous les champs qui ne sont pas automatiquement mappés à des champs d’objet `xdm` ou `data` sont inclus en tant que [variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) lors du transfert vers Adobe Analytics. Vous devez ensuite utiliser les [Règles de traitement](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) pour mapper les champs souhaités à leurs variables Analytics respectives.

Par exemple, si vous disposiez d’un schéma XDM personnalisé qui ressemblait à ce qui suit :

```json
{
  "xdm": {
    "key": "value",
    "animal": {
      "species": "Raven",
      "size": "13 inches"
    },
    "array": [
      "v0",
      "v1",
      "v2"
    ],
    "objectArray":[{
      "ad1": "300x200",
      "ad2": "60x240",
      "ad3": "600x50"
    }]
  }
}
```

Ces champs seraient alors les clés de données contextuelles disponibles dans l’interface des Règles de traitement :

```javascript
a.x.key // value
a.x.animal.species // Raven
a.x.animal.size // 13 inches
a.x.array.0 // v0
a.x.array.1 // v1
a.x.array.2 // v2
a.x.objectarray.0.ad1 // 300x200
a.x.objectarray.1.ad2 // 60x240
a.x.objectarray.2.ad3 // 600x50
```

La taille maximale de la charge utile d’une variable de données contextuelles donnée (y compris les clés et les valeurs) est de 32 ko. Vous pouvez réduire la taille de cette payload en ajustant les champs pertinents afin qu’ils soient reconnus par Adobe Analytics dans les objets [`xdm`](xdm-var-mapping.md) ou [`data`](data-var-mapping.md).
