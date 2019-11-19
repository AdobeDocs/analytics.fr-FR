---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 8deec068fcea49f1183633826d5ce8271fb38a14

---



# s.useForcedLinkTracking

Cet indicateur est utilisé pour désactiver le suivi des liens forcé pour certains navigateurs. Ce type de suivi est activé par défaut pour les navigateurs FireFox 20+ et WebKit.

When `useForcedLinkTracking` is enabled, the AppMeasurement file overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. Le fichier AppMeasurement exécute l’appel de suivi des liens et gère manuellement l’événement de navigation, au lieu d’utiliser l’action par défaut du navigateur.

Dans JavaScript H.25.4 (publié en février 2013), les limites de portée ci-après ont été ajoutées aux liens suivis lorsque `useForcedLinkTracking` est activé. Le suivi forcé automatique des liens s’applique uniquement dans les conditions suivantes :

* Balises `<A>` et `<AREA>`.
* La balise doit avoir un attribut `HREF`.
* The `HREF` can't start with `#`, `about:`, or `javascript:`.
* L’attribut `TARGET` ne doit pas être défini ou `TARGET` doit se rapporter à la fenêtre active (`_self`, `_top` ou à la valeur de `window.name`).

Valeur par défaut = `true`

## Exemple

`s.useForcedLinkTracking = false`
