---
title: Fonctions et méthodes
description: Découvrez comment utiliser les fonctions et les méthodes qu’Adobe   dans votre implémentation.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Fonctions et méthodes

Adobe   plusieurs fonctions et méthodes que vous pouvez utiliser dans votre implémentation. Lorsque vous référencez ces fonctions ou méthodes, elles effectuent des  courantes avec une seule ligne de code.

Certaines de ces lignes de code uniques appartiennent au  de suivant :

* **Suivi des appels**: Les méthodes les plus courantes et essentielles dans de nombreuses implémentations. Ils incluent les méthodes [`t()`](t-method.md) et [`tl()`](tl-method.md) les méthodes.
* **Utilitaires** AppMeasurement : Dans les versions précédentes d’AppMeasurement, les implémentations devaient écrire leur propre code pour exécuter ces  de. Adobe fournit ces méthodes d’utilitaire pour rationaliser ces  de courants. Les utilitaires AppMeasurement incluent [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md)et [`Util.getQueryParam()`](util-getqueryparam.md).
* **Enregistrer les fonctions**: Vous pouvez écrire vos propres fonctions et faire en sorte qu’AppMeasurement les exécute automatiquement avant ou après l’envoi d’un appel de suivi à Adobe. Les variables qui se trouvent sous cette  sont [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md)et [`registerPostTrackCallback()`](registerposttrackcallback.md).
