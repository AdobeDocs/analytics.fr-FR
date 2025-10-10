---
title: state
description: (Retiré) A rempli le « Rapport État du visiteur », qui n’est plus disponible.
feature: Appmeasurement Implementation
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 80%

---

# state

>[!IMPORTANT]
>
>Cette variable a été abandonnée et n’est pas une dimension disponible dans Analysis Workspace. Utilisez plutôt la dimension [&#x200B; États américains &#x200B;](/help/components/dimensions/us-states.md) , qu’AppMeasurement collecte automatiquement en fonction de la localisation du visiteur.

Dans les versions précédentes d’Adobe Analytics, la variable `state` était utilisée lorsque les visiteurs renseignaient les informations d’expédition sur les sites de vente au détail. Elle est fonctionnellement identique à une prop, mais n’est pas disponible dans Analysis Workspace.

## État utilisant l’extension Adobe Analytics

Vous pouvez définir l’état lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à la [collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics, et le [!UICONTROL Type d’action] sur [!UICONTROL Définir les variables].
6. Recherchez la section [!UICONTROL État].

Vous pouvez définir l’état sur n’importe quelle valeur de chaîne ou élément de données.

## s.state dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.state` est une chaîne qui contient généralement l’état ou la province du visiteur. Les noms d’état complets ou les codes à deux lettres sont tous deux valides. Celle-ci a une valeur maximale de 50 octets ; les valeurs plus longues sont tronquées. Sa valeur par défaut est une chaîne vide.

```js
s.state = "Utah";
```
