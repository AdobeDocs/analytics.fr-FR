---
title: referrer
description: Permet de remplacer le référent collecté automatiquement pour un accès.
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# referrer

La variable `referrer` remplace le référent collecté automatiquement dans les rapports. Cette variable s’avère utile lorsque le référent risque d’être perdu, par exemple lors des redirections ou du transfert temporaire du visiteur vers un processeur de paiement. Cette variable permet de renseigner les dimensions Référent et Domaine référent.

## Référent dans Adobe Experience Platform Launch

Vous pouvez définir le référent soit lors de la configuration de l’extension Analytics (variables globales), soit sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Référent].

Vous pouvez définir le référent sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.referrer dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.referrer` est une chaîne contenant l’URL de la page précédente. Cette variable peut stocker un maximum de 255 octets ; les valeurs supérieures à 255 octets sont tronquées. AppMeasurement définit automatiquement cette variable sur `document.referrer` ; vous n’avez pas besoin de définir cette variable, sauf si vous souhaitez remplacer la valeur collectée automatiquement.

```js
s.referrer = "https://example.com";
```

Évitez de définir cette variable sur des valeurs autres que les URL.

## Exemple

De nombreuses organisations traitent des mises en œuvre autour des redirections. Vous pouvez utiliser l’utilitaire [`Util.getQueryParam()`](../functions/util-getqueryparam.md) pour obtenir un référent de l’URL si votre site l’accepte. Veillez à coder les valeurs incluses dans la chaîne de requête dans l’URL.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
