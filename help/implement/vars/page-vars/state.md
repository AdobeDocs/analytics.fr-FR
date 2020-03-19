---
title: state
description: Permet de renseigner le « rapport État du visiteur » dans Reports and Analytics.
translation-type: ht
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# state

> [!IMPORTANT] Cette variable a été abandonnée et n’est pas une dimension disponible dans Analysis Workspace. Utilisez plutôt la dimension « États américains », que AppMeasurement collecte automatiquement en fonction de l’emplacement du visiteur.

Dans les versions précédentes d’Adobe Analytics, la variable `state` était utilisée lorsque les visiteurs renseignaient les informations d’expédition sur les sites de vente au détail. Elle est fonctionnellement identique à une prop, mais n’est pas disponible dans Analysis Workspace.

## État dans Adobe Experience Platform Launch

Vous pouvez définir l’état lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL État].

Vous pouvez définir l’état sur n’importe quelle valeur de chaîne ou élément de données.

## s.state dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.state` est une chaîne qui contient généralement l’état ou la province du visiteur. Les noms d’état complets ou les codes à deux lettres sont tous deux valides. Celle-ci a une valeur maximale de 50 octets ; les valeurs plus longues sont tronquées. Sa valeur par défaut est une chaîne vide.

```js
s.state = "Utah";
```
