---
title: dynamicVariablePrefix
description: Permet de personnaliser la chaîne qui identifie les variables dynamiques.
feature: Variables
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 70%

---

# dynamicVariablePrefix

Les variables dynamiques sont un concept abrégé qui vous permet de copier des valeurs d’une variable vers une autre. Elles s’avèrent utiles pour les longues valeurs de variable, car elles permettent de raccourcir la longueur de l’URL d’une demande d’image. Voir [Variables dynamiques](../page-vars/dynamic-variables.md) pour en savoir plus sur ce concept.

Par défaut, les variables dynamiques utilisent le préfixe `D=`. La variable `dynamicVariablePrefix` vous permet de personnaliser la chaîne qui identifie les variables dynamiques. Elle est sensible à la casse.

## Préfixe de variable dynamique à l’aide du SDK Web

Le SDK Web n’utilise pas de formatage de variable dynamique. Vous pouvez plutôt utiliser le mappage de flux de données pour remplir plusieurs champs cibles à l’aide d’un seul champ source. Voir [Variables dynamiques à l’aide du SDK Web](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk) pour plus d’informations.

Si vous envoyez des données directement à Adobe Analytics sans respecter un schéma, la variable suivante est utilisée :

* [Objet de données](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.dynamicVariablePrefix`

## Préfixe de variable dynamique à l’aide de l’extension Adobe Analytics

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
