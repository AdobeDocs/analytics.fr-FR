---
description: Les événements personnalisés vous permettent de définir le type de succès dont vous souhaitez effectuer le suivi.
keywords: Implémentation d'Analytics ; événement personnalisé
seo-description: Les événements personnalisés vous permettent de définir le type de succès dont vous souhaitez effectuer le suivi.
seo-title: Qu'est-ce qu'un événement personnalisé ?
solution: Analytics
title: Qu'est-ce qu'un événement personnalisé ?
topic: Développeur et mise en œuvre
uuid: 8 e 78 ba 04-9 b 4 c -4566-980 c-c 24 dd 9 d 82236
translation-type: tm+mt
source-git-commit: d7056c233e784a073c75c55f396ff43c9e0d1c71

---


# Qu'est-ce qu'un événement personnalisé ?

Les événements personnalisés vous permettent de définir le type de succès dont vous souhaitez effectuer le suivi.

Bien que semblables aux événements [!UICONTROL prédéfinis], les événements [!UICONTROL personnalisés] vous permettent de définir votre propre mesure de succès. For example, if you have a newsletter, your success event could be _Registration_. Clearly, _Registration_ is not part of the [!UICONTROL predefined] events. L’utilisation d’un événement [!UICONTROL personnalisé] vous vous permet de suivre le nombre de visiteurs qui s’inscrivent à votre bulletin d’informations. Les événements [!UICONTROL personnalisés] respectent la syntaxe standard illustrée ci-dessous.

```js
s.events="event3"
```

Le code ci-dessus illustre l’affectation d’un événement à la variable _variable events_ . If you do not modify the event name in the interface, _event3_ would display in the interface.

Par défaut, les événements de succès sont configurés en tant qu’événements « _compteur_ ». Ces événements comptabilisent le nombre de fois où un événement de succès est déclenché. Certains événements de réussite exigent qu'un événement soit incrémenté par un montant personnalisé. These events can be set either as _numeric_ events or _currency_ events. Vous pouvez modifier le type d'événement dans la console d'administration.
