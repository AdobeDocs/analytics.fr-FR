---
title: trackInlineStats
description: Activez ou désactivez Activity Map dans votre implémentation.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackInlineStats

Carte d’activités est une fonctionnalité d’Adobe Analytics qui collecte des données sur l’endroit où les visiteurs cliquent et sur ce sur quoi ils cliquent. Vous pouvez afficher ces données dans les rapports Analytics ou en utilisant une incrustation d’extension de navigateur. Activez cette variable si vous souhaitez utiliser les fonctionnalités de Carte d’activités.

Lorsqu’il est activé, AppMeasurement collecte des informations sur le lien et envoie ces données dans la demande d’image suivante. Les informations de chaque clic sont stockées dans un cookie intitulé `s_sq`.

## Activer Clickmap dans le lancement d’Adobe Experience Platform

[!UICONTROL L’option Activer ClickMap] est une case à cocher située sous l’accordéon Suivi des [!UICONTROL liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon Suivi des [!UICONTROL liens] , qui affiche la case à cocher [!UICONTROL Activer ClickMap] .

Cochez la case pour activer le suivi de Carte d’activités.

## s.trackInlineStats dans AppMeasurement et lancement de l’éditeur de code personnalisé

La valeur booléenne `s.trackInlineStats` active ou désactive le suivi de Carte d’activités. Its default value is `false`. Définissez cette valeur sur `true` si vous souhaitez activer la collecte de données de Carte d’activités.

```js
s.trackInlineStats = true;
```
