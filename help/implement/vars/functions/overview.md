---
title: Fonctions et méthodes
description: Découvrez comment utiliser les fonctions et méthodes proposées par Adobe dans votre mise en œuvre.
feature: Variables
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 100%

---

# Fonctions et méthodes

Adobe offre plusieurs fonctions et méthodes que vous pouvez utiliser dans votre implémentation. Lorsque vous référencez ces fonctions ou méthodes, elles effectuent des tâches courantes avec une seule ligne de code.

Certaines de ces lignes de code uniques appartiennent aux catégories suivantes :

* **Suivi des appels** : Les méthodes les plus courantes et essentielles dans de nombreuses implémentations. Elles incluent les méthodes [`t()`](t-method.md) et [`tl()`](tl-method.md).
* **Utilitaires AppMeasurement** : Dans les versions précédentes d’AppMeasurement, les implémentations devaient écrire leur propre code pour exécuter ces tâches. Adobe fournit ces méthodes d’utilitaire pour rationaliser ces tâches courantes. Les utilitaires AppMeasurement incluent [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md) et [`Util.getQueryParam()`](util-getqueryparam.md).
* **Enregistrement des fonctions** : Vous pouvez créer vos propres fonctions et faire en sorte qu’AppMeasurement les exécute automatiquement avant ou après l’envoi d’un appel de suivi à Adobe. Les variables qui tombent dans cette catégorie sont [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md) et [`registerPostTrackCallback()`](registerposttrackcallback.md).
