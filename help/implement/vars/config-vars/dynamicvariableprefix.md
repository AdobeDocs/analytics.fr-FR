---
title: dynamicVariablePrefix
description: Permet de personnaliser la chaîne qui identifie les variables dynamiques.
feature: Appmeasurement Implementation
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/7Ayfh1-CNzZvurWPaQNTjWuWrgOG8t-NYwdbJLyzFP8'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 71%

---

# dynamicVariablePrefix

Les variables dynamiques sont un concept abrégé qui vous permet de copier des valeurs d’une variable vers une autre. Elles s’avèrent utiles pour les longues valeurs de variable, car elles permettent de raccourcir la longueur de l’URL d’une demande d’image. Voir [Variables dynamiques](../page-vars/dynamic-variables.md) pour en savoir plus sur ce concept.

Par défaut, les variables dynamiques utilisent le préfixe `D=`. La variable `dynamicVariablePrefix` vous permet de personnaliser la chaîne qui identifie les variables dynamiques. Elle est sensible à la casse.

## Préfixe de variable dynamique utilisant le SDK Web

Le SDK Web n’utilise pas le formatage dynamique des variables. Au lieu de cela, vous pouvez utiliser le mappage de flux de données pour renseigner plusieurs champs cibles à l’aide d’un seul champ Source. Voir [Variables dynamiques à l’aide de Web SDK](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk) pour plus d’informations.

Si vous envoyez des données directement à Adobe Analytics sans vous conformer à un schéma, la variable suivante est utilisée :

* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.dynamicVariablePrefix`

## Préfixe de variable dynamique utilisant l’extension Adobe Analytics

Le préfixe de variable dynamique est un champ situé sous l’accordéon [!UICONTROL Variables globales] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Variables globales], qui affiche le champ [!UICONTROL Préfixe de variable dynamique].

Ce champ contient `D=` par défaut. Vous pouvez modifier la valeur si vous souhaitez utiliser un préfixe de variable dynamique différent. Vous pouvez utiliser n’importe quelle valeur, à condition qu’elle corresponde au codage des caractères sur votre site.

## s.dynamicVariablePrefix dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.dynamicVariablePrefix` est une chaîne pouvant contenir n’importe quelle séquence de caractères. Si cette variable n’est pas définie, AppMeasurement utilise la chaîne `D=` par défaut.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
