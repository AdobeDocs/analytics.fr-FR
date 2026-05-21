---
title: eVar (variable)
description: Variables personnalisées que vous pouvez utiliser dans votre mise en œuvre.
feature: Appmeasurement Implementation
exl-id: f89457b2-4186-4276-8637-9992070e3a73
role: Admin, Developer
TQID: https://experienceleague.adobe.com/X5HNYsZBAIMpvsM7ktZhQCSHt1icRQdcpzIkUBJjxv4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 96%

---

# eVar

*Cette page d’aide décrit comment implémenter des eVars. Pour plus d’informations sur le fonctionnement des eVars en tant que dimension, voir [eVars](/help/components/dimensions/evar.md) dans le guide d’utilisation Composants.*

Les eVars sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Si vous disposez d’un [document de conception de solution](/help/implement/prepare/solution-design.md), la plupart des dimensions propres à votre entreprise se présentent sous la forme d’eVars. Par défaut, les eVars persistent au-delà de l’accès sur lequel elles sont définies. Vous pouvez personnaliser leur expiration et leur attribution sous [Variables de conversion](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) dans les paramètres de la suite de rapports.

Le nombre d’eVars disponibles dépend de votre contrat avec Adobe. Si le contrat que vous avez conclu avec Adobe le prévoit, vous pouvez obtenir jusqu’à 250 eVar.

## Configurer des eVars dans les paramètres de la suite de rapports

Avant d’utiliser des eVars dans votre mise en œuvre, veillez à configurer chaque eVar dans les paramètres de la suite de rapports. Reportez-vous à la section [Variables de conversion](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) dans le guide Administrateur.

## eVars utilisant le SDK Web

Les eVars sont mappées aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm._experience.analytics.customDimensions.eVars.eVar1` à `xdm._experience.analytics.customDimensions.eVars.eVar250`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.eVar1` à `data.__adobe.analytics.eVar250` ; ou `data.__adobe.analytics.v1` à `data.__adobe.analytics.v250`

## eVars utilisant l’extension Adobe Analytics

Vous pouvez définir des eVars lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL eVars].

Vous pouvez définir une eVar sur une valeur ou un élément de données. Vous pouvez également copier la valeur d’une autre variable Analytics.

## s.eVar1 - s.eVar250 dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Chaque eVar est une chaîne qui contient des valeurs personnalisées propres à votre organisation. Leur longueur maximale est de 255 octets ; les valeurs de plus de 255 octets sont automatiquement tronquées lorsqu’elles sont envoyées à Adobe.

```js
s.eVar1 = "Example custom value";
```

## eVars de compteur

Les valeurs eVar contiennent généralement une valeur de chaîne. Vous pouvez toutefois configurer les eVars pour qu’elles contiennent un compteur. Par exemple, vous souhaitez comptabiliser le nombre de recherches internes effectuées avant un achat. Au lieu de définir une valeur de texte, utilisez la syntaxe suivante :

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

S’il y a plus de deux décimales, le compteur eVar arrondit la valeur à deux décimales. Un compteur eVar ne peut pas contenir de nombres négatifs.

>[!IMPORTANT]
>
>Vous devez d’abord configurer les eVars sur « Compteur » dans l’Admin Console avant d’utiliser les eVars de compteur. Reportez-vous à la section [Variables de conversion](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) dans le guide Administrateur.
