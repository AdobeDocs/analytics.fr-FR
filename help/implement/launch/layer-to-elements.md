---
title: Mise en correspondance des objets de couche de données avec les éléments de données
description: Configurez les balises pour la lecture à partir de votre couche de données.
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 46%
---
# Mise en correspondance des objets de couche de données avec les éléments de données

Une fois que votre organisation a établi et implémenté une couche de données sur votre site, vous pouvez mapper des objets de couche de données à des éléments de données au sein des balises.

## Conditions préalables

[Créer une couche de données](../prepare/data-layer.md) : Assurez-vous qu’une couche de données existe sur votre site. Techniquement, vous pouvez mettre en correspondance n’importe quel objet JavaScript ou récupérer des éléments CSS directement à partir de la page, mais Adobe recommande cette pratique en dernier recours. Si la mise en page de votre site change, les sélecteurs CSS utilisés dans les balises cessent de fonctionner, ce qui entraîne une perte de données.

## Utilisation de balises pour créer des éléments de données

Les [éléments de données](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=fr) sont des composants dans la collecte de données Adobe Experience Platform que vous pouvez utiliser dans l’ensemble de l’outil. Vous pouvez attribuer des valeurs de variable dans l’extension Adobe Analytics à l’aide d’éléments de données.

Les étapes suivantes utilisent l’[extension de la couche de données client Adobe](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/client-data-layer/overview), qui doit être installée dans votre propriété de balise.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Sélectionnez la propriété de balise de votre choix.
1. Sélectionnez l’onglet **[!UICONTROL Éléments de données]**, puis sélectionnez **[!UICONTROL Ajouter un élément de données]**.

   ![Création d’un élément de données](assets/createelement.png)

1. Saisissez un nom pour votre élément de données, tel que `Page name`.
1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Couche de données client Adobe]**.
1. Dans la liste déroulante **[!UICONTROL Type d’élément de données]**, sélectionnez **[!UICONTROL État calculé de la couche de données]**.
1. Sous **[!UICONTROL Valeur renvoyée]**, sélectionnez **[!UICONTROL Chemin spécifique]**, puis saisissez le chemin d’accès à la valeur dans votre couche de données, tel que `page.name`. Pour valider un chemin d’accès, exécutez `adobeDataLayer.getState("page.name")` dans la console de votre navigateur.
1. Sélectionnez **[!UICONTROL Enregistrer]**.

Utilisez ces éléments de données dans les règles que déclenche l’événement **[!UICONTROL Push de la couche de données]** de l’extension, de sorte que la couche de données ait chargé et contienne les données de la notification push. Voir [Types d’éléments de données](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/client-data-layer/data-element-types#computed-state).

### Couches de données basées sur des objets {#object-based}

Si votre couche de données est un objet JavaScript, tel qu’un objet CEDDL `digitalData`, utilisez plutôt le type d’élément de données **[!UICONTROL Variable JavaScript]** à partir de l’extension **[!UICONTROL Core]**. Saisissez le chemin d’accès à la valeur, par exemple `digitalData.page.pageInfo.pageName`. Ce type d’élément de données ne peut pas lire la couche de données client Adobe, qui stocke ses données dans un état calculé au lieu de dans les propriétés d’objet.

## Étapes suivantes

[Mise en correspondance d’éléments de données aux variables Analytics](elements-to-variable.md) : Affectez des éléments de données à des variables Analytics afin de les utiliser comme dimensions dans Analysis Workspace.
