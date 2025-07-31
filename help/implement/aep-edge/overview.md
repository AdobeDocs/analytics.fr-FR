---
title: Mettre en œuvre Adobe Analytics à l’aide d’Adobe Experience Platform Edge
description: Présentation de l’utilisation des données XDM d’Experience Platform dans Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: a515927313fdc6025fb3ff8eaedf0b3742bede70
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 17%

---

# Mettre en œuvre Adobe Analytics avec le réseau Edge d&#39;Adobe Experience Platform

Le réseau Edge d&#39;Adobe Experience Platform vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. Le réseau Edge transfère les informations appropriées aux produits souhaités. Ce concept vous permet de consolider les efforts d’implémentation, en particulier sur plusieurs solutions de données. Adobe Analytics est l’un des produits auxquels vous pouvez envoyer des données à l’aide d’Edge Network.

## Comment Adobe Analytics gère les données du réseau Edge

Les données envoyées à Adobe Experience Platform Edge Network peuvent suivre trois formats : **objet XDM**, **objet de données** et **données contextuelles**. Lorsqu’un flux de données transfère des données vers Adobe Analytics, elles sont traduites dans un format qu’Adobe Analytics peut gérer.

## objet `xdm`

Respectez les schémas que vous créez en fonction de [XDM](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home) (modèle de données d’expérience). XDM vous offre davantage de flexibilité quant aux champs définis comme faisant partie d’événements. Si vous souhaitez utiliser un schéma prédéfini spécifique à Adobe Analytics, vous pouvez ajouter le groupe de champs de schéma [Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) à votre schéma. Une fois ajouté, vous pouvez remplir ce schéma à l’aide de l’objet `xdm` dans le SDK Web pour envoyer des données à une suite de rapports. Lorsque les données arrivent à l’Edge Network, elles traduisent l’objet XDM dans un format compris par Adobe Analytics.

Consultez [Mappage des variables d’objet XDM à Adobe Analytics](xdm-var-mapping.md) pour obtenir une référence complète des champs XDM et de leur mappage aux variables Analytics.

>[!TIP]
>
>Si vous prévoyez de migrer vers [Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-landing) à l’avenir, Adobe vous déconseille d’utiliser le groupe de champs de schéma Adobe Analytics. Adobe recommande plutôt de [créer votre propre schéma](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect) et d’utiliser le mappage de flux de données pour renseigner les variables Analytics souhaitées. Cette stratégie ne vous verrouille pas sur un schéma de props et d’eVars lorsque vous êtes prêt à passer à Customer Journey Analytics.

## objet `data`

Au lieu d’utiliser l’objet `xdm`, vous pouvez utiliser l’objet `data` à la place. L’objet de données est destiné aux implémentations qui utilisent actuellement AppMeasurement, ce qui facilite considérablement la mise à niveau vers le SDK Web. Edge Network détecte la présence de champs spécifiques à Adobe Analytics sans avoir besoin de se conformer à un schéma.

Consultez [Mappage des variables d’objet de données à Adobe Analytics](data-var-mapping.md) pour consulter une référence complète des champs d’objet de données et de la manière dont ils sont mappés aux variables Analytics.

## Variables de données contextuelles

Envoyez les données à Edge Network dans le format de votre choix. Tous les champs qui ne sont pas automatiquement mappés à des champs d’objet `xdm` ou `data` sont inclus en tant que [variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) lors du transfert vers Adobe Analytics. Vous devez ensuite utiliser [Règles de traitement](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) pour mapper les champs souhaités à leurs variables Analytics respectives.

Par exemple, si vous disposiez d’un schéma XDM personnalisé qui ressemblait à ce qui suit :

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

Ces champs sont alors les clés de données contextuelles disponibles dans l’interface des Règles de traitement :

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
