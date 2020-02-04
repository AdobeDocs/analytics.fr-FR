---
title: État
description: Renseignez le "rapport État du visiteur" dans les rapports et analyses.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# state

> [!IMPORTANT] Cette variable est retirée et n’est pas une dimension disponible dans Analysis Workspace. Utilisez plutôt la dimension Etats-Unis, que AppMeasurement collecte automatiquement en fonction de l’emplacement du visiteur.

Dans les versions précédentes d’Adobe Analytics, la `state` variable était utilisée lorsque les visiteurs renseignaient les informations d’expédition sur les sites de vente au détail. Fonctionnellement identique à une prop, elle n’est pas disponible dans Analysis Workspace.

## Etat du lancement d’Adobe Experience Platform

Vous pouvez définir l’état lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Etat] .

Vous pouvez définir state sur n’importe quelle valeur de chaîne ou élément de données.

## s.state dans AppMeasurement et Lancement de l’éditeur de code personnalisé

La `s.state` variable est une chaîne qui contient généralement l’état ou la province du visiteur. Les noms d’état complet ou les codes à deux lettres sont tous deux valides. Il a une valeur maximale de 50 octets ; les valeurs plus longues sont tronquées. Sa valeur par défaut est une chaîne vide.

```js
s.state = "Utah";
```
