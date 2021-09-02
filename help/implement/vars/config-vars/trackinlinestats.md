---
title: trackInlineStats
description: Permet d’activer ou de désactiver Activity Map dans votre mise en œuvre.
keywords: désactiver Activity Map
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '196'
ht-degree: 100%

---

# trackInlineStats

Activity Map est une fonctionnalité d’Adobe Analytics qui collecte des données sur l’endroit où les visiteurs cliquent et sur les éléments sur lesquels ils cliquent. Vous pouvez afficher ces données dans les rapports Analytics ou en utilisant une incrustation d’extension de navigateur. Activez cette variable si vous souhaitez utiliser les fonctionnalités d’Activity Map.

Lorsqu’il est activé, AppMeasurement collecte des informations sur le lien et envoie ces données dans la demande d’image suivante. Les informations de chaque clic sont stockées dans un cookie intitulé `s_sq`.

## Activation de ClickMap à l’aide de balises dans Adobe Experience Platform

[!UICONTROL Activer ClickMap] est une case à cocher située sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche la case à cocher [!UICONTROL Activer Clickmap].

Cochez la case pour activer le suivi d’Activity Map.

## s.trackInlineStats dans AppMeasurement et l’éditeur de code personnalisé

La valeur booléenne `s.trackInlineStats` active ou désactive le suivi d’Activity Map. Sa valeur par défaut est `false`. Définissez cette valeur sur `true` si vous souhaitez activer la collecte de données d’Activity Map.

```js
s.trackInlineStats = true;
```
