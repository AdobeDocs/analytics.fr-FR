---
title: zip
description: Permet de renseigner manuellement la dimension « Code postal » si les paramètres de la suite de rapports le permettent.
feature: Appmeasurement Implementation
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/dv564yEz9tChaxot0w65ZGIc1T0Jqdnp1Mua0QUbn5Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 275
ht-degree: 81%

---

# zip

La variable `zip` vous permet de renseigner manuellement la dimension « Code postal » si l’[!UICONTROL option de code postal] des paramètres de la suite de rapports l’autorise. Dans les versions précédentes d’Adobe Analytics, cette variable ne pouvait être définie manuellement que lors de la saisie d’informations d’expédition sur un site de vente au détail. Les améliorations apportées à Adobe Analytics permettent de définir automatiquement cette variable à l’aide des données de géolocalisation. Cette variable ne persiste pas au-delà de l’accès auquel elle est définie.

>[!IMPORTANT]
>
>Assurez-vous que l’[!UICONTROL option de code postal] des paramètres de la suite de rapports est définie sur la valeur souhaitée. Vous ne pouvez pas utiliser cette variable si [!UICONTROL Geo zip] est toujours utilisé. Pour plus d’informations, consultez la section [Paramètres généraux du compte](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) du guide d’utilisation destiné à l’administrateur.

## Code postal utilisant le SDK Web

Le code postal est mappé aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm.placeContext.geo.postalCode`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.zip`

## Code postal utilisant l’extension Adobe Analytics

Vous pouvez définir le code postal lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Code postal].

Vous pouvez définir le code postal sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.zip dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.zip` est une chaîne qui contient généralement un code postal, mais qui peut contenir toute valeur souhaitée jusqu’à 50 octets de longueur.

```js
s.zip = "84043";
```
