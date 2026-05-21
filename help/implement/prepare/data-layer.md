---
title: Création d’une couche de données
description: Découvrez quelle couche de données se trouve dans votre mise en œuvre Analytics et comment elle peut être utilisée pour mapper des variables dans Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 476
ht-degree: 100%

---

# Création d’une couche de données

Une couche de données est une structure d’objets JavaScript sur votre site qui contient les valeurs de variable utilisées dans votre mise en œuvre Analytics. Elle permet un meilleur contrôle et une maintenance plus facile lors de l’attribution de valeurs aux variables Analytics.

## Conditions préalables

[Créer un document de conception de solution :](solution-design.md) il est important que votre entreprise s’aligne sur les exigences de suivi. Assurez-vous d’être préparé et de disposer d’un document de conception de solution avant de contacter les équipes de développement de votre organisation.

## Workflow

La mise en œuvre d’Adobe Analytics à l’aide d’une couche de données suit généralement les étapes suivantes :

1. **Collaborez avec votre équipe de développement de site pour mettre en œuvre une couche de données :** votre équipe de développement de site est principalement chargée de s’assurer que l’objet de couche de données est renseigné avec les valeurs correctes. Consultez cette page avec votre équipe de développement de site pour vous assurer que les attentes sont harmonisées entre les équipes.

   >[!NOTE]
   >
   >Le respect des spécifications de couche de données recommandées par Adobe est facultatif. Si vous disposez déjà d’une couche de données ou si vous choisissez de ne pas respecter les spécifications d’Adobe, assurez-vous que votre entreprise s’aligne sur les spécifications à suivre.

1. **Validez la couche de données à l’aide d’une console de navigateur :** une fois une couche de données créée, vous pouvez vérifier qu’elle fonctionne à l’aide de la console de développement de n’importe quel navigateur. Vous pouvez ouvrir la console de développement dans la plupart des navigateurs à l’aide de la clé `F12`. Un exemple de valeur de variable serait `adobeDataLayer.page.title`.
1. **Utilisez la collecte de données Adobe Experience Platform pour mapper les objets de couche de données aux éléments de données** : Cette étape varie en fonction de la méthode de mise en œuvre de votre entreprise :
   * **Si vous utilisez le SDK Web** : mappez les objets de couche de données de votre choix aux champs XDM désirés dans Adobe Experience Platform Edge. Consultez [Mappage des variables XDM Analytics](../aep-edge/xdm-var-mapping.md) pour déterminer le mappage de couche de données souhaité.
   * **Si vous utilisez l’extension Analytics** : créez des éléments de données sous l’onglet Balises dans la collecte de données Adobe Experience Platform et affectez-les aux objets de couche de données de votre choix. Ensuite, dans l’extension Analytics, affectez chaque élément de données à la variable Analytics appropriée.

## Spécifications

Adobe recommande d’utiliser la [couche de données du client Adobe](https://github.com/adobe/adobe-client-data-layer/wiki) pour les nouvelles implémentations ou les implémentations restructurées.

Votre entreprise peut utiliser d’autres spécifications de couche de données, comme la [couche de données numériques de l’expérience client](https://www.w3.org/2013/12/ceddl-201312.pdf), ou une autre spécification personnalisée. L’alignement sur une couche de données cohérente répondant aux besoins de votre entreprise est le plus important.

Les couches de données sont extensibles ; si vous avez des exigences spécifiques à votre entreprise, vous pouvez inclure des objets dans la couche de données pour répondre à ces besoins.

## Définition des valeurs de couche de données

Les couches de données génèrent généralement des données côté serveur, référençant les mêmes objets que ceux utilisés pour créer le contenu du site. Définissez la couche de données du site en fonction des exigences de suivi définies dans le [document de conception de solution](solution-design.md) de votre entreprise.

## Étapes suivantes

[Mapper des objets de couche de données à des éléments de données](../launch/layer-to-elements.md) : utilisez la couche de données de votre site dans Adobe Experience Platform.
