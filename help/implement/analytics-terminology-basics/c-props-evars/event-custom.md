---
description: Les événements personnalisés vous permettent de définir le type de succès dont vous souhaitez effectuer le suivi.
keywords: Analytics Implementation;custom event
title: Qu’est-ce qu’un événement personnalisé ?
topic: Developer and implementation
uuid: 8e78ba04-9b4c-4566-980c-c24dd9d82236
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Qu’est-ce qu’un événement personnalisé ?

Les événements personnalisés vous permettent de définir le type de succès dont vous souhaitez effectuer le suivi.

Bien que semblables aux événements [!UICONTROL prédéfinis], les événements [!UICONTROL personnalisés] vous permettent de définir votre propre mesure de succès. Dans le cas d’un bulletin d’informations, par exemple, votre événement de succès peut être _Inscription_. Manifestement, _Inscription_ ne fait pas partie des événements [!UICONTROL prédéfinis]. L’utilisation d’un événement [!UICONTROL personnalisé] vous vous permet de suivre le nombre de visiteurs qui s’inscrivent à votre bulletin d’informations. Les événements [!UICONTROL personnalisés] respectent la syntaxe standard illustrée ci-dessous.

```js
s.events="event3"
```

Le code ci-dessus illustre l’affectation d’un événement à la variable Variable _events_. Si vous ne modifiez pas le nom de l’événement dans l’interface, _event3_ s’affiche.

Par défaut, les événements de succès sont configurés en tant qu’événements « _compteur_ ». Ces événements comptabilisent le nombre de fois où un événement de succès est déclenché. Dans certains cas, les événements de succès doivent obligatoirement être incrémentés selon une valeur personnalisée. Ces événements peuvent être définis comme étant de type _numérique_ ou _monétaire_. Vous pouvez modifier le type d’événement dans Admin Console.
