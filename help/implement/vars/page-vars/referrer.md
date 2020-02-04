---
title: referrer
description: Remplacez le référent collecté automatiquement pour un accès.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# referrer

La `referrer` variable remplace le référent collecté automatiquement dans les rapports. Cette variable s’avère utile lorsque le référent risque d’être perdu, par exemple lors des redirections ou du transfert temporaire du visiteur vers un processeur de paiement. Cette variable permet de renseigner les dimensions Référent et Domaine référent.

## Référent dans Adobe Experience Platform Launch

Vous pouvez définir le référent soit lors de la configuration de l’extension Analytics (variables globales), soit sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Référent] .

Vous pouvez définir le référent sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.referrer dans AppMeasurement et Lancer l’éditeur de code personnalisé

La `s.referrer` variable est une chaîne contenant l’URL de la page précédente. Cette variable peut stocker un maximum de 255 octets ; les valeurs supérieures à 255 octets sont tronquées. AppMeasurement définit automatiquement cette variable sur `document.referrer`; vous n’avez pas besoin de définir cette variable, sauf si vous souhaitez remplacer la valeur collectée automatiquement.

```js
s.referrer = "https://example.com";
```

Evitez de définir cette variable sur des valeurs autres que les URL.

## Exemple

De nombreuses organisations traitent des implémentations autour des redirections. Vous pouvez utiliser l’ [`getQueryParam`](../functions/util-getqueryparam.md) utilitaire pour obtenir un référent de l’URL si votre site l’accepte. Veillez à coder les valeurs incluses dans la chaîne de requête dans l’URL.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
