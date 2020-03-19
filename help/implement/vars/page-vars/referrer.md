---
title: referrer
description: Remplacez le  de collecte automatique pour un accès.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# referrer

La `referrer` variable remplace le collecté automatiquement dans les rapports. Cette variable s’avère utile lorsque le  du risque d’être perdu, par exemple lors des redirections ou du transfert temporaire du vers un processeur de paiement. Cette variable permet de renseigner les dimensions &quot;&quot; et &quot;Domaine référent&quot;.

##  dans Adobe Experience Platform Launch

Vous pouvez définir des  lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une [!UICONTROL Adobe Analytics - Set Variables] action existante ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Referrer] section.

Vous pouvez définir le  sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.referrer` variable est une chaîne contenant l’URL de la page précédente. Cette variable peut stocker un maximum de 255 octets ; les valeurs supérieures à 255 octets sont tronquées. AppMeasurement définit automatiquement cette variable sur `document.referrer`; vous n’avez pas besoin de définir cette variable, sauf si vous souhaitez remplacer la valeur collectée automatiquement.

```js
s.referrer = "https://example.com";
```

Evitez de définir cette variable sur des valeurs autres que les URL.

## Exemple

De nombreuses organisations traitent des implémentations autour des redirections. Vous pouvez utiliser l’ [`Util.getQueryParam()`](../functions/util-getqueryparam.md) utilitaire pour obtenir des  à partir de l’URL si votre site les accepte. Assurez-vous que vous codez l’URL pour toutes les valeurs incluses dans la chaîne de  du.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
