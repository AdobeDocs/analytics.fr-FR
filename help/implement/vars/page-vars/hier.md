---
title: hier
description: (Retiré) Mettez en oeuvre des variables de hiérarchie dans Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 93%

---

# hier

>[!IMPORTANT]
>
>Cette variable a été abandonnée et n’est pas une dimension disponible dans Analysis Workspace. Adobe recommande d’utiliser plutôt des [eVars](evar.md) et des classifications.

Les variables de hiérarchie sont des variables personnalisées qui vous permettent de voir la structure d’un site. Adobe prend en charge jusqu’à 5 variables de hiérarchie dans votre mise en œuvre.

Cette variable est utile pour les sites dont la structure comprend plus de trois niveaux. Par exemple, la section Sports d’un site multimédia peut comporter 4 niveaux : `Sports`, `Local Sports`, `Baseball` et `Team name`. Si un visiteur accède à la page Base-ball, les niveaux Sports, Sports locaux et Base-ball reflètent tous cette visite.

Avant d’utiliser des hiérarchies dans votre mise en œuvre, veillez à configurer chaque hiérarchie dans les paramètres de la suite de rapports.

## Hiérarchies utilisant le SDK Web

Les hiérarchies sont [mappées pour Adobe Analytics](/help/implement/aep-edge/xdm-var-mapping.md) sous les champs XDM `xdm._experience.analytics.customDimensions.hierarchies.hier1` à `xdm._experience.analytics.customDimensions.hierarchies.hier5`.

## Hiérarchies utilisant l’extension Adobe Analytics

Vous pouvez définir les hiérarchies soit lors de la configuration de l’extension Analytics (variables globales), soit sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la variable [!UICONTROL Extension] de la liste déroulante vers Adobe Analytics, et de la variable [!UICONTROL Type d’action] to [!UICONTROL Définition de variables].
6. Recherchez la section [!UICONTROL Hiérarchie].

Vous pouvez définir une valeur de hiérarchie sur une chaîne statique ou référencer un élément de données. Vous pouvez également définir le délimiteur souhaité. Assurez-vous que le délimiteur que vous définissez ici correspond au délimiteur défini dans les paramètres de la suite de rapports.

## s.hier1 - s.hier5 dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Chaque hiérarchie est une chaîne qui contient des valeurs personnalisées propres à votre organisation. Leur longueur maximale est de 255 octets ; les valeurs de plus de 255 octets sont automatiquement tronquées lorsqu’elles sont envoyées à Adobe.

Veillez à ce qu’aucun de vos noms de section ne comporte de séparateur. Par exemple, si l’une de vos sections est appelée `Coach Griffin, Jim`, choisissez un délimiteur autre qu’une virgule. La limite de variable totale est de 255 octets. Les délimiteurs peuvent être composés de plusieurs caractères, tels que `||` ou `/|\`, qui sont moins susceptibles d’apparaître dans les valeurs de variable.

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
