---
title: referrer
description: Permet de remplacer le référent collecté automatiquement pour un accès.
feature: Appmeasurement Implementation
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
role: Admin, Developer
TQID: https://experienceleague.adobe.com/YsYfgjFNDiJoQbvPU-XoB6bQt2IAriP1qmkOqc2lFDk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 85%

---

# referrer

La variable `referrer` remplace le référent collecté automatiquement dans les rapports. Cette variable s’avère utile lorsque le référent risque d’être perdu, par exemple lors des redirections ou du transfert temporaire du visiteur vers un processeur de paiement. Cette variable permet de renseigner les dimensions Référent et Domaine référent.

## Référent à l’aide du SDK Web

Le référent est mappé sur les variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm.web.webReferrer.URL`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.referrer`

Le SDK Web inclut automatiquement des `web.webReferrer.URL` sur chaque événement envoyé, le cas échéant.

## Référent utilisant l’extension Adobe Analytics

Vous pouvez définir le référent soit lors de la configuration de l’extension Analytics (variables globales), soit sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Référent].

Vous pouvez définir le référent sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.referrer dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.referrer` est une chaîne contenant l’URL de la page précédente. Cette variable peut stocker un maximum de 255 octets ; les valeurs supérieures à 255 octets sont tronquées. AppMeasurement définit automatiquement cette variable sur `document.referrer` ; vous n’avez pas besoin de définir cette variable, sauf si vous souhaitez remplacer la valeur collectée automatiquement.

```js
s.referrer = "https://example.com";
```

Si vous utilisez la `digitalData` [couche de données](../../prepare/data-layer.md) :

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>Évitez de définir cette variable sur des valeurs autres que les URL. Ne retirez pas le protocole de lʼURL.

## Exemple

De nombreuses organisations traitent des mises en œuvre autour des redirections. Vous pouvez utiliser l’utilitaire [`Util.getQueryParam()`](../functions/util-getqueryparam.md) pour obtenir un référent de l’URL si votre site l’accepte. Veillez à coder les valeurs incluses dans la chaîne de requête dans l’URL.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
