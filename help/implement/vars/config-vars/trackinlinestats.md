---
title: trackInlineStats
description: (Retiré) Activez ou désactivez ClickMap dans votre mise en oeuvre.
keywords: désactiver clickmap
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 1cdcc748e50c7eeffa98897006154aa0953ce7e3
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 28%

---

# trackInlineStats

>[!IMPORTANT]
>
>Cette variable a été abandonnée et n’est plus utilisée.

Le ClickMap est une fonctionnalité abandonnée d’Adobe Analytics qui collecte des données sur l’endroit où les visiteurs cliquent et sur les éléments sur lesquels ils cliquent. La fonctionnalité a été remplacée par [Activity Map](/help/analyze/activity-map/overview.md).

Lorsqu’il est activé, AppMeasurement collecte des informations sur le lien et envoie ces données dans la demande d’image suivante. Les informations de chaque clic sont stockées dans un cookie intitulé `s_sq`.

## Activation du ClickMap à l’aide de l’extension Adobe Analytics

[!UICONTROL Activer le ClickMap] est une case à cocher située sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens] , qui affiche la case à cocher [!UICONTROL Activer le ClickMap] .

>[!NOTE]
>
>Cette case à cocher est différente de la case à cocher [!UICONTROL Utiliser l’Activity Map], qui se trouve sous l’accordéon [!UICONTROL Gestion des bibliothèques].

## s.trackInlineStats dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

`s.trackInlineStats` est une valeur booléenne qui active ou désactive le suivi de ClickMap. Puisque la fonction a été abandonnée, Adobe ne recommande pas de définir cette variable. Sa valeur par défaut est `false`.

```js
s.trackInlineStats = false;
```
